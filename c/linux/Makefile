CFLAGS += -I common
LDFLAGS += -shared

all: build/spicl build/spidriver.so

install: all
	cp build/spi /usr/local/bin

build/spicl: linux/spi.c common/spidriver.c
	mkdir -p build/
	$(CC) -o $@ $(CPPFLAGS) $(CFLAGS) $^

build/spidriver.so: common/spidriver.c
	$(CC) $(LDFLAGS) -o $@ $(CPPFLAGS) $(CFLAGS) -fPIC $^
