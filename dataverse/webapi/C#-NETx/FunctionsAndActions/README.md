# Web API Functions and Actions sample

This .NET 6.0 sample demonstrates how to use OData Functions and Actions using the Dataverse Web API.

This sample uses the common helper code in the [WebAPIService](../WebAPIService) class library project.

## Prerequisites

- Microsoft Visual Studio 2022.
- Access to Dataverse with privileges to perform data operations.

## How to run the sample

1. Clone or download the [PowerApps-Samples](../../../../../PowerApps-Samples) repository.
1. Open the [FunctionsAndActions.sln](FunctionsAndActions.sln) file using Visual Studio 2022.
1. Edit the [appsettings.json](../appsettings.json) file to set the following property values:

   |Property|Instructions  |
   |---------|---------|
   |`Url`|The Url for your environment. Replace the placeholder `https://yourorg.api.crm.dynamics.com` value with the value for your environment. See [View developer resources](https://docs.microsoft.com/power-apps/developer/data-platform/view-download-developer-resources) to find this. |
   |`UserPrincipalName`|Replace the placeholder `you@yourorg.onmicrosoft.com` value with the UPN value you use to access the environment.|
   |`Password`|Replace the placeholder `yourPassword` value with the password you use.|

1. Save the `appsettings.json` file
1. Press F5 to run the sample.

## Demonstrates

This sample has 9 regions:

### Section 1: Unbound Functions: WhoAmI

Operations: Use the [WhoAmI Function](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/whoami) with the WebAPIService [WhoAmIRequest](../WebAPIService/Messages/WhoAmIRequest.cs) and [WhoAmIResponse](../WebAPIService/Messages/WhoAmIResponse.cs) classes.

### Section 2: Unbound Functions: FormatAddress

Operations: Use the [FormatAddress Function](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/formataddress) with the WebAPIService [FormatAddressRequest](../WebAPIService/Messages/FormatAddressRequest.cs) and [FormatAddressResponse](../WebAPIService/Messages/FormatAddressResponse.cs) classes.

### Section 3: Unbound Functions: InitializeFrom

Operations: Use the [InitializeFrom Function](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/initializefrom) with the WebAPIService [InitializeFromRequest](../WebAPIService/Messages/InitializeFromRequest.cs) and [InitializeFromResponse](../WebAPIService/Messages/InitializeFromResponse.cs) classes.

### Section 4: Unbound Functions: RetrieveCurrentOrganization

Operations: Use the [RetrieveCurrentOrganization Function](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/retrievecurrentorganization) with the WebAPIService [RetrieveCurrentOrganizationRequest](../WebAPIService/Messages/RetrieveCurrentOrganizationRequest.cs) and [RetrieveCurrentOrganizationResponse](../WebAPIService/Messages/RetrieveCurrentOrganizationResponse.cs) classes.

### Section 5: Unbound Functions: RetrieveTotalRecordCount

Operations: Use the [RetrieveTotalRecordCount Function](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/retrievetotalrecordcount) with the WebAPIService [RetrieveTotalRecordCountRequest](../WebAPIService/Messages/RetrieveTotalRecordCountRequest.cs) and [RetrieveTotalRecordCountResponse](../WebAPIService/Messages/RetrieveTotalRecordCountResponse.cs) classes.

### Section 6: Bound Functions: IsSystemAdmin

Operations: Use a custom `sample_IsSystemAdmin` operation created using Custom API as a function bound to the `systemuser` table.

This code will install a managed solution containing the Custom API. Then it will use the [IsSystemAdminRequest](Messages/IsSystemAdminRequest.cs) and [IsSystemAdminResponse](Messages/IsSystemAdminResponse.cs) classes defined within this sample application.

This sample will retrieve a set of users and test each one to determine whether the System Administrator security role is associated with their `systemuser` record or a team they belong to.

[Sample: IsSystemAdmin Custom API](../../../orgsvc/C%23/IsSystemAdminCustomAPI/) describes the Custom API used by this sample.

### Section 7: Unbound Actions: GrantAccess

Operations: Use the [GrantAccess Action](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/grantaccess) with the WebAPIService [GrantAccessRequest](../WebAPIService/Messages/GrantAccessRequest.cs) class.

### Section 8: Bound Actions: AddPrivilegesRole

Operations: Use the [AddPrivilegesRole Action](https://docs.microsoft.com/power-apps/developer/data-platform/webapi/reference/addprivilegesrole) with the WebAPIService [AddPrivilegesRoleRequest](../WebAPIService/Messages/AddPrivilegesRoleRequest.cs) class.

### Section 9: Delete sample records

Operations: A reference to each record created in this sample was added to a list as it was created. In this sample the records are deleted using a `$batch` operation.

## Clean up

By default this sample will delete all the records created in it.

If you want to view created records after the sample is completed, change the `deleteCreatedRecords` variable to `false` and you will be prompted to decide if you want to delete the records.
