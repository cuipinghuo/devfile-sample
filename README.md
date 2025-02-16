# nodejs-starter

This is a sample starter project that provides you with a basic Express app and a sample test in a `/test` sub directory. This sample project uses `Express v4.18.x` and enables health checking and application metrics out of the box. You can override or enhance the following endpoints by configuring your own health checks in your application.

## Health checking

Health-checking enables the cloud platform to determine the `readiness` and `liveness` of your application.

These endpoints will be available for you to use:

- Readiness endpoint: http://localhost:3000/ready
- Liveness endpoint: http://localhost:3000/live

## Application metrics

The [prom-client](https://www.npmjs.com/package/prom-client) module will collect a wide range of resource-centric (CPU, memory) and application-centric (HTTP request responsiveness) metrics from your application, and then expose them as multi-dimensional time-series data through an application endpoint for Prometheus to scrape and aggregate.

This endpoint will be available for you to use:

- Metrics endpoint: http://localhost:3000/metrics

## Dockerfile

For constructing node_modules in the first build stage of Dockerfile, we use `npm ci` to avoid file permissions error. For npm versions greater than 6, `npm install` opens `package-lock.json` in write mode, which is restricted to read mode by ubi images and as a result, node_modules construction ends up with a file permissions error.

## License

This stack is licensed under the [EPL 2.0](./LICENSE) license.

## Bump to trigger a new build
