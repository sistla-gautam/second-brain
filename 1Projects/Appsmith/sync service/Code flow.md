## controller
### dependency injection
```C#
private readonly ISyncBIDashboardUsers syncBIDashboardUsers;
```
- we first do dependency injection for the BIDashboard

### routing
```c#
/// <summary>
/// AddEngineeringConsoleUsers
/// </summary>
/// <returns></returns>
[HttpPost]
[Route("console")]
public async Task<IActionResult> AddEngineeringConsoleUsers()
{
	var result = await syncEngineeringConsoleUsers.Add();
	if (result.StatusCode == HttpStatusCode.OK)
	{
		return new ObjectResult(result);
	}
	return new ObjectResult(result) { StatusCode = StatusCodes.Status500InternalServerError };
}
```
- we then create a route for the required operations and map them to the specific operation in the class
- this is calling the `syncEngineeringConsoleUsers.Add()` function

### syncEngineeringConsoleUsers.Add() function
```C#
{
	string tenantName = string.Empty;
	try
	{
		Logger.LogMessageToConsole(LogLevel.INFO, String.Format(SyncConstant.SYNC_START_MESSAGE, SyncConstant.UserAddOpertaion, tenantName, SyncConstant.DASHBOARD_APP_NAME), System.DateTime.UtcNow.ToString());
		Tenant tenants = await helper.GetTenantList();
		foreach (var result in tenants.Results)
		{
			tenantName = result.Data.Name;
			Logger.LogMessageToConsole(LogLevel.INFO, string.Format("Tenant For loop Entered, TenantName:{0}, ApplicationName:{1} ", tenantName, SyncConstant.DASHBOARD_APP_NAME), System.DateTime.UtcNow.ToString());
			var tupleToken = await GetToken(tenantName);

			string token = tupleToken.Item1;

			if (!string.IsNullOrEmpty(token))
			{
				var tuple = await GetData(tenantName, SyncConstant.UserAddOpertaion, token);

				var groupList = tuple.Item1;
				var dashboardUsers = tuple.Item2;
				var users = tuple.Item3;

				if (users.UserList != null && users.UserList.Count > 0)
				{
				   string addUseruri = $"{EnvironmentValues.DashboardEndPoint}{tenantName}/{EnvironmentValues.DashboardEndPointVersion}/users";
				   await biOperations.AddUser(dashboardUsers, users, groupList, addUseruri, SyncConstant.DASHBOARD_APP_NAME, tenantName, token);
				}
			}
		}
		Logger.LogMessageToConsole(LogLevel.INFO, String.Format(SyncConstant.SYNC_COMPLETED_MESSAGE, SyncConstant.UserAddOpertaion, tenantName, SyncConstant.DASHBOARD_APP_NAME), System.DateTime.UtcNow.ToString());
		return new BaseEntity() { StatusCode = HttpStatusCode.OK };
	}
	catch (Exception ex)
	{
		Logger.LogMessageToConsole(LogLevel.INFO, String.Format(SyncConstant.SYNC_COMPLETED_ERROR_MESSAGE, SyncConstant.UserAddOpertaion, tenantName, SyncConstant.DASHBOARD_APP_NAME, ex.Message), System.DateTime.UtcNow.ToString(), ex.ToString());
		return new BaseEntity() { ErrorMessage = ex.Message, StatusCode = HttpStatusCode.InternalServerError };
	}

}
```
- this is calling 2 specific functions which are serving as helper functions
	- `helper.GetTenantList()`
	- `GetData()`

###### getTenantList function
- this function will return the list of all the tenants that are available
###### GetData function
- this function will return us the following things
	- list of all users from the dashboard
	- list of all users data from the dashboard
	- list of all users from the SAPCDC
- all these details are tenant specific