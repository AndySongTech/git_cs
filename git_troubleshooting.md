## Verbose output of push or pull
```
# See remotes
git remote -v

# Generate verbose output for push
GIT_SSH_COMMAND="ssh -vvv" git push fortrabbit main

# Generate verbose output for pull
GIT_SSH_COMMAND="ssh -vvv" git pull fortrabbit main
```
## Unable to clone GitHub repo
```sh
> ssh -T git@github.com                                                                                          
Hi AndySong16! You've successfully authenticated, but GitHub does not provide shell access.

> ssh -vvv -T git@github.com                          
OpenSSH_8.6p1, LibreSSL 2.8.3
debug1: Reading configuration data /Users/andysong/.ssh/config
debug1: /Users/andysong/.ssh/config line 2: Applying options for github.com
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 21: include /etc/ssh/ssh_config.d/* matched no files
debug1: /etc/ssh/ssh_config line 54: Applying options for *
debug3: expanded UserKnownHostsFile '~/.ssh/known_hosts' -> '/Users/andysong/.ssh/known_hosts'
debug3: expanded UserKnownHostsFile '~/.ssh/known_hosts2' -> '/Users/andysong/.ssh/known_hosts2'
debug1: Authenticator provider $SSH_SK_PROVIDER did not resolve; disabling
debug1: Connecting to github.com port 22.
debug1: Connection established.
debug1: identity file /Users/andysong/.ssh/id_rsa_au type 0
debug1: identity file /Users/andysong/.ssh/id_rsa_au-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_8.6
debug1: Remote protocol version 2.0, remote software version babeld-7f91b4d6
debug1: compat_banner: no match: babeld-7f91b4d6
debug3: fd 5 is O_NONBLOCK
debug1: Authenticating to github.com:22 as 'git'
debug3: record_hostkey: found key type RSA in file /Users/andysong/.ssh/known_hosts:3
debug3: load_hostkeys_file: loaded 1 keys from github.com
debug1: load_hostkeys: fopen /Users/andysong/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug3: order_hostkeyalgs: prefer hostkeyalgs: rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,ssh-rsa-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256,ssh-rsa
debug3: send packet: type 20
debug1: SSH2_MSG_KEXINIT sent
debug3: receive packet: type 20
debug1: SSH2_MSG_KEXINIT received
debug2: local client KEXINIT proposal
debug2: KEX algorithms: curve25519-sha256,curve25519-sha256@libssh.org,ecdh-sha2-nistp256,ecdh-sha2-nistp384,ecdh-sha2-nistp521,diffie-hellman-group-exchange-sha256,diffie-hellman-group16-sha512,diffie-hellman-group18-sha512,diffie-hellman-group14-sha256,ext-info-c
debug2: host key algorithms: rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,ssh-rsa-cert-v01@openssh.com,rsa-sha2-512,rsa-sha2-256,ssh-rsa,ssh-ed25519-cert-v01@openssh.com,ecdsa-sha2-nistp256-cert-v01@openssh.com,ecdsa-sha2-nistp384-cert-v01@openssh.com,ecdsa-sha2-nistp521-cert-v01@openssh.com,sk-ssh-ed25519-cert-v01@openssh.com,sk-ecdsa-sha2-nistp256-cert-v01@openssh.com,ssh-ed25519,ecdsa-sha2-nistp256,ecdsa-sha2-nistp384,ecdsa-sha2-nistp521,sk-ssh-ed25519@openssh.com,sk-ecdsa-sha2-nistp256@openssh.com
debug2: ciphers ctos: chacha20-poly1305@openssh.com,aes128-ctr,aes192-ctr,aes256-ctr,aes128-gcm@openssh.com,aes256-gcm@openssh.com
debug2: ciphers stoc: chacha20-poly1305@openssh.com,aes128-ctr,aes192-ctr,aes256-ctr,aes128-gcm@openssh.com,aes256-gcm@openssh.com
debug2: MACs ctos: umac-64-etm@openssh.com,umac-128-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,hmac-sha1-etm@openssh.com,umac-64@openssh.com,umac-128@openssh.com,hmac-sha2-256,hmac-sha2-512,hmac-sha1
debug2: MACs stoc: umac-64-etm@openssh.com,umac-128-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com,hmac-sha1-etm@openssh.com,umac-64@openssh.com,umac-128@openssh.com,hmac-sha2-256,hmac-sha2-512,hmac-sha1
debug2: compression ctos: none,zlib@openssh.com,zlib
debug2: compression stoc: none,zlib@openssh.com,zlib
debug2: languages ctos:
debug2: languages stoc:
debug2: first_kex_follows 0
debug2: reserved 0
debug2: peer server KEXINIT proposal
debug2: KEX algorithms: curve25519-sha256,curve25519-sha256@libssh.org,ecdh-sha2-nistp256,ecdh-sha2-nistp384,ecdh-sha2-nistp521,diffie-hellman-group-exchange-sha256
debug2: host key algorithms: ssh-ed25519,ecdsa-sha2-nistp256,rsa-sha2-512,rsa-sha2-256,ssh-rsa
debug2: ciphers ctos: chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr
debug2: ciphers stoc: chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes128-gcm@openssh.com,aes256-ctr,aes192-ctr,aes128-ctr
debug2: MACs ctos: hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512,hmac-sha2-256
debug2: MACs stoc: hmac-sha2-512-etm@openssh.com,hmac-sha2-256-etm@openssh.com,hmac-sha2-512,hmac-sha2-256
debug2: compression ctos: none,zlib@openssh.com,zlib
debug2: compression stoc: none,zlib@openssh.com,zlib
debug2: languages ctos:
debug2: languages stoc:
debug2: first_kex_follows 0
debug2: reserved 0
debug1: kex: algorithm: curve25519-sha256
debug1: kex: host key algorithm: rsa-sha2-512
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug3: send packet: type 30
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug3: receive packet: type 31
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-rsa SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8
debug3: record_hostkey: found key type RSA in file /Users/andysong/.ssh/known_hosts:3
debug3: load_hostkeys_file: loaded 1 keys from github.com
debug1: load_hostkeys: fopen /Users/andysong/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host 'github.com' is known and matches the RSA host key.
debug1: Found key in /Users/andysong/.ssh/known_hosts:3
debug3: send packet: type 21
debug2: set_newkeys: mode 1
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug3: receive packet: type 21
debug1: SSH2_MSG_NEWKEYS received
debug2: set_newkeys: mode 0
debug1: rekey in after 134217728 blocks
debug1: Will attempt key: /Users/andysong/.ssh/id_rsa_au RSA SHA256:LMO03neTsqCnC22WUZWu2U03hVe3elcUHUJAfv7b/lY explicit
debug2: pubkey_prepare: done
debug3: send packet: type 5
debug3: receive packet: type 7
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519-cert-v01@openssh.com,ecdsa-sha2-nistp521-cert-v01@openssh.com,ecdsa-sha2-nistp384-cert-v01@openssh.com,ecdsa-sha2-nistp256-cert-v01@openssh.com,sk-ssh-ed25519-cert-v01@openssh.com,sk-ecdsa-sha2-nistp256-cert-v01@openssh.com,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,ssh-rsa-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,sk-ecdsa-sha2-nistp256@openssh.com,ssh-ed25519,ecdsa-sha2-nistp521,ecdsa-sha2-nistp384,ecdsa-sha2-nistp256,rsa-sha2-512,rsa-sha2-256,ssh-rsa>
debug3: receive packet: type 6
debug2: service_accept: ssh-userauth
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug3: send packet: type 50
debug3: receive packet: type 51
debug1: Authentications that can continue: publickey
debug3: start over, passed a different list publickey
debug3: preferred publickey,keyboard-interactive,password
debug3: authmethod_lookup publickey
debug3: remaining preferred: keyboard-interactive,password
debug3: authmethod_is_enabled publickey
debug1: Next authentication method: publickey
debug1: Offering public key: /Users/andysong/.ssh/id_rsa_au RSA SHA256:LMO03neTsqCnC22WUZWu2U03hVe3elcUHUJAfv7b/lY explicit
debug3: send packet: type 50
debug2: we sent a publickey packet, wait for reply
debug3: receive packet: type 60
debug1: Server accepts key: /Users/andysong/.ssh/id_rsa_au RSA SHA256:LMO03neTsqCnC22WUZWu2U03hVe3elcUHUJAfv7b/lY explicit
debug3: sign_and_send_pubkey: RSA SHA256:LMO03neTsqCnC22WUZWu2U03hVe3elcUHUJAfv7b/lY
debug3: sign_and_send_pubkey: signing using rsa-sha2-512 SHA256:LMO03neTsqCnC22WUZWu2U03hVe3elcUHUJAfv7b/lY
debug3: send packet: type 50
debug3: receive packet: type 52
debug1: Authentication succeeded (publickey).
Authenticated to github.com ([20.205.243.166]:22).
debug1: channel 0: new [client-session]
debug3: ssh_session2_open: channel_new: 0
debug2: channel 0: send open
debug3: send packet: type 90
debug1: Entering interactive session.
debug1: pledge: filesystem full
debug3: receive packet: type 80
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug3: client_input_hostkeys: received RSA key SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8
debug3: client_input_hostkeys: received ECDSA key SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM
debug3: client_input_hostkeys: received ED25519 key SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU
debug1: client_input_hostkeys: searching /Users/andysong/.ssh/known_hosts for github.com / (none)
debug3: hostkeys_foreach: reading file "/Users/andysong/.ssh/known_hosts"
debug3: hostkeys_find: found ssh-rsa key at /Users/andysong/.ssh/known_hosts:3
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:4
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:5
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:7
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:8
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:9
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:10
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:11
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:23
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:24
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:25
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:26
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:28
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:29
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:30
debug3: hostkeys_find: found ssh-rsa key under different name/addr at /Users/andysong/.ssh/known_hosts:37
debug1: client_input_hostkeys: searching /Users/andysong/.ssh/known_hosts2 for github.com / (none)
debug1: client_input_hostkeys: hostkeys file /Users/andysong/.ssh/known_hosts2 does not exist
debug3: client_input_hostkeys: 3 server keys: 2 new, 18446744073709551615 retained, 2 incomplete match. 0 to remove
debug1: client_input_hostkeys: host key found matching a different name/address, skipping UserKnownHostsFile update
debug3: receive packet: type 91
debug2: channel_input_open_confirmation: channel 0: callback start
debug2: fd 5 setting TCP_NODELAY
debug3: set_sock_tos: set socket 5 IP_TOS 0x20
debug2: client_session2_setup: id 0
debug1: Sending environment.
debug3: Ignored env TERM_SESSION_ID
debug3: Ignored env SSH_AUTH_SOCK
debug1: channel 0: setting env LC_TERMINAL_VERSION = "3.4.15"
debug2: channel 0: request env confirm 0
debug3: send packet: type 98
debug3: Ignored env COLORFGBG
debug3: Ignored env ITERM_PROFILE
debug3: Ignored env XPC_FLAGS
debug3: Ignored env PWD
debug3: Ignored env SHELL
debug3: Ignored env __CFBundleIdentifier
debug3: Ignored env TERM_PROGRAM_VERSION
debug3: Ignored env TERM_PROGRAM
debug3: Ignored env PATH
debug3: Ignored env DISPLAY
debug1: channel 0: setting env LC_TERMINAL = "iTerm2"
debug2: channel 0: request env confirm 0
debug3: send packet: type 98
debug3: Ignored env COLORTERM
debug3: Ignored env COMMAND_MODE
debug3: Ignored env TERM
debug3: Ignored env HOME
debug3: Ignored env TMPDIR
debug3: Ignored env USER
debug3: Ignored env XPC_SERVICE_NAME
debug3: Ignored env LOGNAME
debug3: Ignored env ITERM_SESSION_ID
debug3: Ignored env __CF_USER_TEXT_ENCODING
debug3: Ignored env SHLVL
debug3: Ignored env OLDPWD
debug3: Ignored env ARTIFACT_REPO_LOCATION
debug3: Ignored env ARTIFACT_REPO_USERNAME
debug3: Ignored env ARTIFACT_REPO_PASSWORD
debug3: Ignored env ARTIFACT_REPO_MAVEN_URL
debug3: Ignored env MVNW_REPOURL
debug3: Ignored env MVNW_USERNAME
debug3: Ignored env MVNW_PASSWORD
debug3: Ignored env ARTIFACT_REPO_PYPI_URL
debug3: Ignored env PIP_INDEX_URL
debug3: Ignored env PIP_EXTRA_INDEX_URL
debug3: Ignored env ENGINEERING_SAMLROLE
debug3: Ignored env ZSH
debug3: Ignored env PAGER
debug3: Ignored env LESS
debug3: Ignored env LSCOLORS
debug3: Ignored env DEFAULT_USER
debug3: Ignored env AWS_REGION
debug3: Ignored env AWS_DEFAULT_REGION
debug3: Ignored env NAME
debug3: Ignored env KOPS_STATE_STORE
debug3: Ignored env FZF_DEFAULT_OPTS
debug3: Ignored env LDFLAGS
debug3: Ignored env CPPFLAGS
debug3: Ignored env GITHUB_TOKEN
debug3: Ignored env GITHUB_ORG
debug3: Ignored env AWS_SESSION_TTL
debug3: Ignored env AWS_ASSUME_ROLE_TTL
debug3: Ignored env AWS_PAGER
debug1: channel 0: setting env LC_CTYPE = "UTF-8"
debug2: channel 0: request env confirm 0
debug3: send packet: type 98
debug3: Ignored env TILLER_NAMESPACE
debug3: Ignored env _
debug2: channel 0: request shell confirm 1
debug3: send packet: type 98
debug2: channel_input_open_confirmation: channel 0: callback done
debug2: channel 0: open confirm rwindow 32000 rmax 35000
debug3: receive packet: type 99
debug2: channel_input_status_confirm: type 99 id 0
debug2: shell request accepted on channel 0
debug2: channel 0: rcvd ext data 92
debug3: receive packet: type 98
debug1: client_input_channel_req: channel 0 rtype exit-status reply 0
debug3: receive packet: type 96
debug2: channel 0: rcvd eof
debug2: channel 0: output open -> drain
debug3: receive packet: type 97
debug2: channel 0: rcvd close
debug2: chan_shutdown_read: channel 0: (i0 o1 sock -1 wfd 6 efd 8 [write])
debug2: channel 0: input open -> closed
debug3: channel 0: will not send data after close
debug2: channel 0: obuf_empty delayed efd 8/(92)
Hi AndySong16! You've successfully authenticated, but GitHub does not provide shell access.
debug2: channel 0: written 92 to efd 8
debug3: channel 0: will not send data after close
debug2: channel 0: obuf empty
debug2: chan_shutdown_write: channel 0: (i3 o1 sock -1 wfd 7 efd 8 [write])
debug2: channel 0: output drain -> closed
debug2: channel 0: almost dead
debug2: channel 0: gc: notify user
debug2: channel 0: gc: user detached
debug2: channel 0: send close
debug3: send packet: type 97
debug2: channel 0: is dead
debug2: channel 0: garbage collecting
debug1: channel 0: free: client-session, nchannels 1
debug3: channel 0: status: The following connections are open:
  #0 client-session (t4 r43 i3/0 o3/0 e[write]/0 fd -1/-1/8 sock -1 cc -1)

debug3: send packet: type 1
debug3: fd 1 is not O_NONBLOCK
Transferred: sent 2908, received 2992 bytes, in 0.6 seconds
Bytes per second: sent 4606.8, received 4739.8
debug1: Exit status 1
```
