# Docker Magento

Docker image for magento

## Installation

Clone the project using the following command:

```bash
git clone https://github.com/jsalazarv/magento-docker.git
```

You need to create an .env file at the root level of the project as shown in the .env.example file and set the environment variables for the project to work properly.

```bash
WEB_PORT=
DB_ROOT_PASSWORD=
DB_DATABASE=
DB_USERNAME=
MYSQL_PASSWORD=
```

Inside the folder that contains the docker-compose.yml file, you must run the following command.

```bash
docker-compose up -d
```

Enter the container with the following command.

```bash
docker exec -it "CONTAINER_NAME" bash
```

Change the user 'magento2' with the following command.

```bash
su magento2
```

Now you must download Magento with the following command

```bash
php -d memory_limit=8G /usr/local/bin/composer create-project --repository-url=https://repo.magento.com/ magento/project-enterprise-edition .
```

You must enter the credentials for magento.

You should indicate to Magento the following parameters:

--base-url =
--db-host =
--db-name =
--db-user =
--db-name =
--db-password =

```bash
bin/magento setup:install --base-url=http://training.wolf/ \
--db-host=mysql --db-name=training --db-user=magentodb --db-password=magento \
--admin-firstname=Juan --admin-lastname=Salazar --admin-email=juansalazar@wolfsellers.com \
--admin-user=admin --admin-password=admin123 --language=es_MX \
--currency=USD --timezone=America/Chicago --use-rewrites=1 \
--search-engine=elasticsearch7 --elasticsearch-host=elasticsearch7 \
--elasticsearch-port=9200
```
