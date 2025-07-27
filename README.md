/* === Project Structure: _k3rn3lgh0st_C_l01ng_struct === */

// include/main.h
#ifndef MAIN_H
#define MAIN_H

void hello_world();

#endif // MAIN_H

// src/hello.c
#include <stdio.h>
#include "main.h"

void hello_world() {
    printf("Hello, Commander KernelGhost!\n");
}

// src/main.c
#include <stdio.h>
#include "main.h"

int main() {
    hello_world();
    return 0;
}

// Makefile
# === _k3rn3lgh0st_C_l01ng_struct ===

CC = gcc
CFLAGS = -Wall -Wextra -Iinclude
SRC = $(wildcard src/*.c)
OBJ = $(patsubst src/%.c, build/%.o, $(SRC))
BIN = bin/gh0st.exe

all: $(BIN)

$(BIN): $(OBJ)
	@mkdir -p bin
	$(CC) $(OBJ) -o $@

build/%.o: src/%.c
	@mkdir -p build
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf build/* bin/*

.PHONY: all clean

// README.md
# _k3rn3lgh0st_C_l01ng_struct

> Commander KernelGhost's C boilerplate launchpad.
> Built for speed. Fueled by `gcc`. No IDEs. No mercy.

## 🚀 Build & Run

```bash
make
./bin/gh0st.exe
```

## 🧼 Clean up

```bash
make clean
```

## 📦 Structure

- `src/` → All `.c` files
- `include/` → Header files
- `build/` → Object files (auto-generated)
- `bin/` → Final binary output
