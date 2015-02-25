PREFIX = /usr/local
DEST_HEADER = $(PREFIX)/include/

TARGET = librpi_gpio.a
SRCS = rpi_gpiolib.c
OBJS = $(subst .c,.o,$(SRCS))
HEADERS = rpi_gpiolib.h rpi_gpio.h

RM := rm
CC := gcc
AR := ar

CPPFLAGS = -g -fPIC -O2 -I./
LDFLAGS = -g -fPIC
ARFLAGS = cr

$(TARGET): $(OBJS)
	$(AR) $(ARFLAGS) $@ $^$(LOADLIBES)

install : $(TARGET) $(HEADERS)
	mkdir -p $(PREFIX)/lib/
	install -m644 $(TARGET) $(PREFIX)/lib/$(TARGET)
	mkdir -p $(DEST_HEADER)
	install -m644 $(HEADERS) $(DEST_HEADER)

.PHONY: clean

clean:
	$(RM) $(OBJS) $(TARGET)
