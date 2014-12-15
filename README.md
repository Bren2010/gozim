[![Build Status](https://travis-ci.org/akhenakh/gozim.svg?branch=master)](https://travis-ci.org/akhenakh/gozim)

gozim
=====

A Go native implementation for ZIM files. See http://akhenakh.github.io/gozim  

ZIM files are used mainly as offline wikipedia copies.

See http://openzim.org/wiki/ZIM_file_format and http://openzim.org/wiki/ZIM_File_Example

Wikipedia/Wikinews/... ZIMs can be downloaded from there http://download.kiwix.org/zim/

![ScreenShot](/shots/browse.jpg)

build and installation
======================
For the indexer bleve to work properly it's recommended that you use leveldb as storage.
Note that you need to install libleveldb as a dependency on your system
```
go get -u -v -tags leveldb  github.com/blevesearch/bleve/...
```

Gozim http server is using go.rice to embed html/css in the binary install the rice command
```
go install github.com/GeertJohan/go.rice/rice
```

After a go build run:
```
rice append --exec gozimhttpd
```

On Ubuntu/Debian youn need to apt-get install liblzma-dev.


TODO
====
Mmap 1st 2GB on 32 bits  
Selective Gzip encode response based on content type  
Search with title stemming  
func rather than if for getBytes  
