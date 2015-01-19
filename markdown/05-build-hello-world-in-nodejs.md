# Build Hello World in NodeJS

---

Running node:

```bash
docker run -it --rm --name hello-world-node node:latest node
```

---

```bash
mkdir helloworld

touch helloworld/index.js
```

```javascript
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!')
});

var server = app.listen(3000, function () {
  var host = server.address().address;
  var port = server.address().port;
  console.log('Example app listening at http://%s:%s', host, port);
});
```

---

```bash
touch helloworld/Dockerfile
```

```Dockerfile
FROM       node:latest
MAINTAINER Mohd Faiz Hasim

ENV APP_PATH /user/src/myapp

EXPOSE 3000

ADD index.js $APP_PATH/index.js
RUN npm install --save express

WORKDIR $APP_PATH

CMD node index.js

```

---

```bash
docker build -t faizhasim/helloworld helloworld/
```

---

```bash
docker run -p=80:3000 -ti --rm --name hello-world-node faizhasim/helloworld
```

