######################
#      Makefile      #
######################

# For POSIX: $$(pwd)
# For PowerShell: $(CURDIR) 

.PHONY: all
SHELL := /bin/bash

.DEFAULT_GOAL := target

NAME := qemu-riscv64
TAGNAME := 0.0.1

target: all

all: build run

build:
	docker build -t cannonkalra/${NAME} .

run:
	docker run -it --rm --name ${NAME} cannonkalra/${NAME} bash  

attach:
	docker exec -it ${NAME} bash

push: 
	docker push cannonkalra/${NAME}:${TAGNAME}
