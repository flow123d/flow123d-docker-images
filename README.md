# Docker images for the project Flow123d
Repository containing Dockerfiles for the project [Flow123d](https://github.com/flow123d/flow123d)

## Images:
  -  [`flow123d/base-env`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/base-env) [![](https://images.microbadger.com/badges/image/flow123d/base-env.svg)](https://microbadger.com/images/flow123d/base-env "analysed by microbadger")
  -  [`flow123d/base`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/base) [![](https://images.microbadger.com/badges/image/flow123d/base.svg)](https://microbadger.com/images/flow123d/base "analysed by microbadger")
  -  [`flow123d/base-build`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/base-build) [![](https://images.microbadger.com/badges/image/flow123d/base-build.svg)](https://microbadger.com/images/flow123d/base-build "analysed by microbadger")
  -  [`flow123d/flow-libs-dev-dbg`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/flow-libs-dev-dbg) [![](https://images.microbadger.com/badges/image/flow123d/flow-libs-dev-dbg.svg)](https://microbadger.com/images/flow123d/flow-libs-dev-dbg "analysed by microbadger")
  -  [`flow123d/flow-libs-dev-rel`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/flow-libs-dev-rel) [![](https://images.microbadger.com/badges/image/flow123d/flow-libs-dev-rel.svg)](https://microbadger.com/images/flow123d/flow-libs-dev-rel "analysed by microbadger")
  -  [`flow123d/install`](https://github.com/janhybs/flow123d-docker-images/tree/master/dockerfiles/install) [![](https://images.microbadger.com/badges/image/flow123d/install.svg)](https://microbadger.com/images/flow123d/install "analysed by microbadger")

## Inheritance of the images:
  - `ubuntu:16.04`
    - `flow123d/base-env`
    - `flow123d/base`
      - `flow123d/base-build`
        - `flow123d/flow-libs-dev-dbg`
        - `flow123d/flow-libs-dev-rel`
      - `flow123d/install`
