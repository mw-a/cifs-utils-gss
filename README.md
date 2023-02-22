cifs-utils-gss
==============

Patches and packages of cifs-utils including support for GSS-API which allows to
employ gssproxy for ticket retrieval. This historically required patching. As
of cifs-utils version 7.0 this is now upstream. Packages here backport the
functionality to various distro releases.

If no useable ticket cache or keytab can be found, credential search falls on
through into credential handling but then diverts into GSS routines. If no
gssproxy is available this will still error out silently because no ticket
cache is available. With gssproxy enabled, credentials can be retrieved from
there and allow unattended access to shares e.g. from batch jobs.

See
https://git.samba.org/cifs-utils.git/?p=cifs-utils.git;a=commitdiff;h=e2430c005d92e5ab19a63976c64c4294095c3ac7
for details.
