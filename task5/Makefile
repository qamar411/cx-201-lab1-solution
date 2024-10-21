# Makefile for task4

# Variables
CC = gcc
CFLAGS = -Wall
SRC = main.c inc1/math_utils.c inc2/string_utils.c
OBJ = $(SRC:.c=.o)  # Object files
BUILD_DIR = build

# Default target
all: $(BUILD_DIR)/app

# Link object files to create the final executable
$(BUILD_DIR)/app: $(OBJ)
	@mkdir -p $(BUILD_DIR)  # Create build directory if it doesn't exist
	@echo "Linking object files..."
	$(CC) -o $@ $^

# Compile source files to object files
%.o: %.c
	@echo "Compiling $<..."
	$(CC) $(CFLAGS) -c $< -o $@

# Run target
run: $(BUILD_DIR)/app
	@echo "Running..."
	@./$(BUILD_DIR)/app

# Clean target
clean:
	@echo "Cleaning up..."
	rm -rf $(BUILD_DIR)

# Help target
help:
	@echo "Usage: make [target]"
	@echo "Targets:"
	@echo "  all     - Compile the project"
	@echo "  run     - Run the compiled executable"
	@echo "  clean   - Remove build files"
	@echo "  help    - Display this help message"

# Declare dependencies
.PHONY: all run clean help
