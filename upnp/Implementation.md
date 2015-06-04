# UPnPポートマップの実装
<hr>
<br>


* **Bencodingはパースしやすい構造**

<br>

* **BNFから機械的にコードを抽出**


<br>
<hr>

## UPnPを実装しよう

次のサンプル実装を以下におきました。
* https://github.com/kyorohiro/dart_hetimanet/tree/master/lib/src/upnp
* https://github.com/kyorohiro/HetimaPortMap


* プライベートネットワークを調べる
```
HetiSocketBuilderChrome#getNetworkInterfaces().then((List<HetiNetworkInterface> il) {
  });
```

* ルータを発見する
```
UpnpDeviceSearcher.createInstance(new hetimacl.HetiSocketBuilderChrome()).then((hetima.UpnpDeviceSearcher searcher) {
    searcher.onReceive().listen((hetima.UPnpDeviceInfo info) {
    });
    searcher.searchWanPPPDevice();
  });
```
## UPnPを実装しよう

次のサンプル実装を以下におきました。
* https://github.com/kyorohiro/dart_hetimanet/tree/master/lib/src/upnp
* https://github.com/kyorohiro/HetimaPortMap


* プライベートネットワークを調べる
```
HetiSocketBuilderChrome#getNetworkInterfaces().then((List<HetiNetworkInterface> il) {
  });
```

* ルータを発見する
```
UpnpDeviceSearcher.createInstance(new hetimacl.HetiSocketBuilderChrome()).then((hetima.UpnpDeviceSearcher searcher) {
    searcher.onReceive().listen((hetima.UPnpDeviceInfo info) {
    });
    searcher.searchWanPPPDevice();
  });
```

* ポートマッピングする
```
UpnpPPPDevice#addPortMapping(localIP, localPort, remotePort, UPnpPPPDevice.VALUE_PORT_MAPPING_PROTOCOL_TCP)
           .then((UpnpPortMappingResult r) {
});
```

* グローバルアドレスを調べる
```
UpnpPPPDevice#requestGetExternalIPAddress().then((String address){
});
```




* ポートマッピングする
```
UpnpPPPDevice#addPortMapping(localIP, localPort, remotePort, UPnpPPPDevice.VALUE_PORT_MAPPING_PROTOCOL_TCP)
           .then((UpnpPortMappingResult r) {
});
```

* グローバルアドレスを調べる
```
UpnpPPPDevice#requestGetExternalIPAddress().then((String address){
});
```


