# Tailscale exit-node on Glinet v4 router
How to enable the Tailscale exit node option on a GL.iNet v4 router

# Configurations

## Option 1
### Connect to your GLINET router
```sh
ssh root@192.168.8.1
```

### Add option to tailscale script
```sh
vi /usr/bin/gl_tailscale
```

Then add `--advertise-exit-node` to `tailscale up`, for example:
```sh
/usr/sbin/tailscale up --advertise-exit-node --reset $param --timeout 3s
```

Then reboot the GLINET.

Repeat these steps after each firmware upgrade.

## Option 2

1. Go to System > Advanced Settings > Go to LuCI > System > Startup > Local startup
2. Replace by something like
   ```sh
   . /lib/functions/gl_util.sh
   remount_ubifs

   ( sleep 60; tailscale set --advertise-exit-node ) &

   exit 0
   ```
3. Reboot


