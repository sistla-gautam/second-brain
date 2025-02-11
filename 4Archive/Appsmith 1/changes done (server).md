### AuthenticationSuccessHandlerCE
line 280
```Java
isFromSignup = user.getCreatedAt().isAfter(Instant.now().minusSeconds(5));
---
 isFromSignup = false;

```
set isFormSignup to false instead of checking if the user is a signup or not

---
line 213
```Java
Mono<Void> redirectionMono = null;

        User user = (User) authentication.getPrincipal();

        Mono<Boolean> isVerificationRequiredMono = Mono.just(FALSE);
        
        
---
 Mono<Void> redirectionMono;

        User user = (User) authentication.getPrincipal();

        Mono<Boolean> isVerificationRequiredMono;

```
not setting a default value, as the isVerfiicationRequiredMono is getting its values from other assignments.

---
line 206
```Java
    private Mono<Void> formEmailVerificationRedirectionHandler(

            WebFilterExchange webFilterExchange,

            String defaultWorkspaceId,

            Authentication authentication,

            Boolean isFromSignup,

            Boolean createDefaultApplication,

            String originHeader) {
            
---

private Mono<Void> formEmailVerificationRedirectionHandler(

            WebFilterExchange webFilterExchange,

            String defaultWorkspaceId,

            Authentication authentication,

            Boolean isFromSignup,

            Boolean createDefaultApplication) {
```
the function is not taking the origin header from the function parameters

---
line 419
```Java
return applicationMono.flatMap(application1 -> applicationPageService.createApplication(application1));

---

return applicationMono.flatMap(applicationPageService::createApplication);
```
both are same, just different representations of the same thing

---
### WorkspaceServiceCEImpl

line 158
```Java
//
---
 if (user.getSource() != LoginSource.FORM) {

            createWorkspaceAllowedMono = Mono.just(FALSE);

        }
```
if the user is not a FORM login, then createWorkspaceAllowedMono is not allowed

---
line 167
```Java
return Mono.error(

                                new AppsmithException(AppsmithError.ACTION_IS_NOT_AUTHORIZED, "Create workspace"));
                                
---
//
```
removed the error messages for the applications not created