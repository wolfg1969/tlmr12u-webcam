# tlmr12u-webcam
TP-Link MR12U + Logitech C170 + OpenWRT


## Build Image
```bash
$ make image PROFILE=TLMR13U PACKAGES="kmod-usb-core kmod-usb2 kmod-ledtrig-usbdev kmod-video-core kmod-video-uvc usbutils mjpg-streamer  liblua lua libuci-lua libubus libubus-lua uhttpd rpcd luci-base luci-lib-ip luci-lib-nixio luci-theme-bootstrap luci-mod-admin-full luci-lib-jsonc -ppp -ppp-mod-pppoe -ip6tables -odhcp6c -kmod-ipv6 -kmod-ip6tables -luci-proto-ipv6 -luci-proto-ppp"
```

## /etc/config/mjpg-streamer
<pre>
config mjpg-streamer 'core'
	option enabled '1'
	option input 'uvc'
	option output 'http'
	option device '/dev/video0'
	option resolution '640x480'
	option yuv '0'
	option quality '80'
	option fps '5'
	option led 'auto'
	option www '/www/webcam'
	option port '8080'
	option username '******'
	option password '******'
</pre>
