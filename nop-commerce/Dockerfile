FROM mcr.microsoft.com/dotnet/aspnet:6.0 as build
LABEL Author="tarun"
LABEL app="nopCommerce"
ENV MYSQL_ROOT_PASSWORD = "rootroot"
ENV MYSQL_DATABASE = "mysql-db"
ENV MYSQL_USER = "mysql-user"
ENV MYSQL_PASSWORD = "mysql-password"
VOLUME [ "/var/lib/mysql" ]
ADD https://github.com/nopSolutions/nopCommerce/releases/download/release-4.50.3/nopCommerce_4.50.3_NoSource_linux_x64.zip .
RUN apt update && \
    apt install unzip -y && \
    unzip ./nopCommerce_4.50.3_NoSource_linux_x64.zip 
ENTRYPOINT [ "dotnet", "Nop.Web.dll", "run", "--server.urls=http://0.0.0.0:*" ]
EXPOSE 80 3306


