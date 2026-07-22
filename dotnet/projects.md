# .NET : Projects

## Create Projects

```bash
dotnet new console -n Application
dotnet new classlib -n Application.Core
dotnet new webapi -n Application.Api
dotnet new xunit -n Application.Tests
```

## Project File

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net10.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>
</Project>
```

Keep project responsibilities narrow, enable nullable analysis for new code, and avoid placing environment secrets or machine-specific paths in project files.
