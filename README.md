# BlazorTable

**Work in progress!**

A simple Table Control for Blazor

[Demo Site](https://BlazorTable.netlify.com/)

[![Nuget (with prereleases)](https://img.shields.io/nuget/vpre/BlazorTable.svg)](https://www.nuget.org/packages/BlazorTable)

![](https://github.com/IvanJosipovic/BlazorTable/workflows/CI/CD/badge.svg)

### Features
- Edit Mode Template Switching
- Client Side
	- Paging
	- Sorting

### Todo
- Client Side
    - Filtering
      - String
      - Numbers (WIP)

- Server Side
	- Paging
	- Sorting
	- Filtering

- Remove dependency on Bootstrap + BlazorStrap


 - Responds to [CORS preflight requests](https://developer.mozilla.org/en-US/docs/Glossary/Preflight_request)
	 1. Default header values (configurable)
		 - Access-Control-Allow-Origin = *
		 - Access-Control-Allow-Method = *
		- Access-Control-Allow-Headers = *
		- Access-Control-Max-Age = 86400
 2. Adds �Access-Control-Allow-Origin� to all responses


### Sample
[Example](/src/BlazorTable.Sample/Pages/Index.razor)

```csharp
<Table TableItem="PersonData" Items="data" PageSize="15">
    <Column TableItem="PersonData" Title="Id" Property="@(x => x.id)" Sortable="true">
        <Template>
            @context.id
        </Template>
    </Column>
    <Column TableItem="PersonData" Title="First Name" Property="@(x => x.first_name)" Sortable="true">
        <Template>
            @context.first_name
        </Template>
    </Column>
    <Column TableItem="PersonData" Title="Last Name" Property="@(x => x.last_name)" Sortable="true">
        <Template>
            @context.last_name
        </Template>
    </Column>
    <Column TableItem="PersonData" Title="Email" Property="@(x => x.email)" Sortable="true">
        <Template>
            <a href="mailto:@context.email">@context.email</a>
        </Template>
    </Column>
    <Column TableItem="PersonData" Title="Gender" Property="@(x => x.gender)" Sortable="true">
        <Template>
            @context.gender
        </Template>
    </Column>
    <Column TableItem="PersonData" Title="IP" Property="@(x => x.ip_address)" Sortable="true">
        <Template>
            @context.ip_address
        </Template>
    </Column>
    <Pager TableItem="PersonData" />
</Table>
```