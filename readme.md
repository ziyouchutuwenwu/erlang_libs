# 收集 erlang 下面的常用的比较好的库

## project creator

```sh
github.com/ziyouchutuwenwu/rebar3-creator
```

## rebar3_erlydtl_plugin

```sh
github.com/tsloughter/rebar3_erlydtl_plugin
```

## http client

```sh
github.com/cmullaparthi/ibrowse
```

用法

```erlang
form_post_demo()->
  ibrowse:start(),
  Url = "http://127.0.0.1:8100",
  ReqHeaders = [{<<"Content-Type">>, <<"application/x-www-form-urlencoded">>}],
  ReqBody = << "{\"voltage\": \"111\" }" >>,
  ibrowse:send_req(Url, ReqHeaders, get, ReqBody).

json_post_demo()->
  ibrowse:start(),
  Url = "http://127.0.0.1:8100",
  ReqHeaders = [{<<"Content-Type">>, <<"application/json">>}],
  ReqBody = << "{\"name\": \"some snippet\" }" >>,
  ibrowse:send_req(Url, ReqHeaders, get, ReqBody).
```

## pool

```sh
github.com/inaka/worker_pool
```

## light web server

```sh
github.com/sinasamavati/leptus
```

## code reloader

```sh
github.com/rustyio/sync
```

## redis

```sh
github.com/ziyouchutuwenwu/eredis_pool
```

## pgsql

```sh
github.com/ziyouchutuwenwu/epgsql_pool
```

## captcha

```sh
github.com/ziyouchutuwenwu/simple_captcha
```

## 目录监控

```sh
github.com/sheyll/inotify
```

## json 解析

```sh
github.com/sile/jsone
```
