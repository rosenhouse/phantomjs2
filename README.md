A Dockerfile to build [PhantomJS](https://github.com/ariya/phantomjs) 2.0.0 for Linux from source.

There is an [Automated Build on hub.docker.com](https://registry.hub.docker.com/u/rosenhouse/phantomjs2/), so getting the image is easy:
```bash
docker pull rosenhouse/phantomjs2:latest
```

There are a couple ways to use it:

## Option 1: Run it from inside a Docker container

```bash
docker run rosenhouse/phantomjs2 phantomjs -v
```


## Option 2: Extract the binary so you can run it without Docker

1. Install [run-time dependencies](https://github.com/rosenhouse/phantomjs2/blob/master/Dockerfile#L10)

  ```bash
  apt-get install -y libicu-dev libfontconfig1-dev libjpeg-dev libfreetype6
  ```

2. Extract binary

  ```bash
  docker pull rosenhouse/phantomjs2:latest
  docker run -name temp rosenhouse/phantomjs2
  docker cp temp:phantomjs/phantomjs-2.0.0/bin/phantomjs ~/phantomjs
  ```

3. Run

  ```bash
  ~/phantomjs -v
  2.0.0
  ```
     
