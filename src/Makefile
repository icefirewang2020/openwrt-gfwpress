#termux make file
TARGET = gfwpress
CC = clang
CFLAGS = -v -O3 -Wall -std=gnu89
SRCS = encrypt.c client.c
OBJS = $(SRCS:.c=.o)
LFLAGS = -lssl -lcrypto
LIBS = -fuse-ld=gold

.PHONY: depend clean

all: $(OBJS)
	$(CC) $(CFLAGS) $(INCLUDES) -o $(TARGET) $(OBJS) $(LFLAGS) $(LIBS)

.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $<  -o $@

clean:
	$(RM) *.o *~ $(TARGET)

depend: $(SRCS)
	makedepend $(INCLUDES) $^

# DO NOT DELETE THIS LINE -- make depend needs it