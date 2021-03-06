# FaceApi Express

A minimal express web app that quickly make the face-api works in nodejs env.

## Why?

The official face-api.js examples is written in ts and requires some extra effort to make it into a standalone service.

## To run

First install dependencies
```
yarn
```

Secondly drag the `weight` folder from face-api.js and named to `models` to root folder.

Thirdly start the service
```
yarn start
```

## To make it a service

You may want to take a look at pm2

```
npm install pm2 -g
pm2 start index.js --name Face-Api-Express
```

## How?

By default the server runs at port `9000` and exposes `/detect` for receiving a json object like following

```
{
    "image":"/9j/4AAQSkZJRgABA....the"
}
```

We also have `/detect-matches` for detecting matching faces, it accepts following request 

```
{
    "image":"/9j/4AAQSkZJRgABA....the" // The source image
    "faces": [
        {
            "name":"Tony",
            "image":"/9j/4AAQSkZJRgABA....the" // The face image
        }
    ]
}
```

It is easy to play with `req.body.image` if you want to handle your own logic. Just call `util.detect` and pass in the buffer of the image.