dnl Copyright (C) 2016 Red Hat, Inc.
dnl
dnl This program is free software; you can redistribute it and/or modify
dnl it under the terms of the GNU General Public License as published by
dnl the Free Software Foundation; version 2 of the License.
dnl
dnl This program is distributed in the hope that it will be useful,
dnl but WITHOUT ANY WARRANTY; without even the implied warranty of
dnl MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
dnl GNU General Public License for more details.
dnl
dnl You should have received a copy of the GNU General Public License
dnl along with this program; if not, write to the Free Software
dnl Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston,
dnl MA  02110-1301, USA.  A copy of the GNU General Public License is
dnl also available at http://www.gnu.org/copyleft/gpl.html.

define([VERSION_NUMBER], [4.4.9])
define([RELEASEVER], [1])

AC_INIT([ovirt-node-ng-image-update], VERSION_NUMBER, [devel@ovirt.org])
AM_INIT_AUTOMAKE([-Wall -Werror foreign -Wno-portability tar-pax no-dependencies])

PACKAGE_RPM_VERSION="VERSION_NUMBER"
AC_SUBST([PACKAGE_RPM_VERSION])

PACKAGE_RPM_RELEASE="1.$(date +%Y%m%d).0"
AC_SUBST([PACKAGE_RPM_RELEASE])

FINALBUILD=True
AC_SUBST([FINALBUILD])

IMAGENAME="ovirt-node-ng-image"
AC_SUBST([IMAGENAME])

AC_ARG_WITH([distro],
    [AS_HELP_STRING([--with-distro=distro], [Base node-ng on distro (default: prolinux)])],
    [DISTRO="$withval"],
    [DISTRO="prolinux"])
AC_SUBST([DISTRO])

AC_ARG_WITH([bootisourl],
    [AS_HELP_STRING([--with-bootisourl=URL],
        [boot ISO url (default: http://prolinux-repo.tmaxos.com/prolinux/.8.2/os/x86_64/images/boot.iso)])],
    [BOOTISOURL="$withval"],
    [BOOTISOURL="http://prolinux-repo.tmaxos.com/prolinux/.8.2/os/x86_64/images/boot.iso"])
AC_SUBST([BOOTISOURL])

AC_ARG_WITH([bootiso],
    [AS_HELP_STRING([--with-bootiso=NAME],
        [boot ISO name (default: basename BOOTISOURL var)])],
    [BOOTISO="$withval"],
    [BOOTISO="$(basename $BOOTISOURL)"])
AC_SUBST([BOOTISO])

AC_ARG_WITH([tmpdir],
    [AS_HELP_STRING([--with-tmpdir=DIR],
        [path to TMP directory (default: /tmp)])],
    [TMPDIR="$withval"],
    [TMPDIR="/var/tmp"])
AC_SUBST([TMPDIR])

AC_ARG_WITH([ovirt-release-rpm-url],
    [AS_HELP_STRING([--with-ovirt-release-rpm-url=URL],
        [URL to the ovirt-release rpm (default: http://hypervm-repo.tmaxcloud.com/pub/HyperVM-22/rpm/pl8/ovirt-release44-4.4.9.3-1.0.2.el8.noarch.rpm)])],
    [OVIRTRELEASERPMURL="$withval"],
    [OVIRTRELEASERPMURL="http://hypervm-repo.tmaxcloud.com/pub/HyperVM-22/rpm/pl8/ovirt-release44-4.4.9.3-1.0.2.el8.noarch.rpm"])
AC_SUBST([OVIRTRELEASERPMURL])

AC_CONFIG_FILES([
	Makefile
])

AC_OUTPUT
