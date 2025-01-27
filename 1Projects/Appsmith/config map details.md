```yaml
apiVersion: v1
data:
  APPSMITH_CLOUD_SERVICES_BASE_URL: https://release-cs.appsmith.com
  APPSMITH_CODEC_SIZE: "10"
  APPSMITH_DB_URL: mongodb://ydxyokoadmin:m4Vo*E0o9E@10.202.64.14:27017,10.202.64.15:27017,10.202.64.16:27017/appsmith?replicaSet=rs0&authSource=admin&ssl=false
  APPSMITH_DISABLE_IFRAME_WIDGET_SANDBOX: "false"
  APPSMITH_ENCRYPTION_PASSWORD: abcd
  APPSMITH_ENCRYPTION_SALT: abcd
  APPSMITH_FORM_LOGIN_DISABLED: "false"
  APPSMITH_MAIL_ENABLED: "false"
  APPSMITH_MAIL_HOST: https://ydx.test.apps.yokogawa.build/api/sensors/Email
  APPSMITH_MAIL_PORT: "25"
  APPSMITH_MAIL_SMTP_AUTH: "true"
  APPSMITH_MAIL_SMTP_TLS_ENABLED: "true"
  APPSMITH_OAUTH2_SAPCDC_CLIENT_ID: redZClCiq003bqsBt8aMMNM3
  APPSMITH_OAUTH2_SAPCDC_CLIENT_SECRET: MIsfNP7UTEwm0viZ4Sm98eNGnLY4JTqgrCsT6mQstStbWs9p3Li_SCKnmAiiI0szokCuBAvsksFqsDanVyUL9A
  APPSMITH_REDIS_URL: redis://appsmith-alpha-redis-master-0.appsmith-alpha-redis-headless.appsmith-alpha.svc.cluster.local:6379
  APPSMITH_SIGNUP_DISABLED: "false"
kind: ConfigMap
metadata:
  annotations:
    meta.helm.sh/release-name: appsmith-alpha
    meta.helm.sh/release-namespace: appsmith-alpha
  creationTimestamp: "2025-01-23T06:57:40Z"
  labels:
    app.kubernetes.io/instance: appsmith-alpha
    app.kubernetes.io/managed-by: Helm
    app.kubernetes.io/name: appsmith
    appsmith.sh/chart: appsmith-alpha-1.0.0
  name: appsmith-alpha
  namespace: appsmith-alpha
  resourceVersion: "214868267"
  uid: 61c4dd68-32b5-49f6-ac05-91940efa908a
```