#!help

# What you can get from this file.

    1. how to surpport multi-project with ~/.ssh/confiig


1. vi ~/.ssh/config

    # Site-wide defaults for various options
    Host *
    ForwardAgent no
    ForwardX11 no
    RhostsAuthentication no
    RhostsRSAAuthentication no
    RSAAuthentication yes
    PasswordAuthentication yes
    FallBackToRsh no
    UseRsh no
    BatchMode no
    CheckHostIP yes
    StrictHostKeyChecking no
    IdentityFile ~/.ssh/identity
    Port 22
    Cipher blowfish
    EscapeChar ~


    # This is ssh server systemwide configuration file.
    Port 22
    ListenAddress 192.168.1.1
    HostKey /etc/ssh/ssh_host_key
    ServerKeyBits 1024
    LoginGraceTime 600
    KeyRegenerationInterval 3600
    PermitRootLogin no
    IgnoreRhosts yes
    IgnoreUserKnownHosts yes
    StrictModes yes
    X11Forwarding no
    PrintMotd yes
    SyslogFacility AUTH
    LogLevel INFO
    RhostsAuthentication no
    RhostsRSAAuthentication no
    RSAAuthentication yes
    PasswordAuthentication yes
    PermitEmptyPasswords no
    AllowUsers admin

    eg:
        Host opencode-v.alibaba-inc.com
        User realtek_hardy
        Port 29418
        IdentityFile ~/.ssh/konka_ali/id_rsa
        
        Host github.com
        HostName github.com
        User gmaui
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/github/id_rsa

