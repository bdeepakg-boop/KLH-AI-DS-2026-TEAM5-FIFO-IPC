CC ?= gcc
CFLAGS ?= -O2 -Wall -Wextra -std=c11
BUILD := build
GTK_CFLAGS := $(shell pkg-config --cflags gtk+-3.0)
GTK_LIBS := $(shell pkg-config --libs gtk+-3.0)

.PHONY: all clean
all: $(BUILD)/ipc_lab $(BUILD)/pipe_communication $(BUILD)/fifo_communication

$(BUILD):
	mkdir -p $(BUILD)

$(BUILD)/ipc_lab: backend/ipc_gui.c | $(BUILD)
	$(CC) $(CFLAGS) $(GTK_CFLAGS) $< -o $@ $(GTK_LIBS)

$(BUILD)/pipe_communication: backend/pipe_communication.c | $(BUILD)
	$(CC) $(CFLAGS) $< -o $@

$(BUILD)/fifo_communication: backend/fifo_communication.c | $(BUILD)
	$(CC) $(CFLAGS) $< -o $@

clean:
	rm -rf $(BUILD)
