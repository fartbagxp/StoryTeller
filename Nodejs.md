# Resources

## Package Manager

The package manager for nodejs and a lot of the javascript development
today falls on npm.

This is a list of [resources](https://github.com/sindresorhus/awesome-npm)
for it.

## Nodejs resources

This is a list of [libraries](https://github.com/sindresorhus/awesome-nodejs)
that are awesome for nodejs development.

## Electron resources

This is a list of [resources](https://github.com/sindresorhus/awesome-electron)
for application development using electron.

## Logging

For modules, use [debug](https://www.npmjs.com/package/debug)
For application, use [winston](https://www.npmjs.com/package/winston)

[How to get Logging Right](https://blog.risingstack.com/node-js-logging-tutorial/?utm_source=nodeweekly&utm_medium=email)

## Node Resource Management

If we need a profiler for NodeJS, this looks to be a good resource to use.
[Resource management](https://www.npmjs.com/package/nodegrind)

## Update Node module version

Commit the code, and then do patch command, that will also commit and push.

```js
git add .
git commit -m "Commit message"
git push
npm version patch
```

## Shrinkwrap

Lock down third party library version.

```js
npm shrinkwrap
```

Check in the shrinkwrap file.

## Environment variables

[nconf](https://github.com/indexzero/nconf)

### Vulnerability Checking with Shrinkwrap

[nsp](https://www.npmjs.com/package/nsp)

### Deployment - NodeJS application

[Using Docker to deploy Apache, Nginx, Wordpress and Nodejs containers with Digital Ocean](https://www.youtube.com/watch?v=1OLyXJJPBSA)

[Architecture](http://www.dwmkerr.com/learn-docker-by-building-a-microservice/)

## Load Balancing with Node.JS

This looks like a hot project for load balancing backend NodeJS.
[Load Balancing using PM2](https://www.npmjs.com/package/pm2)

## SSL

```js

var Hapi = require('hapi');
var server = new Hapi.Server();

var fs = require('fs');

var tls = {
  key: fs.readFileSync('/etc/letsencrypt/live/example.com/privkey.pem'),
  cert: fs.readFileSync('/etc/letsencrypt/live/example.com/cert.pem')
};

server.connection({address: '0.0.0.0', port: 443, tls: tls });
server.connection({address: '0.0.0.0', port: 80 });

server.route({
    method: 'GET',
    path: '/',
    handler: function (request, reply) {
        reply('Hello, world!');
    }
});

server.start(function () {
    console.log('Server running');
});
```

## HTTP to HTTPS redirection

```js
if (request.headers['x-forwarded-proto'] === 'http') {
  return reply()
    .redirect('https://' + request.headers.host + request.url.path)
    .code(301);
}
```

## [Fine Tuned Timing](https://blog.tompawlak.org/measure-execution-time-nodejs-javascript)

Use process.hrtime() instead of Date, due to clock drifts.

```js
  var start = new Date();
  var hrstart = process.hrtime();

  setTimeout(function (argument) {
      // execution time simulated with setTimeout function
      var end = new Date() - start,
          hrend = process.hrtime(hrstart);

      console.info("Execution time: %dms", end);
      console.info("Execution time (hr): %ds %dms", hrend[0], hrend[1]/1000000);
  }, 1);
```

Output:

```js
Execution time: 1ms
Execution time (hr): 0s 1.025075ms

Execution time: 3ms
Execution time (hr): 0s 2.875302ms
```
