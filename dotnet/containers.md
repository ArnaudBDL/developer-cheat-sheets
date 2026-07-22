# .NET : Containers

## Container Build

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:10.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "Application.Api.dll"]
```

Use approved pinned images, run as a non-root identity where practical, keep secrets out of layers, separate build and runtime stages, scan images, and configure health, resource and shutdown behavior.
