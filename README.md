# Which is the fastest?

[![Build Status](https://travis-ci.com/the-benchmarker/web-frameworks.svg?branch=master)](https://travis-ci.com/the-benchmarker/web-frameworks)
[![Join the chat at https://gitter.im/which_is_the_fastest/Lobby](https://badges.gitter.im/which_is_the_fastest/Lobby.svg)](https://gitter.im/which_is_the_fastest/Lobby)

This project aims to be a load benchmarking suite, no more, no less

> Measuring response times (routing times) for each framework (middleware).


<div align="center">
  :warning::warning::warning::warning::warning::warning::warning::warning:
</div>

<div align="center">Results are not <b>production-ready</b> <i>yet</i></div>

<div align="center">
  :warning::warning::warning::warning::warning::warning::warning::warning:
</div>

### Additional purposes :

+ Helping decide beetween languages, depending on use case
+ Learning languages, best practices, devops culture ...
+ Having fun :heart:

## Requirements

+ [Crystal](https://crystal-lang.org) as `built-in` tools are made in this language
+ [Docker](https://www.docker.com) as **frameworks** are `isolated` into _containers_

:warning: `docker` is used for **development** purpose, `production` results will be computed on [DigitalOcean](https://www.digitalocean.com) :warning:

## Usage

+ Install all dependencies

~~~sh
shards install
~~~

+ Build internal tools

~~~sh
shards build
~~~

+ Build containers

> jobs are either languages (example : crystal) or frameworks (example : router.cr)

~~~sh
bin/neph [job1] [job2] [job3] ...
~~~

+ Start the benchmark ....

> tools is a list of language / framework to challenge (example : ruby kemal amber go python)

~~~sh
bin/benchmarker [tools]
~~~

## Results

<!-- Result from here -->
Last update: 2019-01-02
```
OS: Linux (version: 4.19.12-200.fc28.x86_64, arch: x86_64)
CPU Cores: 8
```

### Latency


#### Ranking (top 5)


:one: nickel (rust)


:two: roda (ruby)


:three: rack-routing (ruby)


:four: iron (rust)


:five: laravel (php)


#### Full table

| Language (Runtime) | Framework (Middleware) | Average | 50th percentile | 90th percentile | 99th percentile | 99.9th percentile | Standard deviation |
|---------------------------|---------------------------|----------------:|----------------:|----------------:|----------------:|----------------:|----------------:|
| rust (1.31) | [nickel](http://nickel-org.github.io) (0.10) | 0.06 ms | 0.07 ms | 0.09 ms | 0.12 ms | 2.34 ms | 27.00 | 
| ruby (2.6) | [roda](http://roda.jeremyevans.net) (3.15) | 3.23 ms | 0.16 ms | 12.10 ms | 29.43 ms | 75.45 ms | 6556.67 | 
| ruby (2.6) | [rack-routing](http://github.com/georgeu2000/rack-routing) (0.0) | 3.83 ms | 0.17 ms | 15.32 ms | 35.64 ms | 93.55 ms | 8064.33 | 
| rust (1.31) | [iron](http://ironframework.io) (0.6) | 0.31 ms | 0.30 ms | 0.51 ms | 0.78 ms | 14.14 ms | 203.33 | 
| php (7.2) | [laravel](http://laravel.com) (5.7) | 104.87 ms | 0.31 ms | 264.18 ms | 1834.47 ms | 6846.71 ms | 391253.67 | 
| ruby (2.6) | [hanami](http://hanamirb.org) (1.3) | 6.45 ms | 0.31 ms | 24.72 ms | 51.04 ms | 130.08 ms | 12196.33 | 
| php (7.2) | [symfony](http://symfony.com) (4.2) | 97.99 ms | 0.31 ms | 202.58 ms | 2188.66 ms | 6832.99 ms | 386968.33 | 
| ruby (2.6) | [flame](http://github.com/AlexWayfer/flame) (4.18) | 6.34 ms | 0.32 ms | 22.46 ms | 48.18 ms | 110.84 ms | 11269.33 | 
| php (7.2) | [lumen](http://lumen.laravel.com) (5.7) | 150.49 ms | 0.33 ms | 232.64 ms | 3665.25 ms | 6788.15 ms | 592027.00 | 
| php (7.2) | [zend-framework](http://framework.zend.com) (3.0) | 185.89 ms | 0.33 ms | 395.57 ms | 3955.31 ms | 7094.76 ms | 660956.67 | 
| php (7.2) | [zend-expressive](http://zendframework.github.io/zend-expressive) (3.0) | 174.11 ms | 0.33 ms | 338.90 ms | 3705.72 ms | 6798.73 ms | 628484.33 | 
| php (7.2) | [slim](http://slimframework.com) (3.11) | 122.86 ms | 0.33 ms | 197.93 ms | 2982.30 ms | 6797.09 ms | 495247.33 | 
| ruby (2.6) | [sinatra](http://sinatrarb.com) (2.0) | 8.63 ms | 0.45 ms | 29.48 ms | 60.87 ms | 136.92 ms | 14498.00 | 
| rust (nightly) | [rocket](http://rocket.rs) (0.4) | 68.00 ms | 1.31 ms | 2.85 ms | 2447.71 ms | 6592.94 ms | 468034.67 | 
| python (3.7) | [japronto](http://github.com/squeaky-pl/japronto) (0.1) | 2.77 ms | 2.03 ms | 5.86 ms | 12.38 ms | 34.16 ms | 2674.33 | 
| rust (1.31) | [actix-web](http://actix.rs) (0.7) | 3.04 ms | 2.05 ms | 6.49 ms | 15.92 ms | 121.78 ms | 3940.00 | 
| c (11) | [agoo-c](http://github.com/ohler55/agoo-c) (0.3) | 2.33 ms | 2.25 ms | 3.91 ms | 7.99 ms | 31.67 ms | 1655.33 | 
| go (1.11) | [fasthttprouter](http://godoc.org/github.com/buaazp/fasthttprouter) (0.1) | 3.33 ms | 2.71 ms | 5.64 ms | 10.49 ms | 39.54 ms | 2211.33 | 
| python (3.6) | [vibora](http://vibora.io) (0.0) | 3.55 ms | 2.88 ms | 7.52 ms | 13.99 ms | 37.04 ms | 3083.67 | 
| cpp (11.0) | [evhtp](http://github.com/criticalstack/libevhtp) (1.2) | 2.93 ms | 2.88 ms | 5.07 ms | 6.84 ms | 22.67 ms | 1592.00 | 
| rust (1.31) | [gotham](http://gotham.rs) (0.3) | 3.18 ms | 3.06 ms | 4.63 ms | 7.90 ms | 82.74 ms | 2111.67 | 
| crystal (0.27) | [onyx](http://github.com/onyxframework/rest) (0.5) | 3.58 ms | 3.28 ms | 6.28 ms | 12.24 ms | 28.26 ms | 2461.67 | 
| crystal (0.27) | [spider-gazelle](http://spider-gazelle.net) (1.2) | 3.87 ms | 3.33 ms | 7.39 ms | 14.09 ms | 33.80 ms | 2870.33 | 
| ruby (2.6) | [rails](http://rubyonrails.org) (5.2) | 37.50 ms | 3.35 ms | 126.44 ms | 339.52 ms | 915.00 ms | 72341.33 | 
| nim (0.19) | [jester](http://github.com/dom96/jester) (0.4) | 4.02 ms | 3.40 ms | 6.77 ms | 11.57 ms | 49.34 ms | 2249.33 | 
| ruby (2.6) | [agoo](http://github.com/ohler55/agoo) (2.5) | 5.49 ms | 3.81 ms | 9.47 ms | 54.24 ms | 112.88 ms | 9094.00 | 
| c (99) | [kore](http://kore.io) (3.1) | 4.42 ms | 4.36 ms | 7.34 ms | 9.13 ms | 24.49 ms | 2239.00 | 
| csharp (7.3) | [aspnetcore](http://docs.microsoft.com/en-us/aspnet/index) (2.1) | 5.33 ms | 4.70 ms | 7.89 ms | 15.03 ms | 284.53 ms | 5706.67 | 
| go (1.11) | [muxie](http://godoc.org/github.com/kataras/muxie) (1.0) | 5.62 ms | 4.72 ms | 9.43 ms | 18.54 ms | 166.86 ms | 4724.67 | 
| go (1.11) | [chi](http://github.com/go-chi/chi) (3.3) | 5.95 ms | 4.87 ms | 10.05 ms | 19.63 ms | 224.20 ms | 5095.67 | 
| go (1.11) | [iris](http://iris-go.com) (11.1) | 6.03 ms | 4.98 ms | 9.95 ms | 20.13 ms | 108.88 ms | 4549.67 | 
| python (3.7) | [falcon](http://falconframework.org) (1.4) | 7.40 ms | 5.00 ms | 12.58 ms | 25.50 ms | 212.63 ms | 7117.33 | 
| nim (0.19) | [mofuw](http://github.com/2vg/mofuw) (2.0) | 6.43 ms | 5.00 ms | 9.68 ms | 28.98 ms | 124.73 ms | 4975.33 | 
| java (8) | [act](http://actframework.org) (1.8) | 5.95 ms | 5.07 ms | 9.74 ms | 20.15 ms | 173.95 ms | 4760.33 | 
| go (1.11) | [gin](http://gin-gonic.github.io/gin) (1.3) | 7.38 ms | 5.18 ms | 10.94 ms | 28.00 ms | 420.64 ms | 16226.33 | 
| go (1.11) | [echo](http://echo.labstack.com) (3.3) | 6.51 ms | 5.28 ms | 11.13 ms | 22.27 ms | 161.63 ms | 4934.33 | 
| go (1.11) | [beego](http://beego.me) (1.11) | 6.83 ms | 5.42 ms | 11.06 ms | 23.22 ms | 238.79 ms | 8082.67 | 
| go (1.11) | [gorilla-mux](http://www.gorillatoolkit.org/pkg/mux) (1.6) | 7.03 ms | 5.49 ms | 11.36 ms | 24.08 ms | 290.91 ms | 9340.33 | 
| node (11.1) | [restana](http://github.com/jkyberneees/ana) (2.3) | 8.50 ms | 6.09 ms | 15.42 ms | 36.56 ms | 307.82 ms | 10499.67 | 
| scala (2.12) | [akkahttp](http://akka.io) (10.1) | 157.37 ms | 6.55 ms | 123.53 ms | 3798.20 ms | 7177.58 ms | 640785.33 | 
| node (11.1) | [polka](http://github.com/lukeed/polka) (0.5) | 9.15 ms | 6.64 ms | 15.73 ms | 38.55 ms | 396.12 ms | 13957.33 | 
| python (3.7) | [bottle](http://bottlepy.org) (0.12) | 8.81 ms | 6.83 ms | 16.82 ms | 31.42 ms | 170.92 ms | 7326.33 | 
| node (11.1) | [rayo](http://rayo.js.org) (1.2) | 9.31 ms | 7.02 ms | 16.96 ms | 38.78 ms | 287.79 ms | 10391.00 | 
| go (1.11) | [gf](http://gfer.me) (1.3) | 9.10 ms | 7.99 ms | 13.29 ms | 29.41 ms | 357.26 ms | 10313.33 | 
| node (11.1) | [fastify](http://fastify.io) (1.13) | 10.49 ms | 8.11 ms | 18.00 ms | 41.45 ms | 368.11 ms | 11868.00 | 
| node (11.1) | [foxify](http://foxify.js.org) (0.10) | 12.72 ms | 9.40 ms | 21.21 ms | 52.98 ms | 476.49 ms | 17540.67 | 
| node (11.1) | [koa](http://koajs.com) (2.6) | 14.09 ms | 10.37 ms | 23.95 ms | 54.69 ms | 469.11 ms | 17614.33 | 
| swift (4.2) | [vapor](http://vapor.codes) (3.0) | 12.87 ms | 10.66 ms | 18.49 ms | 30.89 ms | 624.53 ms | 20617.33 | 
| swift (4.2) | [perfect](http://perfect.org) (3.0) | 10.78 ms | 10.70 ms | 12.50 ms | 14.38 ms | 223.15 ms | 6418.67 | 
| scala (2.12) | [http4s](http://http4s.org) (0.18) | 48.13 ms | 11.56 ms | 25.03 ms | 1231.38 ms | 2609.48 ms | 217691.33 | 
| node (11.1) | [express](http://expressjs.com) (4.16) | 18.58 ms | 14.11 ms | 30.10 ms | 71.26 ms | 618.28 ms | 25047.67 | 
| node (11.1) | [restify](http://restify.com) (7.2) | 18.16 ms | 14.53 ms | 31.04 ms | 59.22 ms | 410.31 ms | 15905.67 | 
| python (3.7) | [aiohttp](http://aiohttp.readthedocs.io) (3.5) | 17.65 ms | 16.04 ms | 29.22 ms | 41.74 ms | 78.24 ms | 8335.00 | 
| crystal (0.27) | [router.cr](http://github.com/tbrand/router.cr) (0.2) | 22.13 ms | 19.75 ms | 33.51 ms | 43.75 ms | 245.02 ms | 8765.33 | 
| swift (4.2) | [kitura](http://kitura.io) (2.5) | 23.83 ms | 21.17 ms | 35.80 ms | 49.59 ms | 165.32 ms | 8772.00 | 
| crystal (0.27) | [kemal](http://kemalcr.com) (0.25) | 28.29 ms | 21.48 ms | 37.55 ms | 184.22 ms | 534.63 ms | 29637.67 | 
| python (3.7) | [flask](http://flask.pocoo.org) (1.0) | 25.84 ms | 22.90 ms | 37.99 ms | 63.24 ms | 389.99 ms | 13618.33 | 
| crystal (0.27) | [raze](http://razecr.com) (0.3) | 26.27 ms | 26.00 ms | 35.35 ms | 44.71 ms | 315.17 ms | 11348.00 | 
| node (11.1) | [hapi](http://hapijs.com) (17.7) | 38.90 ms | 27.04 ms | 49.53 ms | 416.07 ms | 1321.57 ms | 75853.67 | 
| python (3.7) | [sanic](http://github.com/huge-success/sanic) (18.12) | 39.60 ms | 31.30 ms | 77.01 ms | 138.48 ms | 290.28 ms | 27813.33 | 
| crystal (0.27) | [orion](http://github.com/obsidian/orion) (1.6) | 34.83 ms | 31.46 ms | 43.92 ms | 67.44 ms | 353.51 ms | 14248.67 | 
| crystal (0.27) | [lucky](http://luckyframework.org) (0.11) | 32.20 ms | 32.13 ms | 39.40 ms | 49.23 ms | 396.05 ms | 10911.67 | 
| crystal (0.27) | [amber](http://amberframework.org) (0.11) | 34.80 ms | 34.66 ms | 41.89 ms | 49.01 ms | 317.46 ms | 9426.00 | 
| python (3.7) | [quart](http://pgjones.gitlab.io/quart) (0.7) | 46.17 ms | 35.64 ms | 90.36 ms | 140.48 ms | 207.38 ms | 29869.00 | 
| python (3.7) | [django](http://djangoproject.com) (2.1) | 45.02 ms | 37.25 ms | 74.63 ms | 113.53 ms | 372.59 ms | 22659.33 | 
| python (3.7) | [tornado](http://tornadoweb.org) (5.1) | 72.41 ms | 69.90 ms | 93.86 ms | 127.87 ms | 386.71 ms | 19692.33 | 

### Requests per seconds


#### Ranking (top 5)


:one: (agoo-c) (c)


:two: (japronto) (python)


:three: (actix-web) (rust)


:four: (vibora) (python)


:five: (evhtp) (cpp)


#### Full table

| Language (Runtime) | Framework (Middleware) | Requests / s | Throughput |
|---------------------------|---------------------------|----------------:|---------:|
| c (11) | [agoo-c](http://github.com/ohler55/agoo-c) (0.3) | 416858.33 | 241.12 MB |
| python (3.7) | [japronto](http://github.com/squeaky-pl/japronto) (0.1) | 372575.00 | 445.74 MB |
| rust (1.31) | [actix-web](http://actix.rs) (0.7) | 358135.33 | 407.22 MB |
| python (3.6) | [vibora](http://vibora.io) (0.0) | 303355.00 | 344.46 MB |
| cpp (11.0) | [evhtp](http://github.com/criticalstack/libevhtp) (1.2) | 299117.67 | 290.44 MB |
| go (1.11) | [fasthttprouter](http://godoc.org/github.com/buaazp/fasthttprouter) (0.1) | 279744.00 | 450.50 MB |
| rust (1.31) | [gotham](http://gotham.rs) (0.3) | 274939.00 | 561.89 MB |
| crystal (0.27) | [onyx](http://github.com/onyxframework/rest) (0.5) | 265853.33 | 250.13 MB |
| nim (0.19) | [jester](http://github.com/dom96/jester) (0.4) | 259596.33 | 521.48 MB |
| crystal (0.27) | [spider-gazelle](http://spider-gazelle.net) (1.2) | 258000.00 | 276.26 MB |
| java (8) | [act](http://actframework.org) (1.8) | 243226.33 | 474.95 MB |
| ruby (2.6) | [agoo](http://github.com/ohler55/agoo) (2.5) | 233766.00 | 135.10 MB |
| rust (1.31) | [iron](http://ironframework.io) (0.6) | 188150.67 | 237.15 MB |
| csharp (7.3) | [aspnetcore](http://docs.microsoft.com/en-us/aspnet/index) (2.1) | 179871.00 | 293.18 MB |
| go (1.11) | [muxie](http://godoc.org/github.com/kataras/muxie) (1.0) | 174717.00 | 234.27 MB |
| go (1.11) | [chi](http://github.com/go-chi/chi) (3.3) | 164267.67 | 219.75 MB |
| go (1.11) | [iris](http://iris-go.com) (11.1) | 163027.33 | 218.24 MB |
| nim (0.19) | [mofuw](http://github.com/2vg/mofuw) (2.0) | 162392.00 | 285.15 MB |
| go (1.11) | [gin](http://gin-gonic.github.io/gin) (1.3) | 153896.33 | 270.14 MB |
| go (1.11) | [echo](http://echo.labstack.com) (3.3) | 151286.33 | 265.63 MB |
| go (1.11) | [beego](http://beego.me) (1.11) | 149635.00 | 201.29 MB |
| go (1.11) | [gorilla-mux](http://www.gorillatoolkit.org/pkg/mux) (1.6) | 145978.67 | 195.22 MB |
| python (3.7) | [falcon](http://falconframework.org) (1.4) | 138202.00 | 355.41 MB |
| rust (1.31) | [nickel](http://nickel-org.github.io) (0.10) | 134165.67 | 265.15 MB |
| node (11.1) | [restana](http://github.com/jkyberneees/ana) (2.3) | 131438.00 | 196.96 MB |
| node (11.1) | [polka](http://github.com/lukeed/polka) (0.5) | 125517.33 | 188.13 MB |
| node (11.1) | [rayo](http://rayo.js.org) (1.2) | 119253.33 | 178.53 MB |
| python (3.7) | [bottle](http://bottlepy.org) (0.12) | 118718.00 | 292.63 MB |
| go (1.11) | [gf](http://gfer.me) (1.3) | 112862.33 | 171.23 MB |
| node (11.1) | [fastify](http://fastify.io) (1.13) | 108247.67 | 261.55 MB |
| swift (4.2) | [perfect](http://perfect.org) (3.0) | 94021.67 | 88.29 MB |
| node (11.1) | [foxify](http://foxify.js.org) (0.10) | 90103.00 | 189.29 MB |
| swift (4.2) | [vapor](http://vapor.codes) (3.0) | 81680.33 | 137.57 MB |
| scala (2.12) | [http4s](http://http4s.org) (0.18) | 80336.00 | 140.38 MB |
| node (11.1) | [koa](http://koajs.com) (2.6) | 80242.00 | 169.69 MB |
| php (7.2) | [slim](http://slimframework.com) (3.11) | 71204.00 | 352.58 MB |
| php (7.2) | [symfony](http://symfony.com) (4.2) | 67333.33 | 333.65 MB |
| c (99) | [kore](http://kore.io) (3.1) | 67332.67 | 182.59 MB |
| php (7.2) | [lumen](http://lumen.laravel.com) (5.7) | 66281.67 | 343.90 MB |
| rust (nightly) | [rocket](http://rocket.rs) (0.4) | 65554.00 | 103.21 MB |
| scala (2.12) | [akkahttp](http://akka.io) (10.1) | 63840.00 | 137.38 MB |
| node (11.1) | [express](http://expressjs.com) (4.16) | 60453.33 | 147.52 MB |
| node (11.1) | [restify](http://restify.com) (7.2) | 58658.00 | 102.58 MB |
| php (7.2) | [zend-expressive](http://zendframework.github.io/zend-expressive) (3.0) | 56891.33 | 286.34 MB |
| python (3.7) | [aiohttp](http://aiohttp.readthedocs.io) (3.5) | 56673.33 | 128.57 MB |
| php (7.2) | [laravel](http://laravel.com) (5.7) | 54552.00 | 284.06 MB |
| php (7.2) | [zend-framework](http://framework.zend.com) (3.0) | 52906.67 | 263.91 MB |
| crystal (0.27) | [router.cr](http://github.com/tbrand/router.cr) (0.2) | 44834.67 | 42.05 MB |
| swift (4.2) | [kitura](http://kitura.io) (2.5) | 41887.67 | 77.65 MB |
| crystal (0.27) | [kemal](http://kemalcr.com) (0.25) | 40237.67 | 65.57 MB |
| ruby (2.6) | [roda](http://roda.jeremyevans.net) (3.15) | 39841.67 | 37.92 MB |
| python (3.7) | [flask](http://flask.pocoo.org) (1.0) | 38556.00 | 95.01 MB |
| crystal (0.27) | [raze](http://razecr.com) (0.3) | 38000.33 | 35.63 MB |
| ruby (2.6) | [rack-routing](http://github.com/georgeu2000/rack-routing) (0.0) | 33627.67 | 19.44 MB |
| node (11.1) | [hapi](http://hapijs.com) (17.7) | 33277.33 | 85.92 MB |
| crystal (0.27) | [lucky](http://luckyframework.org) (0.11) | 31306.00 | 38.31 MB |
| crystal (0.27) | [amber](http://amberframework.org) (0.11) | 29135.67 | 53.16 MB |
| crystal (0.27) | [orion](http://github.com/obsidian/orion) (1.6) | 28642.33 | 46.66 MB |
| python (3.7) | [sanic](http://github.com/huge-success/sanic) (18.12) | 27022.33 | 48.12 MB |
| python (3.7) | [quart](http://pgjones.gitlab.io/quart) (0.7) | 23120.67 | 46.18 MB |
| python (3.7) | [django](http://djangoproject.com) (2.1) | 22215.00 | 64.45 MB |
| ruby (2.6) | [flame](http://github.com/AlexWayfer/flame) (4.18) | 20273.00 | 11.68 MB |
| ruby (2.6) | [hanami](http://hanamirb.org) (1.3) | 19825.00 | 149.82 MB |
| ruby (2.6) | [sinatra](http://sinatrarb.com) (2.0) | 14912.00 | 38.64 MB |
| python (3.7) | [tornado](http://tornadoweb.org) (5.1) | 13484.33 | 39.66 MB |
| ruby (2.6) | [rails](http://rubyonrails.org) (5.2) | 3411.67 | 10.44 MB |
<!-- Result till here -->

## How to contribute ?

In any way you want ...

+ Request a framework addition
+ Report a bug (on any implementation)
+ Suggest an idea
+ ...

Any kind of idea is :heart:

## Contributors

- [Taichiro Suzuki](https://github.com/tbrand) - Author, maintainer
- [OvermindDL1](https://github.com/OvermindDL1) - Maintainer
- [Marwan Rabbâa](https://github.com/waghanza) - Mainainer
