```sh
tar -cf termux_data.tar home usr
```

Push the file to your Android device:

```sh
adb push termux_data.tar /sdcard/Download
```

```sh
adb shell
```

```sh
su
```

Then, under `su` mode:

```sh
cd /data/data/com.termux/files
rm -rf *
tar -xf /sdcard/Download/termux_data.tar
chmod -R 777 .
```

Don't forget to restart Termux.
