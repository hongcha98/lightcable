# lightcable

lightweight websocket channel server

[![Build Status](https://github.com/a-wing/lightcable/workflows/ci/badge.svg)](https://github.com/a-wing/lightcable/actions?query=workflow%3Aci)
[![codecov](https://codecov.io/gh/a-wing/lightcable/branch/master/graph/badge.svg)](https://codecov.io/gh/a-wing/lightcable)
[![Go Report Card](https://goreportcard.com/badge/github.com/a-wing/lightcable)](https://goreportcard.com/report/github.com/a-wing/lightcable)
[![Go Reference](https://pkg.go.dev/badge/github.com/a-wing/lightcable.svg)](https://pkg.go.dev/github.com/a-wing/lightcable)
[![GitHub release](https://img.shields.io/github/tag/a-wing/lightcable.svg?label=release)](https://github.com/a-wing/lightcable/releases)
[![license](https://img.shields.io/github/license/a-wing/lightcable.svg?maxAge=2592000)](https://github.com/a-wing/lightcable/blob/master/LICENSE)

## Compile

* golang >= 1.13

### Application scenario

* A simple Websocket broadcast room
* WebRTC signaling server
* Replace [socket.io](https://socket.io/)  (Special case: client only join a room)
* Wx APP sdk and webview communication (微信小程序下和 webview 通信)

### As a Application

```bash
go get -u github.com/a-wing/lightcable/cmd/lightcable

# Listen port: 8088
lightcable -l localhost:8088
```

### URL

```bash
ws://localhost:8080/{roomName}
```

### broadcast server demo

Server

```bash
lightcable
```

Room: `xxx`, Client: `1`

```bash
websocat --linemode-strip-newlines 'ws://localhost:8080/xxx'
```

Room: `xxx`, Client: `2`

```bash
websocat --linemode-strip-newlines 'ws://localhost:8080/xxx'
```

Room: `xxx`, Client: `3`

```bash
websocat --linemode-strip-newlines 'ws://localhost:8080/xxx'
```

Room: `xxx-2`, Client: `4`

```bash
websocat --linemode-strip-newlines 'ws://localhost:8080/xxx-2'
```

