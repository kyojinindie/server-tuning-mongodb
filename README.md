# server-tuning-mongodb
## Ulimit

1.- ir a la ruta y abrir el archivo:
``sudo vi /etc/systemd/user.conf``

2.-dar la siguiente configuración:

[Manager]

```text
DefaultLimitCPU=unlimited
DefaultLimitFSIZE=unlimited
DefaultLimitNOFILE=200000
DefaultLimitAS=unlimited
DefaultLimitNPROC=200000
DefaultLimitMEMLOCK=unlimited
```

3.- ir a la ruta y abrir el archivo:
``sudo vi /etc/security/limits.conf``

4.-dar la siguiente configuración:

```text
DefaultLimitCPU=unlimited
DefaultLimitFSIZE=unlimited
DefaultLimitNOFILE=200000
DefaultLimitAS=unlimited
DefaultLimitNPROC=200000
DefaultLimitMEMLOCK=unlimited
```

3.- ir a la ruta y abrir el archivo:
``sudo vi /etc/security/limits.conf``

4.-dar la siguiente configuración:

```text
*                soft     nproc          200000
*                hard     nproc          200000
*                soft     nofile         200000
*                hard     nofile         200000
*                soft     fsize          -1
*                hard     fsize          -1
```

6.- Comprobar cambios

``ulimit -a``

```text
core file size          (blocks, -c) 0
data seg size           (kbytes, -d) unlimited
scheduling priority             (-e) 0
file size               (blocks, -f) unlimited
pending signals                 (-i) 257153
max locked memory       (kbytes, -l) 65536
max memory size         (kbytes, -m) unlimited
open files                      (-n) 200000
pipe size            (512 bytes, -p) 8
POSIX message queues     (bytes, -q) 819200
real-time priority              (-r) 0
stack size              (kbytes, -s) 8192
cpu time               (seconds, -t) unlimited
max user processes              (-u) 200000
virtual memory          (kbytes, -v) unlimited
file locks                      (-x) unlimited
```
## Disable Transparent Huge Pages (THP)

1.- crear el siguiente archivo:

``sudo touch /etc/systemd/system/disable-transparent-huge-pages.service``

2.- pegar en el archivo:

```text
[Unit]
Description=Disable Transparent Huge Pages (THP)
DefaultDependencies=no
After=sysinit.target local-fs.target
Before=mongod.service
[Service]
Type=oneshot
ExecStart=/bin/sh -c 'echo never | tee /sys/kernel/mm/transparent_hugepage/enabled > /dev/null'
[Install]
WantedBy=basic.target
```
3.- tirar el siguiente comando

``sudo systemctl daemon-reload``

4.- iniciar el servicio

``sudo systemctl start disable-transparent-huge-pages``

5.- verificar THP

``cat /sys/kernel/mm/transparent_hugepage/enabled``

