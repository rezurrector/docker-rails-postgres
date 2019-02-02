# docker-rails-postgres
Docker Ruby On Rails Image

##Pre Requisites
[Reference ruby on rails docker image](https://docs.docker.com/compose/rails/)
[Install docker compose](https://docs.docker.com/compose/install/)

##Installation Steps
git clone https://github.com/rezurrector/docker-rails-postgres.git
cd docker-rails-postgres.git
docker-compose run web rails new . --force --no-deps --database=postgresql
sudo chown -R $USER:$USER .
docker-compose build

```yaml
#config/database.yml
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: 5

development:
  <<: *default
  database: myapp_development

test:
  <<: *default
  database: myapp_test
```

docker-compose up

docker-compose run web rake db:create
docker-compose down  

##References
[Rails Guides](https://guides.rubyonrails.org)
[Ruby Docs](https://www.ruby-lang.org)