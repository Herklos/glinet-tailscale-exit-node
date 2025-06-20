# glinet-tailscale-exit-node
How to enable tailscale exit node option on a Glinet v4 router

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
