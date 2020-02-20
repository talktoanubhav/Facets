#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.
RUN curl -fsSLO https://get.docker/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
  && tar xzvf docker-17.04.0-ce.tgz \
  && mv docker/docker /usr/local/bin \
  && rm -r docker docker-17.04.0-ce.tgz
  
FROM mcr.microsoft.com/dotnet/core/runtime:3.1-buster-slim AS base
WORKDIR /app

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["AnubhavConsole/AnubhavConsole.csproj", "AnubhavConsole/"]
RUN dotnet restore "AnubhavConsole/AnubhavConsole.csproj"
COPY . .
WORKDIR "/src/AnubhavConsole"
RUN dotnet build "AnubhavConsole.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "AnubhavConsole.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "AnubhavConsole.dll"]
