# Docker Web Server

## Introduction
LEMP environment built on  Nginx with PHP5-FPM (Zend OPcache + Xdebug) and MySQL (w/ Symfony3 support). Optional: Node, MongoDB, Memcached, Redis, Elasticsearch, Logstash

=======================

## Requirements

1. [Docker](https://docs.docker.com/engine/installation/)

# Installation

1. Clone this repository:
```bash
$ git clone git@github.com:rakauchuk/docker-web-server.git
```
2. Put your Symfony application into `www` folder
3. Add `symfony.dev` in your `/etc/hosts` file
4. Builds, start and attach to containers:
```bash
$ docker-compose up
```

_Note:_  Now, you can visit your Symfony application on the following URL:
– Applicathion on `http://symfony.dev`
– Kibana on `http://symfony.dev:81` (it is a tool to visualize Nginx & application logs)

Enjoy!

## License

The MIT License (MIT)

Copyright (c) 2016 Kirill Rakauchuk

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
