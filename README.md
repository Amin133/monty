# monty

# Stacks, Queues - LIFO, FIFO
# Description

Project 0x19. C - Stacks, Queues - LIFO, FIFO An interpreter for Monty ByteCode files.

# COMPILATION
$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty

# Usage
First make a file with Monty ByteCode commands

$ cat test.m
push 2
push 5
push 9
pall

Now run our interpreter with that file

$ ./monty test.m
9
5
2

# Examples
pint:

push 1
push 3
push 4
pint
Output will be: 4

pop:

push 1
push 2
push 3
pop
pall
Output will be: 2 1

swap:

push 1
push 2
push 3
swap
pall
Output will be: 2 3 1

# File Structure
1. main.c - The main function for monty interpreter.
int main(int argc, char *argv[]) - main function where program starts.
buf_struct *make_struct(char *argv[]) - make struct for buffers.
2. dl_ops.c - Doubly linked list operations.
void free_stack(stack_t *head) - free list.
3. exec_ops.c - file where commands get executed.
void exec_loop(buf_struct *a) - loop through commands and execute.
void (*get_op_func(char *s))(stack_t **stack, unsigned int line_number) - calls function.
4. check.c - extra helper functions.
int digits_only(char *str) - checks if push option is a number.
5. opcode.c - file for opcode basic commands.
stack_t *push(stack_t **head, int n) - pushes node to top of stack.
void pall(stack_t **stack, unsigned int line_n) - prints from the top of stack.
void pint(stack_t **stack, unsigned int line_n) - print only top of stack.
void pop(stack_t **stack, unsigned int line_n) - frees top of stack.
void swap(stack_t **stack, unsigned int line_n) - swap first two nodes.
6. opcode1.c - file for opcode math commands.
void add(stack_t **stack, unsigned int line_n) - add top two elements of stack.
void sub(stack_t **stack, unsigned int line_n) - subtracts top two elements of stack.
void _div(stack_t **stack, unsigned int line_n) - divide top two elements.
void mod(stack_t **stack, unsigned int line_n) - modulus top two elements.
void mul(stack_t **stack, unsigned int line_n) - multiplies top two elements.
7. opcode2.c - file for extra opcode commands.
void nop(stack_t **stack, unsigned int line_n) - does nothing.
void pchar(stack_t **stack, unsigned int line_n) - prints ascii character from head.
void pstr(stack_t **stack, unsigned int line_n) - prints string.
8.opcode3.c - file for extra opcode commands.
void rotl(stack_t **stack, unsigned int line_n) - rotate list.
void rotr(stack_t **stack, unsigned int line_n) - rotate list.
void queue(stack_t **stack, unsigned int line_n) - flips list.
9. split.c - file for tokenizing lines from file.
char **split_newline(buf_struct *a) - splits line based on newlines.
char **split_spaces(char *buff, buf_struct *a) - splits line based on spaces and tabs.

# Author
UMAR AMINA ABDULMUMIN https://github.com/Amin133/monty
