> Configuration Properties
The appsettings.json file contains configuration settings for your .NET application. Below is a description of each property and how to access them programmatically.
Properties
1.	PublisherTenantId
•	Description: The Id of the workload publisher tenant.
•	Example: "PublisherTenantId": "your-tenant-id"
2.	ClientId
•	Description: Client ID (AppId) of the workload AAD application. Should match the AppId value in AAD application in WorkloadManifest.xml.
•	Example: "ClientId": "00000000-0000-0000-0000-000000000000"
3.	ClientSecret
•	Description: The secret for the workload AAD application.
•	Example: "ClientSecret": "your-client-secret"
4.	Audience
•	Description: Audience for incoming AAD tokens. Should match the ResourceId value in AAD application in WorkloadManifest.xml.
•	Example: "Audience": "api://localdevinstance/tenantID/Org.WorkloadSample"
To obtain the values for PublisherTenantId, ClientId, ClientSecret, and Audience from Azure, follow these steps:
> Steps to Get Configuration Values from Azure
1. Create an Azure Active Directory (AAD) Application
1.	Sign in to the Azure portal:
•	Go to Azure Portal.
2.	Navigate to Azure Active Directory:
•	In the left-hand navigation pane, click on "Azure Active Directory".
3.	Register a new application:
•	Click on "App registrations" in the left-hand menu.
•	Click on "New registration".
•	Enter a name for your application.
•	Select the supported account types (e.g., "Accounts in this organizational directory only").
•	Enter a redirect URI if needed (optional).
•	Click "Register".
4.	Get the Application (client) ID:
•	After registration, you will be redirected to the application's overview page.
•	Copy the "Application (client) ID". This is your ClientId.
5.	Get the Directory (tenant) ID:
•	On the application's overview page, copy the "Directory (tenant) ID". This is your PublisherTenantId.
2. Create a Client Secret
1.	Navigate to Certificates & secrets:
•	In the left-hand menu of the application, click on "Certificates & secrets".
2.	Create a new client secret:
•	Under "Client secrets", click on "New client secret".
•	Add a description for the client secret.
•	Set an expiration period.
•	Click "Add".
3.	Copy the client secret value:
•	After creating the client secret, copy the value immediately. This is your ClientSecret.
•	Note: You won't be able to see the client secret value again after you leave the page.
3. Set the API Permissions
1.	Navigate to API permissions:
•	In the left-hand menu of the application, click on "API permissions".
2.	Add permissions:
•	Click on "Add a permission".
•	Select the API your application needs to access (e.g., Microsoft Graph).
•	Select the permissions your application needs (e.g., "User.Read").
•	Click "Add permissions".
3.	Grant admin consent:
•	Click on "Grant admin consent for [your organization]".
•	Confirm the action.
4. Configure the Audience
1.	Set the Audience:
•	The Audience value should match the ResourceId value in your AAD application.
•	Typically, it follows the format: api://<your-application-id>.
