# Server App - WebAPI

Scenario: Protected web API

<https://learn.microsoft.com/en-us/azure/active-directory/develop/scenario-protected-web-api-overview>

Protect a web API with Microsoft Identity platform

<https://learn.microsoft.com/en-us/azure/active-directory/develop/web-api-quickstart?pivots=devlang-aspnet-core>

## Register application

| | |
|-|-|
| Display Name | Demo Server WebAPI | 
| Application (client) ID | `cd67a751-e146-495b-81e7-5c1e9bdc618f` |
| Directory Tenant ID | `2a8d6e38-f847-47c9-bf7d-71334a7a948d` | 

## Expose an API

### Add a scope

| | |
|-|-|
| Application ID URI (default) | `api://cd67a751-e146-495b-81e7-5c1e9bdc618f` |
| Scope name | `access_as_user` |
| Who can consent? | `Admins and users` |
| Admin consent display name | `Access Demo Server WebAPI` |
| Admin consent description | `Allows the app to access Demo Server WebAPI as the signed-in user`  |
| User consent display name | `Access Demo Server WebAPI` |
| User consent description | `Allow the application to access Demo Server WebAPI on your behalf` |
| State | `Enabled` |


## Sample Application 

[Download the ASP.NET Core solution](https://github.com/Azure-Samples/active-directory-dotnet-native-aspnetcore-v2/archive/aspnetcore3-1.zip) from GitHub.

```
wget https://github.com/Azure-Samples/active-directory-dotnet-native-aspnetcore-v2/archive/aspnetcore3-1.zip
unzip aspnetcore3-1.zip
rm aspnetcore3-1.zip
cd active-directory-dotnet-native-aspnetcore-v2-aspnetcore3-1
```

Update webapi/appsettings.json file
```
"ClientId": "Enter_the_Application_Id_here",
"TenantId": "Enter_the_Tenant_Info_Here"
```

### Install dotnet sdk

```
sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

```
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
chmod +x dotnet-install.sh
./dotnet-install.sh --help
```

