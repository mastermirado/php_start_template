#Build image
docker compose build

#Start container
docker compose up -d

#Go to interactive container
docker exec -it php-app sh

CASE 1
#Install symfony 8 for example
composer create-project symfony/skeleton:"8.0.x"  

CASE 2
#Install laravel for example
composer create-project laravel/laravel skeleton

#copy dot files
mv skeleton/.* . skeleton/* . 

#remove skeleton directory
rm -rf skeleton/

#restart project
docker compose down
docker compose up -d

#For laravel, update permissions
chmod -R 777 storage

#rm -rf bin/ config/ public/ src/ var/ vendor/ symfony.lock composer.* .*


