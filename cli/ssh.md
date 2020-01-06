# SSH config


## Allow SSH Root Login From Specific IP
 

file: sshd_config

```shell
# global config
PermitRootLogin no


Match Host foo.example.com
    PermitRootLogin yes

# permit root login
Match Address 192.168.10.10,192.168.1.0/24,10.254.0.0/16
    PermitRootLogin yes
```

可以根据Host或者Address匹配。

- [Linux: Allow SSH Root Login From Specific IP](https://stackpointer.io/unix/linux-allow-ssh-root-login-specific-ip/618/)