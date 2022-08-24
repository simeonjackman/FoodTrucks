SF Food Trucks
===

> San Francisco's finger-licking street food now at your fingertips.

![img](shot.png)

This is a fun application built to accompany the [docker curriculum](http://prakhar.me/docker-curriculum) which is a comprehensive tutorial on getting started with Docker targeted especially at beginners. The app is built with [Flask](http://flask.pocoo.org/) on the backend and [Elasticsearch](http://elastic.co/) is the search engine powering the searches. The front-end is built with [React](http://facebook.github.io/react/) and the beautiful maps are courtesy of [Mapbox](https://www.mapbox.com/).

If you find the design of the website a bit ostentatious, blame [Genius](http://genius.com) for giving me the idea of using this color scheme.  Lastly, the data for the food trucks is made available in the public domain by [SF Data](https://data.sfgov.org/Economy-and-Community/Mobile-Food-Facility-Permit/rqzj-sfat).

#### Docker

There are two different ways of getting the app up and running with Docker. To learn more about how these two differ, check out the [docker curriculum](http://prakhar.me/docker-curriculum).

##### Docker Network
```
$ ./setup-docker.sh
```

##### Docker Compose
```
$ docker-compose up
```

Push the image to SDN's ECR
```
$ aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/j1m4u0k0
$ docker build -t sre-training .
$ docker tag sre-training:latest public.ecr.aws/j1m4u0k0/sre-training:latest
$ docker push public.ecr.aws/j1m4u0k0/sre-training:latest
$ docker push aws_account_id.dkr.ecr.region.amazonaws.com/my-repository:tag
```
