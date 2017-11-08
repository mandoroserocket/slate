# Internal Rose Rocket Readme

To build the docs:
```
$ bundle exec middleman build --clean
```

To copy to platform docs:
```
$ cp -R /usr/local/src/github.com/roserocket/api-docs/build/* /usr/local/src/github.com/roserocket/roserocket/platform/static/docs/.
$ cp /usr/local/src/github.com/roserocket/api-docs/source/swagger/swagger.json /usr/local/src/github.com/roserocket/roserocket/platform/static/docs/swagger.json
```