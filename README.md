# NextJS with Typescript Starter

This is a minimal setup for NextJS application that work with:

- typescript
- `styled-components`
- Docker

## How to use

### Clone this repo to your machine

```bash
git clone git@github.com:martindavid/nextjs-typescript-starter.git nextjs-app
cd nextjs-app
```

Build it with docker:

```bash
# build
docker build -t nextjs-app .
# or, use multi-stage builds to build a smaller docker image
docker build -t nextjs-app -f ./Dockerfile.multistage .
```

Run it:

```bash
docker run --rm -it \
  -p 3000:3000 \
  -e "API_URL=https://example.com" \
  next-app
```

Deploy it to the cloud with [now](https://zeit.co/now) ([download](https://zeit.co/download))

```bash
now --docker -e API_URL="https://example.com"
```

## The idea behind the example

This example show how to set custom environment variables for your **docker application** at runtime.

The `dockerfile` is the simplest way to run Next.js app in docker, and the size of output image is `173MB`. However, for an even smaller build, you can do multi-stage builds with `dockerfile.multistage`. The size of output image is `85MB`.

You can check the [Example Dockerfile for your own Node.js project](https://github.com/mhart/alpine-node/tree/43ca9e4bc97af3b1f124d27a2cee002d5f7d1b32#example-dockerfile-for-your-own-nodejs-project) section in [mhart/alpine-node](https://github.com/mhart/alpine-node) for more details.
