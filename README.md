Even `dpdk_dep` is used with `as_system('system')` the includes are done using `-I` instead of `-isystem` causing the compiler to throw many warnings related to DPDK code.

```
meson setup build
meson compile -C build -v
```

or see `setup.log` and `build.log` file.

From `build.log`:
```
[145/225] c++ -Isrc/main.p -Isrc -I../src -Isubprojects/dpdk -I../subprojects/dpdk -Isubprojects/dpdk/config -I../subprojects/dpdk/config -Isubprojects/dpdk/lib/eal/include -I../subprojects/dpdk/lib/eal/include -Isubprojects/dpdk/lib/eal/linux/include -I../subprojects/dpdk/lib/eal/linux/include -Isubprojects/dpdk/lib/eal/x86/include -I../subprojects/dpdk/lib/eal/x86/include -Isubprojects/dpdk/lib/log -I../subprojects/dpdk/lib/log -Isubprojects/dpdk/lib/kvargs -I../subprojects/dpdk/lib/kvargs -I../subprojects/dpdk/lib/metrics -Isubprojects/dpdk/lib/telemetry -I../subprojects/dpdk/lib/telemetry -Isubprojects/dpdk/lib/eal/common -I../subprojects/dpdk/lib/eal/common -Isubprojects/dpdk/lib/eal -I../subprojects/dpdk/lib/eal -Isubprojects/dpdk/lib/ring -I../subprojects/dpdk/lib/ring -Isubprojects/dpdk/lib/rcu -I../subprojects/dpdk/lib/rcu -Isubprojects/dpdk/lib/mempool -I../subprojects/dpdk/lib/mempool -Isubprojects/dpdk/lib/mbuf -I../subprojects/dpdk/lib/mbuf -Isubprojects/dpdk/lib/net -I../subprojects/dpdk/lib/net -Isubprojects/dpdk/lib/meter -I../subprojects/dpdk/lib/meter -Isubprojects/dpdk/lib/ethdev -I../subprojects/dpdk/lib/ethdev -Isubprojects/dpdk/lib/pci -I../subprojects/dpdk/lib/pci -Isubprojects/dpdk/lib/cmdline -I../subprojects/dpdk/lib/cmdline -Isubprojects/dpdk/lib/hash -I../subprojects/dpdk/lib/hash -Isubprojects/dpdk/lib/stack -I../subprojects/dpdk/lib/stack -Isubprojects/dpdk/drivers/bus/pci -I../subprojects/dpdk/drivers/bus/pci -I../subprojects/dpdk/drivers/bus/pci/linux -Isubprojects/dpdk/drivers/bus/vdev -I../subprojects/dpdk/drivers/bus/vdev -Isubprojects/dpdk/drivers/mempool/ring -I../subprojects/dpdk/drivers/mempool/ring -Isubprojects/dpdk/drivers/net/af_packet -I../subprojects/dpdk/drivers/net/af_packet -fdiagnostics-color=always -D_GLIBCXX_ASSERTIONS=1 -D_FILE_OFFSET_BITS=64 -Wall -Winvalid-pch -Wextra -O0 -g -include rte_config.h -march=native -mrtm -MD -MQ src/main.p/main.cpp.o -MF src/main.p/main.cpp.o.d -o src/main.p/main.cpp.o -c ../src/main.cpp
```