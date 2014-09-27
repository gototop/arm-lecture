CC	= arm-linux-gnueabihf-gcc
CFLAGS	= -O0 -ggdb -Wall
LDFLAGS = -fno-stack-protector

objects	= example5.o

default: example5

.PHONY: default clean

example5: $(objects)
	$(CC) -o $@ $^

example5.o: example5.c

%.o: %.c
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o $@ $<

clean:
	rm -f $(objects) example5
	rm -f example5_1.o example5_1
	rm -f example5_2.o example5_2
	rm -f example5_3.o example5_3

qemu:
	qemu-arm -L /usr/arm-linux-gnueabihf ./example5

ex1:
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o example5_1.o example5_1.c
	$(CC) -o example5_1 example5_1.o

ex2:
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o example5_2.o example5_2.c
	$(CC) -o example5_1 example5_1.o

ex3:
	$(CC) -c $(CFLAGS) $(LDFLAGS) -o example5_3.o example5_3.c
	$(CC) -o example5_1 example5_1.o


