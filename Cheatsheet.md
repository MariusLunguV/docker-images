## Sitecore Docker Repository (Clone locally)
git clone https://github.com/Sitecore/docker-images

## Change Directory to Root of Cloned Repository
cd docker-images

## Run Build.ps1 (with default tags)
.\Build.ps1

## Set Path for Licence File
.\Set-LicenseEnvironmentVariable.ps1 -Path D:\License\License

## Compose Docker Sitecore Containers (Takes list of Containers and start Containers)
docker-compose -f .\docker-compose.xp.yml up

## Compose Docker Sitecore Containers (Takes list of Containers and turns them down)
docker-compose -f .\docker-compose.xp.yml down

## Lists currently running Containers
docker container ls

## Lists all aimages locally available
docker image ls
docker images

## List Volumes
docker volume ls

## List Networks
docker network ls

## Remove all unused containers (all stopped containers, all networks not used by at least one container, all dangling images, etc)
docker system prune

## Remove all unused Volumes
docker system prune --Volumes

## Remove a Docker container by ID (use 'docker container ls -a' to get list of container IDs)
docker container rm {{ID}}

## Remove a Docker image by ID (use 'docker image ls' to get list of image IDs)
docker image rm {{ID}}

## Removes (and un-tags) all images from the host node (--force to force removal)
docker rmi $(docker images -a -q)

## After you run a docker topology, you should clean data folder (.\Clean-Data.ps1 in the windows\tests\9.3.0 folder)
~\windows\tests\9.x.x\Clean-Data.ps1

## View your Docker container here: (default below)
http://localhost:44001 (CM)
http://localhost:44002 (CD)
localhost:44010 (SQL)

## Execute Powershell inside a Container - {{ID}} should match a container ID
docker exec -it {{ID}} powershell

## Configure the Docker Url in your Docker-Compose yml File
## Under 'ports' under each instance