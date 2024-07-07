
# SSH -> Linux

Install openssh-server: `sudo apt install openssh-server`
Start the service `sudo systemctl start ssh`

If on VM check for Bridged Adapter network
Check IP: `ip a`

Connect with `ssh <username>@<target-ip>`

## Local port forwarding

```sh
ssh -L <host-port>:127.0.0.1:<target-port> <user>@<target-ip>
```

Connect on host web browser with: `localhost:<host-port>`