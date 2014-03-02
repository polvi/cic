coreos on coreos

```
$ git clone https://github.com/polvi/cic
$ sudo ./cic/cic boom
boom / # systemctl status dbus
dbus.service - D-Bus System Message Bus
   Loaded: loaded (/usr/lib64/systemd/system/dbus.service; static)
   Active: active (running) since Sun 2014-03-02 06:29:08 UTC; 1min 1s ago
 Main PID: 58 (dbus-daemon)
   CGroup: /system.slice/machine-boom.scope/system.slice/dbus.service
           └─58 /usr/bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation

Mar 02 06:29:08 boom systemd[1]: Starting D-Bus System Message Bus...
Mar 02 06:29:08 boom systemd[1]: Started D-Bus System Message Bus.
Mar 02 06:29:08 boom dbus-daemon[58]: Unknown username "tlsdate-dbus" in message bus configuration file
Mar 02 06:29:08 boom dbus-daemon[58]: dbus[58]: [system] Successfully activated service 'org.freedesktop.systemd1'
Mar 02 06:29:08 boom dbus[58]: [system] Successfully activated service 'org.freedesktop.systemd1'
boom / # touch /etc/systemd/system/foo.service
```

Now you have a rw working coreos instance. Fully managed by systemd. 

Easy to clean up:

```
boom / # exit
logout
$ sudo systemctl stop cic-boom
```
