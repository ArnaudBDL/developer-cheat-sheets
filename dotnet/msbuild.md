# .NET : MSBuild

## Build Properties

```xml
<PropertyGroup>
  <TargetFramework>net10.0</TargetFramework>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <ContinuousIntegrationBuild Condition="'$(CI)' == 'true'">true</ContinuousIntegrationBuild>
</PropertyGroup>
```

## Commands

```bash
dotnet build -c Release
dotnet build -p:ContinuousIntegrationBuild=true
dotnet msbuild -getProperty:TargetFramework
```

Keep shared properties in deliberate repository-level build files, avoid machine-specific paths, and inspect evaluated properties when configuration behaves unexpectedly.
