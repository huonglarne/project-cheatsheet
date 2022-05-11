# Generate key pairs

Specify type: `-t rsa`

Specify length: `-b 4096`

Specify filename: `-f filename`

`ssh-keygen -t ed25519 -f filename`

# Connect to server

## Terminal command

Forward port: `-L 8888:localhost:8888`

Only forward port, not execute command: `-N`

`ssh -N -L 8888:localhost:8888 username@address -i identity_file_path`

## Config

Modify file `~/.ssh/config`

```
Host host_nickname
    HostName 111.111.111.111
    Port 8888
    User username
    IdentityFile path_to_private_key
    LocalForward 8888 localhost:8888
```

`ssh host_nickname`