# Command Line 1

## Introduction

### What is the command line?
The Command Line Interface (CLI) is a way of interacting with your computer using text-based commands. This is also referred to as a Text User Interface (TUI) which is different from the way most people interact with their computers, using their mouse and a Graphical User Interface (GUI).

### Why should I use it?
Once you become comfortable with the basics, it can be a more powerful way to use your computer. You're able to do many things more quickly and *programatically*. It is especially useful if you need to do something repetitively or in bulk.

### Example Use Cases
- find all files in a folder that contain a phrase
- rename several files at the same time
- resize or crop several images or pdfs
- download a list of urls

### Anatomy of a Command
`<command> -<options> <arguments>`

* `<command>` is the action we want the computer to take. This is the program that you are running.
* `<options>` (or "flags") modify the behavior of the command
* `<arguments>` (or positional arguments) are the things we want the command to act on. They are the "inputs" to the program that you are running. You can view the manual for a command by typing `man <command>`. Sometimes, you can view a help page by typing `<command> --help`.

#### `df`

As an example, let's take disect the `df` (disk free) command. This command shows how much disk space is used and remaining on your computer.

If you run

```
df
```

by itself, it will show you a result that looks similar to:

```
Filesystem    512-blocks      Used Available Capacity iused               ifree %iused  Mounted on
/dev/disk1s1   488555536 438995376  33577784    93% 3186543 9223372036851589264    0%   /
devfs                411       411         0   100%     712                   0  100%   /dev
/dev/disk1s4   488555536  14681200  33577784    31%       7 9223372036854775800    0%   /private/var/vm
map -hosts             0         0         0   100%       0                   0  100%   /net
map auto_home          0         0         0   100%       0                   0  100%   /home
```

The output isn't all that readable. I don't know how to translate how "512-blocks" to gigabytes in my head.

We can use the `-h` option/flag to make the output human readable text.

```
df -h
```

The output now looks like this:

```
Filesystem      Size   Used  Avail Capacity iused               ifree %iused  Mounted on
/dev/disk1s1   233Gi  209Gi   16Gi    93% 3186562 9223372036851589245    0%   /
devfs          206Ki  206Ki    0Bi   100%     712                   0  100%   /dev
/dev/disk1s4   233Gi  7.0Gi   16Gi    31%       7 9223372036854775800    0%   /private/var/vm
map -hosts       0Bi    0Bi    0Bi   100%       0                   0  100%   /net
map auto_home    0Bi    0Bi    0Bi   100%       0                   0  100%   /home
```

We can see above that I only have 16 gigabytes remaining on my main hard drive. Yikes!

#### `ping`

Let's also disect the `ping` command. You might hear people in normal converation saying "Can you *ping* me when you're back in the office?". The word originates from this old unix command. `ping` sends packets of data to an ip address every few seconds in order to check for a response. One use case for this this command can be used to check if a website is down or not or see how quickly it responds.

In this command, we'll start by using a single position argument.

```
ping google.com
```

You can see a response that looks like:

```
PING google.com (172.217.12.142): 56 data bytes
64 bytes from 172.217.12.142: icmp_seq=0 ttl=55 time=14.140 ms
64 bytes from 172.217.12.142: icmp_seq=1 ttl=55 time=18.354 ms
64 bytes from 172.217.12.142: icmp_seq=2 ttl=55 time=12.728 ms
64 bytes from 172.217.12.142: icmp_seq=3 ttl=55 time=18.537 ms
64 bytes from 172.217.12.142: icmp_seq=4 ttl=55 time=12.509 ms
64 bytes from 172.217.12.142: icmp_seq=5 ttl=55 time=14.982 ms
64 bytes from 172.217.12.142: icmp_seq=6 ttl=55 time=11.185 ms
64 bytes from 172.217.12.142: icmp_seq=7 ttl=55 time=26.755 ms
64 bytes from 172.217.12.142: icmp_seq=8 ttl=55 time=11.612 ms
64 bytes from 172.217.12.142: icmp_seq=9 ttl=55 time=10.857 ms
64 bytes from 172.217.12.142: icmp_seq=10 ttl=55 time=13.876 ms
...
```

This command will keep going on forever sending packets of data to google.com and getting back a response each time. If we want the command to terminate after some number of iterations, we can use the `-c` count option/flag.

```
ping -c 5 google.com
```

The output should look similar to:

```
PING google.com (172.217.7.14): 56 data bytes
64 bytes from 172.217.7.14: icmp_seq=0 ttl=55 time=15.656 ms
64 bytes from 172.217.7.14: icmp_seq=1 ttl=55 time=13.808 ms
64 bytes from 172.217.7.14: icmp_seq=2 ttl=55 time=12.510 ms
64 bytes from 172.217.7.14: icmp_seq=3 ttl=55 time=12.845 ms
64 bytes from 172.217.7.14: icmp_seq=4 ttl=55 time=10.901 ms

--- google.com ping statistics ---
5 packets transmitted, 5 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 10.901/13.144/15.656/1.567 ms
```

You can use the `man` command to understand all the different options that can be used with `ping`.

```
man ping
```

Use your arrow keys to move up and down and press `q` to exit the man page.

The output should look like:

```man
PING(8)                   BSD System Manager's Manual                  PING(8)

NAME
     ping -- send ICMP ECHO_REQUEST packets to network hosts

SYNOPSIS
     ping [-AaCDdfnoQqRrv] [-b boundif] [-c count] [-G sweepmaxsize] [-g sweepminsize] [-h sweepincrsize] [-i wait]
          [-k trafficclass] [-K netservicetype] [-l preload] [-M mask | time] [-m ttl] [-P policy] [-p pattern]
          [-S src_addr] [-s packetsize] [-t timeout] [-W waittime] [-z tos] [--apple-connect] [--apple-time] host
     ping [-AaDdfLnoQqRrv] [-b boundif] [-c count] [-I iface] [-i wait] [-k trafficclass] [-K netservicetype] [-l preload]
          [-M mask | time] [-m ttl] [-P policy] [-p pattern] [-S src_addr] [-s packetsize] [-T ttl] [-t timeout]
          [-W waittime] [-z tos] [--apple-connect] [--apple-time] mcast-group

DESCRIPTION
     The ping utility uses the ICMP protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from a host
     or gateway.  ECHO_REQUEST datagrams (``pings'') have an IP and ICMP header, followed by a ``struct timeval'' and then
     an arbitrary number of ``pad'' bytes used to fill out the packet.  The options are as follows:

     -A      Audible.  Output a bell (ASCII 0x07) character when no packet is received before the next packet is transmit-
             ted.  To cater for round-trip times that are longer than the interval between transmissions, further missing
             packets cause a bell only if the maximum number of unreceived packets has increased.

     -a      Audible.  Include a bell (ASCII 0x07) character in the output when any packet is received.  This option is
             ignored if other format options are present.
...
```

As we can see from reading the documentation above, if we use the `-a` flag, `ping` will beep on each iteration.

```
ping -a google.com
```

Sure enough, running the command will make your computer start beeping.

Now that you have an understanding of option/flags vs. positional arguments, let's check out some other basic commands you can use on the command line.

## Basic Commands

### `whomai`
* prints your username to the terminal

### `hostname`
* prints your computer's name to the terminal

### `echo`
* example usage: `echo "Hello, World"`
* prints a text string (denoted by quotes) to the terminal

### `man`
* example usage: `man <name_of_command>`
* shows you the **man**ual page - get help on how to use any command
* press `q` to quit

### `uname`
* example usage: `uname -a`
* shows you the operating system name

### `curl`
* example usage 1: `curl 'https://api.ipify.org'`
* example usage 2: `curl 'http://dhrumilmehta.com'`
* downloads and shows you the source code of a website

