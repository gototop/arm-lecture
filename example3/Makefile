CC	= arm-linux-gnueabihf-gcc
CFLAGS	= -O3 -ggdb -Wall
LDFLAGS = -fno-stack-protector

objects	= example3.o

default: example3

.PHONY: default clean

example3: $(objects)
	$(CC) -o $@ $^

example3.o: example3.c

%.o: %.c
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o $@ $<

clean:
	rm -f $(objects) example3
	rm -f example3_1.o example3_1
	rm -f example3_2.o example3_2

qemu: example3
	qemu-arm -L /usr/arm-linux-gnueabihf ./example3

ex1:
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o example3_1.o example3_1.c 
	$(CC) -o example3_1 example3_1.o
	
ex2:
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o example3_2.o example3_2.c 
	$(CC) -o example3_2 example3_2.o
	
