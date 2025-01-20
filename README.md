# Projet de démarrage avec django-oscar

```bash
$ docker compose exec solr ./bin/solr create -c sandbox -n basic_config
$ docker compose cp solr:/opt/solr/solr/server/solr/sandbox/conf ./solr_config
```

```yaml
volumes:
  - ...
  - ./solr_config:/opt/solr/solr/server/solr/sandbox/conf
```

```bash
$ docker compose down
$ docker compose up -d
```

```bash
$ python manage.py build_solr_schema --configure-directory=./solr_config
$ python manage.py build_solr_schema --reload-core sandbox
$ python manage.py rebuild_index --noinput
```