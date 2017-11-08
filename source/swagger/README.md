# Swagger files

To convert from swagger to slate use widdersins
```
$ node /usr/local/src/github.com/Mermade/widdershins/widdershins.js /usr/local/src/github.com/roserocket/api-docs/source/swagger/swagger.json /usr/local/src/github.com/roserocket/api-docs/source/api.html.md
```

Add this to the markdown:
```
Swagger definition:

* <a href="https://platform.roserocket.com/swagger.json">https://platform.roserocket.com/swagger.json</a>
```