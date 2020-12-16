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
github.com/benoitc/hackney
```

用法

```erlang
get_demo() ->
  application:ensure_all_started(hackney),
  ReqHeaders = [],
  Path = <<"http://127.0.0.1:8100">>,
  ReqBody = << "{
      \"name\": \"aaaa\",
      \"pass\": \"bbb\"
  }" >>,
  Options = [],
  {ok, _StatusCode, _RespHeaders, _ClientRef} = hackney:request(get, Path, ReqHeaders, ReqBody, Options).

%% curl -d "name=dongguan" http://127.0.0.1:8100
form_post_demo() ->
  application:ensure_all_started(hackney),
  ReqHeaders = [{<<"Content-Type">>, <<"application/x-www-form-urlencoded">>}],
  Path = <<"http://127.0.0.1:8100">>,
  Form = {form,  [{<<"name">>,<<"aaa">>}, {<<"pass">>,<<"bbb">>}]},
  Options = [],
  hackney:post(Path, ReqHeaders, Form, Options).

%% curl -H "Content-Type:application/json" -X POST --data '{"name": "sunshine"}' http://127.0.0.1:8100
json_post_demo() ->
  application:ensure_all_started(hackney),

  ReqBody = << "{
      \"name\": \"aaaa\",
      \"pass\": \"bbb\"
  }" >>,
  ReqHeaders = [{<<"Content-Type">>, <<"application/json">>}],
  Path = <<"http://127.0.0.1:8100">>,
  Method = post,
  {ok, ClientRef} = hackney:request(Method, Path, ReqHeaders, stream, []),
  ok  = hackney:send_body(ClientRef, ReqBody),
  {ok, _Status, _Headers, ClientRef} = hackney:start_response(ClientRef),
  {ok, _Body} = hackney:body(ClientRef).
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
