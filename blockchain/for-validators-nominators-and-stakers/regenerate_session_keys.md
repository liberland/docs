# Regenerate session keys

`author_rotateKeys` generates new keys and stores them in your node, overwriting any keys that were there before.
Install `node-ws` package if you don't have `wscat`: `apt install node-ws`.

```
user@host:~/liberland/$ wscat -c ws://127.0.0.1:9944 -x '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}'
{"jsonrpc":"2.0","result":"0x58db6952384f2d1f9600255a2fce9b116201e872e9951a0a0c0edd7c31124934c690eb603407f4b98a1c9fc0628d4b926fec03d577f233fda3af01d33e2a391b9ad7558c0ae9ba082b3b70236ec584471c92c3a5d78e9bc08f49de7c75961e132697e5419818bfcd31e1bc2cc7d0560a81db72a76af59374c1932bc7a96d773a","id":1}
```

Copy the contents of `result` from your terminal, thats the new session keys.

Alternatively if you dont have wscat try 

```
curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}' http://127.0.0.1:9944
```
