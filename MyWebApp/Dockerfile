FROM mcr.microsoft.com/dotnet/sdk AS build
COPY . ./src
WORKDIR /src
RUN dotnet build -o /app
RUN dotnet publish -o /publish
 
FROM mcr.microsoft.com/dotnet/aspnet AS base
COPY --from=build  /publish /app
WORKDIR /app
EXPOSE 80
CMD ["./myWebApp"]