# xx530v SQM / CAKE OpenWrt build

This repository builds an OpenWrt firmware image for the TP-Link xx230v/xx530v v1 profile on the Airoha EN7523 target.

## Included

- `sqm-scripts`
- `luci-app-sqm`
- `kmod-sched-cake`
- `kmod-sched-fq_codel`
- `kmod-ifb`

The build is pinned to OpenWrt commit `aeee87fcbf75c3b8ea027fa33b50d795c60ffbb1`, matching the snapshot family shown on the router.

## Important before flashing

1. Back up `/etc/config`, especially networking, wireless, and any OMCI/vendor-specific configuration.
2. Keep a known-good recovery/boot path available.
3. Use the `*-squashfs-sysupgrade.bin` image for a normal OpenWrt sysupgrade when the installed firmware and partition layout are compatible.
4. Do not flash bootloader artifacts unless you specifically know they are required for your device.
5. After upgrading, configure SQM manually in LuCI and start with a conservative bandwidth such as 37–38 Mbps for a 40 Mbps line, then tune latency and throughput.

The OpenWrt image target itself is the existing `tplink_xx230v-v1` profile; OpenWrt identifies it with the xx530v alternate model name as well.
