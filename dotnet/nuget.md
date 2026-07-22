# .NET : NuGet

## Package Commands

```bash
dotnet add package Package.Name
dotnet remove package Package.Name
dotnet list package
dotnet list package --outdated
dotnet restore
```

## Package Reference

```xml
<ItemGroup>
  <PackageReference Include="Package.Name" Version="1.2.3" />
</ItemGroup>
```

Use approved feeds, inspect transitive dependencies, pin versions according to project policy, review licenses, and enable vulnerability auditing in the build workflow.
