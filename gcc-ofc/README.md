# GCC Option Flags Checker

## Description:

This tool will show you what option flags GCC enables when you pass it arguments. It's mainly geared for doing a differential comparison of different sets of optimization option flags, for example:

```
./gcc-ofc '-gcc-bin=gcc-8 -march=sandybridge -O2' '-gcc-bin=gcc-9 -march=ivybridge -O3'
```

If comparing only two options, you can pass them without using single quotes, for example:

```
./gcc-ofc -march=sandybridge -march=ivybridge
```

If passing more then two options then you will need to use single quotes. Additionally, if you want to test a different GCC version then pass the -gcc-bin=<gcc_binary_name> parameter, otherwise if you don't set this the program will default to "gcc", i.e. /usr/bin/gcc.

#### Notes:

Developed and tested on a Ubuntu 18.04 system, it should work just fine on most any Unix-like system. For color diffs you need GNU diff v3.4+, you can however change the diff program used by just changing one line of code at the bottom.

Additionally, it has soft dependencies on the lsb_release & dmidecode commands, and /proc/cpuinfo file for collecting system information. However, It should fail gracefully by simply not including that information if they are not available. 

### Example Screenshot:

![Screenshot](https://github.com/nbritton/gcc-misc/blob/master/gcc-ofc/Screenshot.png?raw=true)
