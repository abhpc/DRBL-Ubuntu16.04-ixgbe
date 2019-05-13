### 1. Download the driver:

    # wget https://downloadmirror.intel.com/14687/eng/ixgbe-5.5.5.tar.gz

### 2. Build and install the driver:

    # tar -vxf ixbge-5.5.5.tar.gz
    # cd ixgbe-5.5.5/src
    # make && make install

### 3. Load the ixgbe module at startup.

There are two ways to load the ixgbe module:

#### 1) Load the module through /etc/rc.local:

Insert this line below into /etc/rc.local before the "exit 0;" line:

    modprobe ixgbe allow_unsupported_sfp=1

##### 2) Load the module thourgh /lib/modprobe.d/ixgbe.conf

    # echo "options ixgbe allow_unsupported_sfp=1" > /lib/modprobe.d/ixgbe.conf
    # depmod -a
    # echo "ixgbe" >> /etc/modules
