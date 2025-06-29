# Makefile for C project
# Authors: A. & G. Grimaud
# License: LGPL
  
# Directory variables
SRC := src
BLD := build
BIN := bin
INC := include

# Default executable name
EXEC := add

# Compiler and flags
CC := gcc
CFLAGS := -I$(INC) -Wall -Wextra -pedantic
# Source files and object files
SRCS := $(wildcard $(SRC)/*.c)
HDRS := $(wildcard $(INC)/*.h)
OBJS := $(patsubst $(SRC)/%.c,$(BLD)/%.o,$(SRCS))

# Phony targets
.PHONY: all clean

# Target for the default executables
all: $(BIN)/$(EXEC)

# Rule to link the object files into the executables
$(BIN)/$(EXEC): $(OBJS)
  mkdir -p $(BIN)
  $(CC) $(OBJS) -o $@

# Rule to compile source files into object files
$(BLD)/%.o: $(SRC)/%.c $(HDRS)
  mkdir -p $(BLD)
  $(CC) $(CFLAGS) -c $< -o $@

# Rule to clean the generated files
clean:
  rm -rf $(BLD)/*.o $(BIN)/$(EXEC)
