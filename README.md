# Monty Language README

This README provides an overview of the Monty language and its supported opcodes. Monty is a stack-based programming language designed for use in an interpreter. It supports various operations on a stack of integers and can be used for tasks ranging from simple arithmetic to more complex operations.

## Supported Opcodes

### Push Opcode

The `push` opcode pushes an element onto the stack.

**Usage**: `push <int>`

- `<int>` should be replaced with an integer.
- If `<int>` is not an integer or if no argument is given to `push`, an error message is printed: `L<line_number>: usage: push integer`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Pall Opcode

The `pall` opcode prints all the values on the stack, starting from the top of the stack.

**Usage**: `pall`

- If the stack is empty, nothing is printed.

### Pint Opcode

The `pint` opcode prints the value at the top of the stack, followed by a new line.

**Usage**: `pint`

- If the stack is empty, an error message is printed: `L<line_number>: can't pint, stack empty`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Pop Opcode

The `pop` opcode removes the top element of the stack.

**Usage**: `pop`

- If the stack is empty, an error message is printed: `L<line_number>: can't pop an empty stack`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Swap Opcode

The `swap` opcode swaps the top two elements of the stack.

**Usage**: `swap`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't swap, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Add Opcode

The `add` opcode adds the top two elements of the stack.

**Usage**: `add`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't add, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- The result is stored in the second top element of the stack, and the top element is removed.

### Nop Opcode

The `nop` opcode doesn't perform any operation.

**Usage**: `nop`

### Sub Opcode

The `sub` opcode subtracts the top element of the stack from the second top element of the stack.

**Usage**: `sub`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't sub, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- The result is stored in the second top element of the stack, and the top element is removed.

### Div Opcode

The `div` opcode divides the second top element of the stack by the top element of the stack.

**Usage**: `div`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't div, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- The result is stored in the second top element of the stack, and the top element is removed.
- If the top element of the stack is 0, an error message is printed: `L<line_number>: division by zero`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Mul Opcode

The `mul` opcode multiplies the second top element of the stack with the top element of the stack.

**Usage**: `mul`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't mul, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- The result is stored in the second top element of the stack, and the top element is removed.

### Mod Opcode

The `mod` opcode computes the remainder of the division of the second top element of the stack by the top element of the stack.

**Usage**: `mod`

- If the stack contains less than two elements, an error message is printed: `L<line_number>: can't mod, stack too short`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- The result is stored in the second top element of the stack, and the top element is removed.
- If the top element of the stack is 0, an error message is printed: `L<line_number>: division by zero`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Pchar Opcode

The `pchar` opcode prints the character at the top of the stack, followed by a new line.

**Usage**: `pchar`

- The integer stored at the top of the stack is treated as the ASCII value of the character to be printed.
- If the value is not within the ASCII table (man ascii), an error message is printed: `L<line_number>: can't pchar, value out of range`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.
- If the stack is empty, an error message is printed: `L<line_number>: can't pchar, stack empty`, followed by a new line, and the program exits with the status `EXIT_FAILURE`.

### Pstr Opcode

The `pstr` opcode prints the string starting at the top of the stack, followed by a new line.

**Usage**: `pstr`

- The integer stored in each element of the stack is treated as the ASCII value of the character to be printed.
- The string stops when either:
  - The stack is empty.
  - The value of an element is 0.
  - The value of an element is not within the ASCII table.
- If the stack is empty, only a new line is printed.

### Rotl and Rotr Opcodes

- The `rotl` opcode rotates the stack to the top, with the top element becoming the last one and the second top element becoming the first one.
- The `rotr` opcode rotates the stack to the bottom, with the last element becoming the top element.

**Usage**: `rotl` and `rotr`

- These opcodes do not fail.

### Stack and Queue Opcodes

- The `stack` opcode sets the format of the data to a stack (LIFO). This is the default behavior of the program.
- The `queue` opcode sets the format of the data to a queue (FIFO).

**Usage**: `stack` and `queue`

- When switching modes:
  - The top of the stack becomes the front of the queue.
  - The front of the queue becomes the top of the stack.

## Additional Features

### Brainf*ck Script

Included is a Brainf*ck script that prints "School," followed by a new line. The script is stored in the `bf` subdirectory.

### Adding and Multiplying Two Digits

There are opcodes provided for adding and multiplying two digits given by the user. These operations


Author 
Georgina Damalie
