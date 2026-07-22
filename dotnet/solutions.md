# .NET : Solutions

## Solution Commands

```bash
dotnet new sln -n Application
dotnet sln Application.sln add src/Application.Core/Application.Core.csproj
dotnet sln Application.sln add tests/Application.Tests/Application.Tests.csproj
dotnet sln Application.sln list
dotnet sln Application.sln remove path/to/project.csproj
```

## Project Reference

```bash
dotnet add tests/Application.Tests/Application.Tests.csproj reference src/Application.Core/Application.Core.csproj
```

Solutions group projects for coordinated build and tooling. Keep dependency direction intentional and avoid circular project references.
