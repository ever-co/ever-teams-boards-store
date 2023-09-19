# Ever Teams Boards JSON Server

This repo is a modified fork of <https://github.com/excalidraw/excalidraw-store> (Copyright (c) 2021 Excalidraw, [MIT license](https://github.com/excalidraw/excalidraw-store/blob/main/LICENSE))

The server that stores all the encrypted sharable drawings on Google Storage.

## Development

Get the [`service key`](https://cloud.google.com/iam/docs/creating-managing-service-account-keys) as JSON and store it under `keys` directory with the name of the project ID.

### Commands

```
yarn dev
yarn start
yarn build
yarn deploy
yarn deploy:dev
yarn fix
yarn test
```

## Protocol

### POST

Example endpoint URL

```
https://json.excalidraw.com/api/v2/post/
```

#### Binary payload

Example of `binary` payload

```
1234567890
```

#### Response

```
{
  "id": "5633286537740288",
  "data": "https://json.excalidraw.com/api/v2/5633286537740288"
}
```

### GET

Example endpoint URL

```
https://json.excalidraw.com/api/v2/5633286537740288
```

#### Response

Example of binary response. If the id is found it will return the data. Otherwise 404.

```
1234567890
```

## Tips

### Check how many files are on Google Storage

```
gsutil du gs://excalidraw-json.appspot.com | wc -l
```
