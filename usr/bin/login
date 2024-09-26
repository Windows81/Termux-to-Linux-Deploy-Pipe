LD_ENV_PATH=$(/system/bin/su -c "cat /data/data/ru.meefik.linuxdeploy/shared_prefs/settings_conf.xml" | /system/bin/grep -o -E "env_dir[^\<]+" | /system/bin/cut -c 10-)

# Sets to the default path just in case anything happens.
if [ -z "$LD_ENV_PATH" ]; then LD_ENV_PATH=/data/user/0/ru.meefik.linuxdeploy/files; fi

/system/bin/su -c $LD_ENV_PATH/bin/linuxdeploy shell "$@"