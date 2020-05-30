# Winston TCP [![version][npm-version]][npm-url] [![License][license-image]][license-url]

> TCP transport for [Winston](https://github.com/winstonjs/winston)

## Install

```bash
npm install --only=production --save winston-tcp-infinite
```

## API

```js
import Transport from 'winston-tcp'

let logger = new (winston.Logger)({
  transports: [
    new (Transport)({
      host: '127.0.0.1',
      port: 1337,
      json: true,
      timestamp: true
    })
  ]
})

logger.log('info', 'foo')
```

or simply:

```js
import winston from 'winston'
import Transport from 'winston-tcp'

winston.add(new Transport({
  host: '127.0.0.1',
  port: 1337
}))

winston.info('foo')
```

## Options

Name                | Description                                                                   | Default
------------------- | ----------------------------------------------------------------------------- | -------
`host`              | The host to connect to                                                        | none
`port`              | The server port to connect to                                                 | none
`reconnectInterval` | Time to pause between disconnect and reconnect (in ms)                        | `1000`
`bufferLength`      | Number of messages to buffer while disconnected, set to `false` for unlimited | `10000`
`json`              | If `true`, messages will be logged as JSON                                    | `false`
`timestamp`         | flag indicating if we should prepend output with timestamps                   | `false`
`formatter`         | a custom formatter (see Winston docs)                                         | none
`reconnectAttempts` | Reconnection apttemp count (0 is infinite)                                    | 100


---
> License: [ISC]
> Github: [@createmain](https://github.com/createmain)  · 

[npm-url]: https://www.npmjs.com/package/winston-tcp-infinite
[npm-version]: https://img.shields.io/npm/v/winston-tcp-infinite.svg?style=flat-square
[npm-downloads]: https://img.shields.io/npm/dm/winston-tcp-infinite.svg?style=flat-square
