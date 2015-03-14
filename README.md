A Dockerfile to build [PhantomJS](https://github.com/ariya/phantomjs) 2.0.0 for Linux from source.

There is a [Trusted build on hub.docker.com](https://registry.hub.docker.com/u/rosenhouse/phantomjs2/)

## To get the pre-built binary from the Trusted Build
```bash
docker pull rosenhouse/phantomjs2
docker run -name temp rosenhouse/phantomjs2
docker cp temp:phantomjs/phantomjs-2.0.0/bin/phantomjs ~/phantomjs
```

## To run the binary
You may need to install some dynamic libraries on your system before `phantomjs` will run:
```bash
sudo apt-get install libfontconfig1-dev libjpeg-dev
```
When in doubt, compare your system against the packages used in the build process at the top of the `Dockerfile`
