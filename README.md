# erlexec #

Execute and control OS processes from Erlang/OTP.

This project implements a C++ port program and Erlang application
that gives light-weight Erlang processes fine-grain control over
execution of OS processes.

It makes possible for an Erlang process to start, stop an OS process,
send POSIX signals, know process IDs of the started OS process, set up
a monitor and/or link to it, run interactive commands with pseudo
terminals. This application provides better control
over OS processes than built-in `erlang:open_port/2` command with a
`{spawn, Command}` option, and performs proper OS child process cleanup
when the emulator exits. 

See http://saleyn.github.com/erlexec for more information.

## SUPPORTED OS's ##
Linux, Solaris, MacOS X

## DOCUMENTATION ##
See http://saleyn.github.io/erlexec

## BUILDING ##
Make sure you have rebar (http://github.com/basho/rebar or
http://github.com/basho/rebar3) installed locally and the rebar script
is in the path.

If you are deploying the application on Linux and would like to
take advantage of exec-port running tasks using effective user IDs
different from the real user ID that started exec-port, then
make sure that libcap-dev[el] library is installed.

OS-specific libcap-dev installation instructions:

* Fedora, CentOS: "yum install libcap-devel"
* Ubuntu:         "apt-get install libcap-dev"

```
$ git clone git@github.com:saleyn/erlexec.git
$ make
```

## LICENSE ##
The program is distributed under BSD license.
Copyright (c) 2003 Serge Aleynikov <saleyn at gmail dot com>
