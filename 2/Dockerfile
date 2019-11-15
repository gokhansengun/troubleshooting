FROM mcr.microsoft.com/dotnet/core/sdk:3.0.100-bionic AS build

COPY ./web.csproj /src/

WORKDIR /src

RUN dotnet restore

COPY . .

RUN dotnet build "web.csproj" -c Release -o /app
RUN dotnet publish "web.csproj" -c Release -o /app


FROM mcr.microsoft.com/dotnet/core/aspnet:3.0.0-bionic

EXPOSE 80
WORKDIR /app

COPY ./entrypoint.sh /app/

COPY --from=build /app .

ENTRYPOINT dotnet /app/web.dll
