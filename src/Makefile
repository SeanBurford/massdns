PREFIX=/usr/local
DEPS=buffers.h  cmd.h  dns.h  flow.h  hashmap.h  list.h  massdns.h  module.h  net.h  random.h  security.h  string.h  timed_ring.h
OBJS=dns.o
BUILDFLAGS=-DHAVE_SYSINFO -DHAVE_EPOLL -DDEBUG

all:	${OBJS}
	$(CC) $(CFLAGS) -O3 -std=c11 -Wall -fstack-protector-strong ${BUILDFLAGS} main.c $^ -o ../bin/massdns ${LDFLAGS}

%.o:	%.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

clean:	
	rm -f *.o ../bin/massdns
