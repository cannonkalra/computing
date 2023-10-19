######################
#      Makefile      #
######################

# For POSIX: $$(pwd)
# For PowerShell: $(CURDIR) 

.PHONY: all
SHELL := /bin/bash

.DEFAULT_GOAL := target

filename := resume
tagname := 0.0.1

target: build

all: build 

build:
	docker build -t cannonkalra/qemu-riscv64 .

push: 
	docker push cannonkalra/qemu-riscv64:${tagname}