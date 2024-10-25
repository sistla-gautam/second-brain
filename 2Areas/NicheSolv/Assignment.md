## User flow
- Add -> Add button -> do the POST -> redirect back to the list
- Edit -> the same .jsp as the Add -> prefill the values -> edit the values -> redirect back to list
- delete -> delete servlet -> redirect to the list

### comments
- only redirection 
	- no HTML flushed from the servlet
- every servlet
	- should only contain the `doGet`, `doPost`, `redirect` methods