# server-tuning-mongodb
server tuning

1.- ir a la ruta y abrir el archivo:
``/etc/systemd/user.conf``

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

