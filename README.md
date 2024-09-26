## !

You know how Termux runs its own chroot inside your Android devices? Why need it if you'd also have a Linux Deploy deployment deployed? This project me automatically redirect my Termux console to my Linux Deploy installation in all cases.

## ?

Here's what I do to deploy my minified environment to my phone:

0. Ensure that the _Mount Namespace Mode_ in Magisk is set to _Global_.

1. Create a tar file from the repo's `./usr` directory:

```sh
tar -cf termux_data.tar usr
```

2. Push the file to the Android device:

```sh
adb push termux_data.tar /sdcard/Download
```

3. Open a root shell on the Android device:

```sh
adb shell
```

```sh
su
```

4. Then replace the files in Termux's app storage under `su` mode:

```sh
cd /data/data/com.termux/files
rm -rf *
tar -xf /sdcard/Download/termux_data.tar
chmod -R 777 .
```

5. Don't forget to restart Termux.
