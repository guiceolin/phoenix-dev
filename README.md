## Phoenix Dev Image

[![](https://badge.imagelayers.io/guiceolin/docker-phoenix-dev:latest.svg)](https://imagelayers.io/?images=guiceolin/docker-phoenix-dev:latest 'Get your own badge on imagelayers.io')

This image has an complete enviroment to developing apps using [Elixir](elixir-lang.org) and [Phoenix Framework](http://phoenixframework.org)

#### USAGE
----

Can be user stand alone, eg:

```
$ docker run --rm -v $(pwd):/code guiceolin/phoenix-dev mix --version
Mix 1.0.5
```

Or inside docker-compose:

```
# docker-compose.yml
web:
  image: guiceolin/phoenix-dev
  volumes:
    - ./:/code
  links:
    - db
  ports:
    - 4000:4000
  command: mix phoenix.server
db:
  image: jonathancamp/alpine-postgres
  environment:
    POSTGRES_USER: DBUSERNAME
    POSTGRES_PASSWORD: SECUREANDLONGPASSWORD
    
```
and then:
```
docker-compose up
```

#### Contents
---

This image contains an complete elixir dev environment, provided by [msaraiva/elixir-dev](https://github.com/msaraiva/docker-alpine/tree/master/dockerfiles/elixir/1.0.5)

plus the Phoenix dependencies, including `psql`.

ImageSize: 70.14 MB
