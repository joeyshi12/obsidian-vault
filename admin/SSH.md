# SSH (Secure Shell)

## Setup

- Let the host run `ssh-keygen` to create a public, private key-pair
- Add public key `*.pub` to a newline in `$HOME/.ssh/authorized_keys` on the linux server
- Add alias in `.ssh/config`

## ~/.ssh/config

```
Host <alias>
    HostName <host>
    User <user>
    IdentityFile <path-to-private-key>  # optional

... other aliases
```

## SSH Daemon Config

- `/etc/ssh/sshd_config`
- Example options:
    - PermitRootLogin
    - PasswordAuthentication (set to no to require users to have authorized private key)

```
#Port 22
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::

#HostKey /etc/ssh/ssh_host_rsa_key
#HostKey /etc/ssh/ssh_host_ecdsa_key
#HostKey /etc/ssh/ssh_host_ed25519_key

# Ciphers and keying
#RekeyLimit default none

# Logging
#SyslogFacility AUTH
#LogLevel INFO

# Authentication:

#LoginGraceTime 2m
#PermitRootLogin prohibit-password
#StrictModes yes
#MaxAuthTries 6
#MaxSessions 10
```