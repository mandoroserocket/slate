## Working on docs

1.  Start the server

```
$ bundle exec middleman server
```

2.  If you're working on API, you can just open the index.html from the url the server is hosted on.

```
e.g.: http://192.168.86.37:4567/index.html
```

2.  If you're working on Webhooks, you can just open the webhooks.html from the url the server is
    hosted on.

```
e.g.: http://192.168.86.37:4567/webhooks.html
```

3.  When you're done

Build the docs:

```
$ bundle exec middleman build --clean
```

Then copy to platform docs:

```
$ cp -R /usr/local/src/github.com/roserocket/api-docs/build/* /usr/local/src/github.com/roserocket/roserocket/platform/static/docs/.
```

# Swagger files

To convert from swagger to slate use widdersins

```
$ node /usr/local/src/github.com/Mermade/widdershins/widdershins.js /usr/local/src/github.com/roserocket/api-docs/source/swagger/swagger.json /usr/local/src/github.com/roserocket/api-docs/source/index.html.md
```

Add this to the markdown:

```
Swagger definition:

* <a href="https://platform.roserocket.com/swagger/swagger.json">https://platform.roserocket.com/swagger/swagger.json</a>
```
