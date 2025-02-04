This is opentracker. An open bittorrent tracker.

You need libowfat (http://www.fefe.de/libowfat/).

Steps to go:

## required commands:

```
sudo apt-get update 
sudo apt-get install clang make cvs
```

```
sudo apt-get install zlib1g-dev
```


```
cvs -d :pserver:cvs@cvs.fefe.de:/cvs -z9 co libowfat
cd libowfat
make
cd .. 
```
``` cvs -d:pserver:anoncvs@cvs.erdgeist.org:/home/cvsroot co opentracker
cd opentracker
make
./opentracker 
```

This tracker is open in a sense that everyone announcing a torrent is welcome to do so and will be informed about anyone else announcing the same torrent. Unless
-DWANT_IP_FROM_QUERY_STRING is enabled (which is meant for debugging purposes only), only source IPs are accepted. The tracker implements a minimal set of
essential features only but was able respond to far more than 10000 requests per second on a Sun Fire 2200 M2 (thats where we found no more clients able to fire
more of our testsuite.sh script).

Some tweaks you may want to try under FreeBSD:

sysctl kern.ipc.somaxconn=1024
sysctl kern.ipc.nmbclusters=32768
sysctl net.inet.tcp.msl=10000
sysctl kern.maxfiles=10240

License information:

Although the libowfat library is under GPL, Felix von Leitner aggreed that the compiled binary may be distributed under the same beer ware license as the source code for opentracker. However, we like to hear from happy customers.
