FROM mcr.microsoft.com/dotnet/sdk:5.0

WORKDIR ${APP_ROOT}

COPY . ${APP_ROOT}

RUN dotnet publish -c Debug -o publish

WORKDIR ${APP_ROOT}/publish

CMD [ "dotnet", "dotnetcore.dll" ]
