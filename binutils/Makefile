#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License, Version 1.0 only
# (the "License").  You may not use this file except in compliance
# with the License.
#
# You can obtain a copy of the license at COPYING
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at COPYING.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright 2017, Joyent, Inc.
#

VER =	binutils-2.31.1

include ../Makefile.defs

FETCH_URL.$(TARBALL) =	https://ftp.gnu.org/gnu/binutils

i86pc_AUTOCONF_OPTS = \
	--target=i386-pc-solaris2.11

armv8_AUTOCONF_OPTS = \
	--target=aarch64-unknown-elf
#	--target=aarch64-*-solaris2.11 \
#	--enable-ld=no

riscv_AUTOCONF_OPTS = \
	--target=riscv64-unknown-elf
#	--target=riscv64-*-solaris2.11

AUTOCONF_OPTS = \
	--prefix=/usr/gnu \
	--enable-64-bit-bfd \
	--program-prefix=g \
	--disable-nls \
	$($(ARCH)_AUTOCONF_OPTS)

PATCHES =	patches/*

AUTOCONF_ENV += \
	CC=gcc \
	CXX=g++ \
	DESTDIR=$(DESTDIR) \
	MAKE=gmake \
	CONFIG_SHELL=/bin/bash

include ../Makefile.targ
include ../Makefile.targ.autoconf
