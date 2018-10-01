Jak rozjet testy nad `Nette/Database` v dockeru?

- fetchni si někam z githubu `Nette/Database` do adresáře `database`
- zavolej tam

```
composer install
```

- zkopči obsah tohoto adresaře do složky `docker` vedle checkoutnuté složky `database` s `Nette\Database`
- pak jdi do této složky a zavolej

```
docker-compose up
```

- tím se spustí kontejner pro PHP a pro MySQL
- vlez do terminálu, otevři terminál pro docker container s PHPčkem: 

```
docker exec -it docker_php_1 /bin/bash
```

- v testech v adresáři `Database` je nutné doplnit soubor `database.ini` s infem pro připojení s obsahem:

```
[mysql]
dsn = "mysql:host=mysql_database"
user = root
password = root

```

- uvnitř terminálu ve složce s repozitářem `database` zavolej:

```
 php ./vendor/bin/tester 'tests/Database/Table/SqlBuilder.addWhere().phpt' -s -C
```

- ten přepínač `-C` tam hodí defaultní `php.ini`, musí tam být, jinak to nepojede, páč nebudou naloadovaný extenze etc.
