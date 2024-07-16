- the main page that gets rendered for the setup screen is the ==`UserWelcomeScreen.tsx`==
- Needs to be replaced with the screen that is similar to YDX login

##### Things to note
- Every string message that needs to be displayed is part of a ==`StringConstants`== file
- the constants are of arrow function type
	- each constant is an arrow function that accepts no input values and returns the required string
		```javascript
		export const MESSAGE = ()=>"This is a message"
		```
- the form is placed in ==`DetailsForm.tsx`== file
- 