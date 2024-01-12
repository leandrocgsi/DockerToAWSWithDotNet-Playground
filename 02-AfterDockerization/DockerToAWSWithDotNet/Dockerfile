FROM microsoft/aspnetcore:2.0 AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/aspnetcore-build:2.0 AS build
WORKDIR /src
COPY DockerFromZeroToMastery/DockerFromZeroToMastery.csproj DockerFromZeroToMastery/
RUN dotnet restore DockerFromZeroToMastery/DockerFromZeroToMastery.csproj
COPY . .
WORKDIR /src/DockerFromZeroToMastery
RUN dotnet build DockerFromZeroToMastery.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish DockerFromZeroToMastery.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "DockerFromZeroToMastery.dll"]
