# Stage 1 - Build the application
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /src
COPY MultiStage.csproj .
RUN dotnet restore 
COPY . .

RUN dotnet build "MultiStage.csproj" -c Release -o /app/build

# Stage 2 - Publish the application
RUN dotnet publish -c Release -o /app

# Stage 3 - Build the runtime image
FROM mcr.microsoft.com/dotnet/sdk:8.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MultiStage.dll"]