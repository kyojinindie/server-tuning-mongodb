# server-tuning-mongodb
server tuning

1.- ir a la ruta y abrir el archivo:
``/etc/systemd/user.conf``

2.-reemplezar el contenido por:

#  This file is part of systemd.
# 
#  systemd is free software; you can redistribute it and/or modify it
#  under the terms of the GNU Lesser General Public License as published by
#  the Free Software Foundation; either version 2.1 of the License, or
#  (at your option) any later version.
#
# You can override the directives in this file by creating files in
# /etc/systemd/user.conf.d/*.conf.
#
# See systemd-user.conf(5) for details

[Manager]
#LogLevel=info
#LogTarget=console
#LogColor=yes
#LogLocation=no
#SystemCallArchitectures=
#TimerSlackNSec=
#DefaultTimerAccuracySec=1min
#DefaultStandardOutput=inherit
#DefaultStandardError=inherit
#DefaultTimeoutStartSec=90s
#DefaultTimeoutStopSec=90s
#DefaultRestartSec=100ms
#DefaultStartLimitIntervalSec=10s
#DefaultStartLimitBurst=5
#DefaultEnvironment=
#DefaultLimitCPU=unlimited
#DefaultLimitFSIZE=unlimited
#DefaultLimitDATA=
#DefaultLimitSTACK=
#DefaultLimitCORE=
#DefaultLimitRSS=
#DefaultLimitNOFILE=200000
#DefaultLimitAS=unlimited
#DefaultLimitNPROC=200000
#DefaultLimitMEMLOCK=unlimited
#DefaultLimitLOCKS=
#DefaultLimitSIGPENDING=
#DefaultLimitMSGQUEUE=
#DefaultLimitNICE=
#DefaultLimitRTPRIO=

