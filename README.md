# FileUpload
 This application allows you to upload and download files over the web. This application is a cloud-native application built on Microsoft Azure.

## How to start development
1. isntall composer packages
   1. composer install
2. create .env file
   1. cp .env.example .env
3. change owner
   1. chown -R www-data:www-data /var/www/html/app
4. update permission storage
   1. chmod -R 775 /var/www/html/app/storage
