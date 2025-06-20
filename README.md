# Tailscale exit-node on Glinet v4 router
How to enable the Tailscale exit node option on a GL.iNet v4 router

## Configuration
### Connect to your GLINET router
```
ssh root@192.168.8.1
```

### Add option to tailscale script
```
vi /usr/bin/gl_tailscale
```

Then add `--advertise-exit-node` to `tailscale up`, for example:
```
/usr/sbin/tailscale up --advertise-exit-node --reset $param --timeout 3s
```

Then reboot the GLINET.

Repeat these steps after each firmware upgrade.
