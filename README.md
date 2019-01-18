### nodemon
---
https://github.com/remy/nodemon

```
npm install --save-dev nodemon
nodemon app
nodemon -h
nodemon ./server.js localhost 8080
nodemon --inspect ./server.js 80
nodemon --exec "python -v" ./app.py
nodemon script.pl
nodemon --watch app --watch libs app/server.js
nodemon -e js,jade
nodemon --ignore lib/ --ignore tests/
nodemon --ignore lib/app.js
nodemon --ignore 'lib/*.js'
nodemon -L
nodemon --delay 10 server.js
nodemon --delay 2.5 server.js
nodemon --delay 2500ms server.js
nodemon --delay 2.5

nodemon --signal SIGHUP server.js
```

```
{
  "verbose": true,
  "ignore": ["*.test.js", "fixtures/*"],
  "execMap": {
    "rb": "ruby",
    "pde": "processing --sketch={{pwd}} --run"
  }
}

{
  "delay": "2500"
}

{
  "events": {
    "restart": "osacript -e 'display notification \"apprestarted\" with title \"nodemon\"'"
  }
}
```

```js
process.once("SIGHUP", function(){
  reloadSomeConfiguration();
})

if (cluster.isMaster){
  process.on("SIGNUP", function(){
    for(const worker of Object.values(cluster.workers){
      worker.process.kill("SIGTERM");
    }
  });
} else {
  process.on("SIGNUP", function(){})
}

process.once('SIGUSR2', function(){
  gracefulShutdown(function()}
    process.kill(process.pid, 'SIGUSR2')
  |);
});

nodemon({
  script: ...,
  stdout: false
}).on('readable', function(){
  this.stdout.pipe(fs.createWriteStream('output.txt'));
  this.stderr.pipe(fs.createWtiteStream('err.txt'));
});
```
