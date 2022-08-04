FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019 AS build

COPY . ./src/
WORKDIR /src

RUN nuget restore eShopLegacyWebForms.sln

#RUN msbuild eShopLegacyWebForms.csproj -t:restore /p:Configuration=Release /p:BuildingProject=true /p:OutDir=..\PUBLISH
RUN msbuild eShopLegacyWebForms.sln /p:Configuration=Release /p:BuildingProject=true /p:OutDir=..\PUBLISH

#RUN echo $(ls)
#RUN echo $(ls src)
#RUN echo $(ls src/PUBLISH)
#RUN echo $(ls src/PUBLISH/_PublishedWebsites/eShopLegacyWebForms)
#RUN echo $(ls src/PUBLISH/_PublishedWebsites/eShopLegacyWebForms/bin)

FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8-windowsservercore-ltsc2019 AS runtime
WORKDIR /inetpub/wwwroot
COPY --from=build src/src/PUBLISH/_PublishedWebsites/eShopLegacyWebForms/ ./

#RUN echo $(ls)
