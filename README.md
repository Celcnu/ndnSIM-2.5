# ndnSIM-2.5

### Download initial code of ndnSIM v2.5
1) git clone the 1st edition of this repository (recommended)
2) follow the instructions below:

`git clone -b ndnSIM-v2.5 https://github.com/named-data-ndnSIM/ns-3-dev.git ns-3

git clone -b 0.18.0 https://github.com/named-data-ndnSIM/pybindgen.git pybindgen

git clone -b ndnSIM-2.5 --recursive https://github.com/named-data-ndnSIM/ndnSIM ns-3/src/ndnSIM`

### Issuses
If you met the problem of "ndnSIM will not be built as it requires boost libraries of version at least 1.54.0" during the waf configure process, please refer to [Installing boost libraries to /usr/local](https://ndnsim.net/current/faq.html#boost-libraries), or follow the instructions below:

**1) install boost libraries manually**

 `wget http://downloads.sourceforge.net/project/boost/boost/1.62.0/boost_1_62_0.tar.bz2
 
 tar jxf boost_1_62_0.tar.bz2
 
 cd boost_1_62_0
 
 ./bootstrap.sh
 
 sudo ./b2 --prefix=/usr/local install`

**2) specify libboost path when compile**

`cd <ns-3>
 
 ./waf configure --boost-includes=/usr/local/include --boost-libs=/usr/local/lib --enable-examples
 
 ./waf
 
 LD_LIBRARY_PATH=/usr/local/lib NS_LOG=ndn.Consumer ./waf --run=ndn-simple`
