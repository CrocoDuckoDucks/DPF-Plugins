#!/usr/bin/make -f
# Makefile for DISTRHO Plugins #
# ---------------------------- #
# Created by falkTX
#

# --------------------------------------------------------------
# Project name, used for binaries

NAME = Nekobi

# --------------------------------------------------------------
# Files to build

OBJS_DSP = \
	DistrhoPluginNekobi.cpp.o

OBJS_UI  = \
	DistrhoArtworkNekobi.cpp.o \
	DistrhoUINekobi.cpp.o

# --------------------------------------------------------------
# Do some magic

include ../Makefile.Nekobi.mk

# --------------------------------------------------------------
# Enable all possible plugin types

ifeq ($(HAVE_DGL),true)
ifeq ($(HAVE_JACK),true)
TARGETS += jack
endif
endif

ifeq ($(LINUX),true)
TARGETS += dssi_dsp
ifeq ($(HAVE_DGL),true)
ifeq ($(HAVE_LIBLO),true)
TARGETS += dssi_ui
endif
endif
endif

ifeq ($(HAVE_DGL),true)
TARGETS += lv2_sep
else
TARGETS += lv2_dsp
endif

TARGETS += vst

all: $(TARGETS)

# --------------------------------------------------------------
