# Build image
docker compose build

# Start container
docker compose up -d

# Clean eventual container who block installation 
# (optional)

# Go to interactive container
docker exec -it php-app sh

CASE 1
# Install symfony 8 for example
composer create-project symfony/skeleton:"8.0.x"  

CASE 2
# Install laravel for example
composer create-project laravel/laravel skeleton
or composer create-project laravel/laravel:"11.x.x" skeleton (for specific version)

# Replace structure
mv skeleton/.* . skeleton/* . 

# Remove skeleton directory
rm -rf skeleton/

# Rename container_name & networks

# Restart project
docker compose down
docker compose up -d --force-recreate 

# For laravel, update permissions
chmod -R 777 storage

#rm -rf bin/ config/ public/ src/ var/ vendor/ symfony.lock composer.* .*

