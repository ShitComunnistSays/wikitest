# Create Swap File

The first thing we need to do is create an empty file of the required size. To do this open the Terminal and execute the command given below. In this example I am creating a 3GB swap file. You will not probably need that much. So, enter your own value.

```
$ cd /
$ sudo dd if=/dev/zero of=swapfile bs=1M count=3000
```

To set it as 1GB, change the count value (3000 in the example above) to 1000, 1500 for 1.5GB etc.

Now change the file created to a swap file with the command below.
```
$ sudo mkswap swapfile
```
Turn on the swap file with the command,
```
$ sudo swapon swapfile
```
To ensure that the swap file is turned on automatically at system startup, open fstab.
```
$ sudo nano etc/fstab
```
And add the line given below. Save and close.
```
/swapfile none swap sw 0 0
```
That is it. You can check if the system is using the swap file you created with the command
```
$ cat /proc/meminfo
```

# Auto
To compile and install ZCore, you can use the [install script](https://zcore.ch/install.sh) using cURL (_tested with Ubuntu 16_):

```
sudo curl -o- https://zcore.ch/install.sh | bash
```

Start daemon:
```
zcored --daemon
```

Test:
```
zcore-cli getinfo
```

# Manual

== Note

Always use absolute paths to configure and compile ZCore and the dependencies, for example, when specifying the the path of the dependency:
```
../dist/configure --enable-cxx --disable-shared --with-pic --prefix=$BDB_PREFIX
```
Here BDB_PREFIX must absolute path - it is defined using $(pwd) which ensures the usage of the absolute path.


This will build zcore-qt as well if the dependencies are met.

== Dependencies

Required: 

 Library     | Purpose          | Description
 ------------|------------------|----------------------
 libssl      | Crypto           | Random Number Generation, Elliptic Curve Cryptography
 libboost    | Utility          | Library for threading, data structures, etc
 libevent    | Networking       | OS independent asynchronous networking

Optional dependencies:

 Library     | Purpose          | Description
 ------------|------------------|----------------------
 miniupnpc   | UPnP Support     | Firewall-jumping support
 libdb4.8    | Berkeley DB      | Wallet storage (only needed when wallet enabled)
 qt          | GUI              | GUI toolkit (only needed when GUI enabled)
 protobuf    | Payments in GUI  | Data interchange format used for payment protocol (only needed when GUI enabled)
 libqrencode | QR codes in GUI  | Optional for generating QR codes (only needed when GUI enabled)
 libzmq3     | ZMQ notification | Optional, allows generating ZMQ notifications (requires ZMQ version >= 4.x)

== System requirements

C++ compilers are memory-hungry. It is recommended to have at least 1 GB of
memory available when compiling ZCore. With 512MB of memory or less
compilation will take much longer due to swap thrashing.

== Dependency Build Instructions: Ubuntu & Debian
=== Build requirements:
```
    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
```

On at least Ubuntu 14.04+ and Debian 7+ there are generic names for the
individual boost development packages, so the following can be used to only
install necessary parts of boost:

```
    sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
```

If that doesn't work, you can install all boost development packages with:

```
    sudo apt-get install libboost-all-dev
```
=== BerkeleyDB

BerkeleyDB is required for the wallet. db4.8 packages are available [here](https://launchpad.net/~bitcoin/+archive/bitcoin).
You can add the repository and install using the following commands:

    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

Ubuntu and Debian have their own libdb-dev and libdb++-dev packages, but these will install
BerkeleyDB 5.1 or later, which break binary wallet compatibility with the distributed executables which
are based on BerkeleyDB 4.8. If you do not care about wallet compatibility,
pass `--with-incompatible-bdb` to configure.


Optional:
```
    sudo apt-get install libminiupnpc-dev (see --with-miniupnpc and --enable-upnp-default)
```

ZMQ dependencies:
```
    sudo apt-get install libzmq3-dev (provides ZMQ API 4.x)
```

== Dependencies for the GUI: Ubuntu & Debian

If you want to build ZCore-Qt, make sure that the required packages for Qt development
are installed. Either Qt 5 or Qt 4 are necessary to build the GUI.
If both Qt 4 and Qt 5 are installed, Qt 5 will be used. Pass `--with-gui=qt4` to configure to choose Qt4.
To build without GUI pass `--without-gui`.

To build with Qt 5 (recommended) you need the following:

```
    sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler
```

Alternatively, to build with Qt 4 you need the following:
```
    sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler
```

libqrencode (optional) can be installed with:
```
    sudo apt-get install libqrencode-dev
```

Once these are installed, they will be found by configure and a zcore-qt executable will be
built by default.

=== miniupnpc
[miniupnpc](http://miniupnp.free.fr/) may be used for UPnP port mapping.  It can be downloaded from [here](
http://miniupnp.tuxfamily.org/files/).  UPnP support is compiled in and
turned off by default.  See the configure options for upnp behavior desired:

```
	--without-miniupnpc      No UPnP support miniupnp not required
	--disable-upnp-default   (the default) UPnP support turned off by default at runtime
	--enable-upnp-default    UPnP support turned on by default at runtime
```


== Build
```
./autogen.sh
./configure
make
make install # optional
```