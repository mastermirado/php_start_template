Build image
Start container

Go to interactive container

Run composer create project symfony/skeleton:"8.0.x"  
Run mv skeleton/.* . #copy dot files
Run mv skeleton/* . #copy sources files
rm -rf skeleton/

#rm -rf bin/ config/ public/ src/ var/ vendor/ symfony.lock composer.* .*


