# Build stage
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src

# copy csproj first to leverage layer caching
COPY backend/CDEImp6.csproj ./
RUN dotnet restore

# now copy the rest
COPY backend ./
RUN dotnet publish -c Release -o /app/publish

# Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app
COPY --from=build /app/publish ./
ENV ASPNETCORE_URLS=http://0.0.0.0:9000
EXPOSE 8080
ENTRYPOINT ["dotnet", "CDEImp6.dll"]
