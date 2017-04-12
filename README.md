# Static `busybox` for Android providing `syslogd` and `klogd`

Used to build a static busybox binary into AOSP to provide kernel logging,
statically linked against `musl` libc.

This is a nasty hack, and i'm not certain if the required patch is
upstreamable, or simply an unpredictable problem caused by linking against
musl and running on Android, with it's, let's say, unusual handling of
permissions, etc.
