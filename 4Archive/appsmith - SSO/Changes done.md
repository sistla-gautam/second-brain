##### Login.tsx

- location - `app/client/src/pages/UserAuth/Login.tsx`
- code
```tsx
import React, { useCallback, useEffect, useState } from "react";
import { Redirect, useLocation } from "react-router-dom";
import { connect, useSelector } from "react-redux";
import type { InjectedFormProps, DecoratedFormProps } from "redux-form";
import { reduxForm, formValueSelector, isDirty } from "redux-form";
import {
  LOGIN_FORM_NAME,
  LOGIN_FORM_EMAIL_FIELD_NAME,
  LOGIN_FORM_PASSWORD_FIELD_NAME,
} from "@appsmith/constants/forms";
import { FORGOT_PASSWORD_URL, SETUP, SIGN_UP_URL } from "constants/routes";
import {
  LOGIN_PAGE_TITLE,
  FORM_VALIDATION_EMPTY_PASSWORD,
  FORM_VALIDATION_INVALID_EMAIL,
  LOGIN_PAGE_SIGN_UP_LINK_TEXT,
  LOGIN_PAGE_INVALID_CREDS_ERROR,
  LOGIN_PAGE_INVALID_CREDS_FORGOT_PASSWORD_LINK,
  NEW_TO_APPSMITH,
  createMessage,
} from "@appsmith/constants/messages";
import { Link, Callout, Button } from "design-system";
import ThirdPartyAuth from "pages/UserAuth/ThirdPartyAuth";
import { isEmail, isEmptyString } from "utils/formhelpers";
import type { LoginFormValues } from "pages/UserAuth/helpers";

import { LOGIN_SUBMIT_PATH } from "@appsmith/constants/ApiConstants";
import { getIsSafeRedirectURL } from "utils/helpers";
import { getCurrentUser } from "selectors/usersSelectors";
import Container from "pages/UserAuth/Container";
import {
  getThirdPartyAuths,
  getIsFormLoginEnabled,
  getTenantConfig,
} from "@appsmith/selectors/tenantSelectors";
import Helmet from "react-helmet";
import { useFeatureFlag } from "utils/hooks/useFeatureFlag";
import { FEATURE_FLAG } from "@appsmith/entities/FeatureFlag";
import { getHTMLPageTitle } from "@appsmith/utils/BusinessFeatures/brandingPageHelpers";
import config from './config.json';
import styled from "styled-components";
// import { jwtDecode } from "jwt-decode";

import type { EventName } from "@appsmith/utils/analyticsUtilTypes";
import AnalyticsUtil from "@appsmith/utils/AnalyticsUtil";
import PerformanceTracker, {
  PerformanceTransactionName,
} from "utils/PerformanceTracker";


const validate = (values: LoginFormValues, props: ValidateProps) => {
  const errors: LoginFormValues = {};
  const email = values[LOGIN_FORM_EMAIL_FIELD_NAME] || "";
  const password = values[LOGIN_FORM_PASSWORD_FIELD_NAME];
  const { isPasswordFieldDirty, touch } = props;
  if (!password || isEmptyString(password)) {
    isPasswordFieldDirty && touch?.(LOGIN_FORM_PASSWORD_FIELD_NAME);
    errors[LOGIN_FORM_PASSWORD_FIELD_NAME] = createMessage(
      FORM_VALIDATION_EMPTY_PASSWORD,
    );
  }
  if (!isEmptyString(email) && !isEmail(email)) {
    touch?.(LOGIN_FORM_EMAIL_FIELD_NAME);
    errors[LOGIN_FORM_EMAIL_FIELD_NAME] = createMessage(
      FORM_VALIDATION_INVALID_EMAIL,
    );
  }

  return errors;
};

type LoginFormProps = {
  emailValue: string;
} & InjectedFormProps<LoginFormValues, { emailValue: string }>;

type ValidateProps = {
  isPasswordFieldDirty?: boolean;
} & DecoratedFormProps<
  LoginFormValues,
  { emailValue: string; isPasswordFieldDirty?: boolean }
>;

export function Login(props: LoginFormProps) {
  const location = useLocation();
  const isFormLoginEnabled = useSelector(getIsFormLoginEnabled);
  const socialLoginList = useSelector(getThirdPartyAuths);
  const queryParams = new URLSearchParams(location.search);
  const isBrandingEnabled = useFeatureFlag(
    FEATURE_FLAG.license_branding_enabled,
  );
  const tentantConfig = useSelector(getTenantConfig);
  const { instanceName } = tentantConfig;
  const htmlPageTitle = getHTMLPageTitle(isBrandingEnabled, instanceName);
  const invalidCredsForgotPasswordLinkText = createMessage(
    LOGIN_PAGE_INVALID_CREDS_FORGOT_PASSWORD_LINK,
  );
  let showError = false;
  let errorMessage = "";
  const currentUser = useSelector(getCurrentUser);
  if (currentUser?.emptyInstance) {
    return <Redirect to={SETUP} />;
  }
  if (queryParams.get("error")) {
    errorMessage = queryParams.get("message") || queryParams.get("error") || "";
    showError = true;
  }
  let loginURL = "/api/v1/" + LOGIN_SUBMIT_PATH;
  let signupURL = SIGN_UP_URL;
  const redirectUrl = queryParams.get("redirectUrl");
  if (redirectUrl != null && getIsSafeRedirectURL(redirectUrl)) {
    const encodedRedirectUrl = encodeURIComponent(redirectUrl);
    loginURL += `?redirectUrl=${encodedRedirectUrl}`;
    signupURL += `?redirectUrl=${encodedRedirectUrl}`;
  }

  let forgotPasswordURL = `${FORGOT_PASSWORD_URL}`;
  if (props.emailValue && !isEmptyString(props.emailValue)) {
    forgotPasswordURL += `?email=${props.emailValue}`;
  }

  const [isToken, setIsToken] = useState(false)
  
  // const token = localStorage.getItem('access_token')

  // const handleToken = () => {
  //     const params = [
  //       'client_id=' + config.clientId,
  //       'redirect_uri=' + encodeURIComponent(config.redirectUri),
  //       'scope=' + config.scope,
  //       'response_type=' + config.responseType,
  //       'response_mode=' + config.responseMode
  //     ];
  //     window.location.href = config.authorizeUri + '?' + params.join('&');
  // }

  // useEffect(()=> {
  //   if(!token && isToken) {
  //     handleToken();
  //   }
  // }, [isToken])

  const path = window.location.pathname;
  const accessToken = localStorage.getItem('access_Token');

  const queryParameters = new URLSearchParams(window.location.search);
  const code = queryParameters.get("code");

  const handleToken = useCallback(async () => {
    console.log('handleToken---', accessToken);
    const tokenParameters = new URLSearchParams(window.location.search);
    const token = tokenParameters.get("token");
    console.log('token---', token);
    if (token) {
      console.log('valid token---', token);
      storeSessionInfo(token);
      await fetch('https://auth-api.opst1.apps.yokogawa.build/users/me', {
        headers: { Authorization: `Bearer ${token}` },
      })
        .then((response) => response.json())
        .then((data) => storeUserInfo(data))
        .catch((error) => console.log("userInfoUri Error: ", error));

      window.location.href = `${window.location.origin}${window.location.pathname}`;
      return;
    } else if (
      (!accessToken) &&
      !path.includes("callback")
    ) {
      const redirectUri = `${window.location.origin}/biviewer/callback`;
      const params = [
        "client_id=" + "Tywflo1cX1zVfZDzy4FUKbDo",
        "redirect_uri=" + encodeURIComponent(redirectUri),
        "scope=" + config.scope,
        "response_type=" + config.responseType,
        "response_mode=" + config.responseMode,
      ];
      console.log('redirect URI---', "https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/authorize?" + params.join("&"));
      window.location.href =
        "https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/authorize" + "?" + params.join("&");

      return;
    }
  }, [accessToken, path]);

  const getAccessToken = useCallback(async (accessCode) => {
    const redirectUri = `${window.location.origin}/applications/`;
    const formData = new FormData();
    formData.append("code", accessCode);
    formData.append("client_id", "Tywflo1cX1zVfZDzy4FUKbDo");
    formData.append("client_secret", "RsGxAAh-Sm4N8eeiXeMePgdedRZJyZbeyKiJUj7XjAZzscDxaiXpl_aPA0a0afe_pUDYMVpgX9TxMvK4RFwUVQ");
    formData.append("redirect_uri", redirectUri);
    formData.append("grant_type", 'authorization_code');

    const payload = {
      method: "POST",
      body: formData,
    };

    let accessToken;
    // get sapcdc token
    await fetch("https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/authorize", payload)
      .then((response) => response.json())
      .then((data) => {
        console.log('token uri---', data);
        if(!data.error) {
          storeLocalStorage(data);
          accessToken = data['access_token'];
        }
      })
      .catch((error) => {
        console.error("tokenUri Error:", error);
      });

    // get user details from sapcdc token
    await fetch("https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/userinfo", {
      headers: { Authorization: `Bearer ${accessToken}` },
    })
      .then((response) => response.json())
      .then((data) => {
        console.log('user info uri---', data);
        // if (tenants.length > 1) {
          // setIsModalOpen(true);
        // } else {
          // storeUserInfo(data);
          // window.location.href = "/biviewer";
        // }
        storeUserInfo(data);
        // window.location.href = "/biviewer";
      })
      .catch((error) => {
        console.log("userInfoUri Error: ", error);
      });

      // get platform token from sapcdc token
      const tenant = localStorage.getItem('tenants');
      let platformTokenUrl = `${window.location.origin}/tokens/v1/${tenant}`;
      platformTokenUrl = platformTokenUrl.replace("cloud", "api");
      // const platformTokenUrl = 'https://api.opst1.apps.yokogawa.build/tokens/v1/OP-DT01';
      await fetch(platformTokenUrl, {
        headers: { Authorization: `Bearer ${accessToken}` },
      })
        .then((response) => response.json())
        .then((data) => {
          console.log('platform token uri---', data);
          localStorage.setItem(
            'access_Token',
            data['token']
          );
          window.location.href = "/applications/";
        })
        .catch((error) => {
          console.log("platformUri Error: ", error);
        });
  }, []);

  useEffect(() => {
    if(isToken){
      if (code) {
        getAccessToken(code);
      } else {
        handleToken();
      }
    }
  }, [code, getAccessToken, handleToken, isToken]);

  const ThirdPartyAuthWrapper = styled.div`
  display: flex;
  gap: var(--ads-v2-spaces-3);
  width: 100%;
  flex-wrap: wrap;
`;

  const StyledButton = styled(Button)`
    flex: 1 0 171px;
  `;

  return (
    <Container title={createMessage(LOGIN_PAGE_TITLE)}>
      <Helmet>
        <title>{htmlPageTitle}</title>
      </Helmet>

      {showError && (
        <Callout
          kind="error"
          links={
            !!errorMessage
              ? undefined
              : [
                  {
                    children: invalidCredsForgotPasswordLinkText,
                    to: FORGOT_PASSWORD_URL,
                  },
                ]
          }
        >
          {!!errorMessage && errorMessage !== "true"
            ? errorMessage
            : createMessage(LOGIN_PAGE_INVALID_CREDS_ERROR)}
        </Callout>
      )}
      <ThirdPartyAuth logins={socialLoginList} type={"SIGNIN"} />
      <ThirdPartyAuthWrapper>
        <StyledButton
          kind="secondary"
          onClick={() => {
            setIsToken(true)
          }}
          renderAs="a"
          size="md"
        >
          <div className="login-method" >
            {'SAP/CDC'}
          </div>
        </StyledButton>
      </ThirdPartyAuthWrapper>
    </Container>
  );
}

const selector = formValueSelector(LOGIN_FORM_NAME);
export default connect((state) => ({
  emailValue: selector(state, LOGIN_FORM_EMAIL_FIELD_NAME),
  isPasswordFieldDirty: isDirty(LOGIN_FORM_NAME)(
    state,
    LOGIN_FORM_PASSWORD_FIELD_NAME,
  ),
}))(
  reduxForm<LoginFormValues, { emailValue: string }>({
    validate,
    touchOnBlur: false,
    form: LOGIN_FORM_NAME,
  })(Login),
);

export const storeSessionInfo = (token_value: string) => {
  const time = new Date().getTime();
  // const decoded = jwtDecode(token);
  // const exp = decoded.exp;
  // const expiresIn = Math.round(exp - new Date().getTime() / 1000);
  localStorage.setItem('clientType', "CONSOLE");
  localStorage.setItem('access_token', token_value);
  localStorage.setItem('storeTime', time.toString());
  // localStorage.setItem('expires_in', expiresIn);
};

export const storeUserInfo = (response: { [x: string]: string; tenants: string; }) => {
  console.log('storeUserInfo---', response);
  localStorage.setItem(
    'given_name',
      response['given_name']
  );
  localStorage.setItem('email', response['email']);
  const tenants = JSON.parse(response.tenants);
  console.log('tenants---', tenants);
  let tenantName;
  if(tenants.length > 1){
      tenantName = tenants[0].tenant_name;
  } else {
      tenantName = tenants.tenantName;
  }
  console.log('tenantName---', tenantName);
  localStorage.setItem(
      'tenants',
      tenantName
  );
};

// export const isTimeExpired = () => {
//   // let expirationTime = Number.parseInt(
//   //   localStorage.getItem(stringConstant.expiresIn)
//   // );
//   // let storeTime = Number.parseInt(
//   //   localStorage.getItem(stringConstant.storeTime)
//   // );
//   let currentTime = new Date().getTime();
//   let difference = (currentTime - storeTime) / 1000;
//   return difference > expirationTime;
// };

export const storeLocalStorage = (response: { [x: string]: string; }) => {
  console.log('storeLocalStorage---', response);
  let time = new Date().getTime();
  localStorage.setItem(
    'sapCdc_token',
    response['access_token']
  );
};
```
---
#### config.json

- location - `app/client/src/pages/UserAuth/config.json`
- code

```JSON
{
    "clientId": "Tywflo1cX1zVfZDzy4FUKbDo",
    "authorizeUri": "https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/authorize",
    "tokenUri": "https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/token",
    "redirectUri": "https://seed-webapp-sso.msa.apps.yokogawa.dev/callback", 
    "userInfoUri": "https://fidm.us1.gigya.com/oidc/op/v1.0/4_lAYiWUZ69vbwCzNEhKvvcA/userinfo",
    "logOutUri": "https://sso-static.opst1.apps.yokogawa.build/oidcLogout.php",
    "adminUrl": "https://sso.msa.apps.yokogawa.dev/admin/auth/user?tenant=YDX",
    "scope": "openid email profile tenants",
    "responseType": "code",
    "responseMode": "query",
    "platformTokenServiceUri": "https://api.msa.apps.yokogawa.dev/tokens/v1/"
}
```
---
#### Application.property

- location - `app/client/src/pages/UserAuth/config.json`