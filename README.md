# Brainfuck Tunnel - Psiphon Pro Go Version

...


Requirements
------------

**Linux**

    git
    golang
    redsocks

**Windows**

    golang
    proxifier

**Android (Termux)**

    git
    golang


Install
-------

**Brainfuck Psiphon Pro Go**

    $ go get -v -u github.com/Anggabaonks/popon-go
    $ cd ~/go/src/github.com/Anggabaonks/popon-go
    $ go build -ldflags "-s -w"
    $ GOOS=linux GOARCH=arm64 go build -ldflags "-s -w"
    $ GOOS=linux GOARCH=arm GOARM=7 go build -ldflags="-s -w"
    $ GOOS=windows GOARCH=amd64 go build -ldflags "-s -w"
    
    
**Psiphon Tunnel Core**

    $ go get -v -u github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ cd ~/go/src/github.com/Psiphon-Labs/psiphon-tunnel-core/ConsoleClient
    $ go build -ldflags "-s -w" -o ~/go/src/github.com/Anggabaonks/popon-go/psiphon-tunnel-core


Usage
-----

**Linux**

    $ cd ~/go/src/github.com/Anggabaonks/popon-go
    $ sudo --preserve-env -s
    # ./popon-go


**Android (Termux)**

    $ cd ~/go/src/github.com/Anggabaonks/popon-go
    $ ./popon-go

<!-- -->

    Use ProxyDroid (root), Tun2Tap, or SocksDroid to redirect all connection to this Tunnel (Socks 5 Port 3080)
    Exclude Termux!


Configurations
--------------

Run `./brainfuck-psiphon-pro-go` first to export all default settings.
Config will generated to `config.json` popon-go binary file are executed.


### Pro Version

    ...
    "PsiphonCore": 1,
    "Psiphon": {
        "CoreName": "psiphon-tunnel-core",
        "Tunnel": 4,
        "Region": "",
        "Protocols": [
            "FRONTED-MEEK-HTTP-OSSH",
            "FRONTED-MEEK-OSSH"
        ],
        "TunnelWorkers": 8,
        "KuotaDataLimit": 0,
        "Authorizations": [
            "blablabla"
        ]
    }
    ...


### Rules

**XL Iflix or Axis Gaming (Default)**

    ...
    "Rules": {
        "akamai.net:80": [
            "video.iflix.com",
            "videocdn-2.iflix.com",
            "iflix-videocdn-p1.akamaized.net",
            "iflix-videocdn-p2.akamaized.net",
            "iflix-videocdn-p3.akamaized.net",
            "iflix-videocdn-p6.akamaized.net",
            "iflix-videocdn-p7.akamaized.net",
            "iflix-videocdn-p8.akamaized.net"
        ]
    },
    ...

**Direct**

    ...
    "Rules": {
        "*:*": [
            "*"
        ]
    },
    ...

or

    ./brainfuck-psiphon-pro-go -f "*" -w "*:*"

**Telkomsel 0P0K**

    ...
    "Rules": {
        "akamai.net:443": [
            "118.97.159.51:443",
            "118.98.95.106:443"
        ]
    },
    ...

or

    ./brainfuck-psiphon-pro-go -f 118.97.159.51:443,118.98.95.106:443 -w akamai.net:443

**XL King**

    ...
    "Rules": {
        "akamai.net:80": [
            "ak-quic.stream.music.joox.com.edgesuite.net",
            "ak-hk.stream.music.joox.com.edgesuite.net",
            "ak-ng.stream.music.joox.com.edgesuite.net",
            "ak-quic.app.joox.com.edgesuite.net",
            "ak-ng.app.joox.com.edgesuite.net",
            "e5121.b.akamaiedge.net",
            "www.pubgmobile.com"
        ]
    },
    ...

**Joox**

    ...
    "Rules": {
        "akamai.net:80": [
            "ak-quic.stream.music.joox.com.edgesuite.net",
            "ak-hk.stream.music.joox.com.edgesuite.net",
            "ak-ng.stream.music.joox.com.edgesuite.net",
            "ak-quic.app.joox.com.edgesuite.net",
            "ak-ng.app.joox.com.edgesuite.net",
            "e5121.b.akamaiedge.net"
        ]
    },
    ...

**Ruang Guru and Udemmy (XL or Axis)**

    ...
    "Rules": {
        "akamai.net:80": [
            "*"
        ],
        "fastly.net:80": [
            "c.shared.global.fastly.net",
            "rg-video.ruangguru.com"
        ]
    },
    ...

