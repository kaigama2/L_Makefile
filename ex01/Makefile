# make a Makefile and run make outside the
# SRCS directory for the rules to be implemented
# make look into SRCS directory for all .c files
# search for SRCS directory for .c files
SRCS = ft_putchar.c ft_putstr.c ft_strcmp.c ft_strlen.c ft_swap.c 
# place the root directory(srcs) before or 
# the object file or target file *.o
# and save it in SRC variable
SRC = ${addprefix ${PRE}, ${SRCS}}

# make convert .c in SRC variable into
# .o files and store it in OBJS variable
OBJS = ${SRC:.c=.o}
# store root directory(./SRCS/) in PRE
# variable
PRE = ./srcs/
# store root directory(./includes/) in 
# HEAD variable
HEAD = ./includes/
# Store random library in the variable
# NAME
NAME = libft.a

# AR variable stores ar rc command
AR = ar rc
# RM variable stores rm -f command
RM = rm -f
# LIB variable stores ranlib command
LIB = ranlib
# GCC variable stores gcc command
GCC = gcc
# CFLAGS variable stores -Wall -Wextra
# -Werror command
CFLAGS = -Wall -Wextra -Werror
# if rule equal to libft.a
all: ${NAME}

.c.o:
# -c tells compiler not to use the linker
# during compiling in order to ouput
# object files only and -I tells the 
# compiler to search the target
# (ft_putchar.o) in order of 
# the arrangement of the variable(HEAD)(OBJS)
		${GCC} ${CFLAGS} -c -I ${HEAD} $< -o ${<:.c=.o}
# if (NAME) is equal to (OBJS)
${NAME}:	${OBJS}
# make creates & replace all old object files with new object files
					${AR} ${NAME} ${OBJS}
# make creates random library
					${LIB} ${NAME}

clean:
# The rule clean should remove 
# all the temporary generated files.
# make remove all object files
					rm -f ${OBJS}
# if fclean is equal to clean
# make remove random library
# The rule fclean should be like a 
# make clean plus all the 
# binary made with make all.
fclean:		clean
					rm -f ${NAME}
# if re is equal to fclean all run
# make all
# remake all object file and random library
# The rule re should be like 
# a make fclean followed by make all.
re:					fclean all
# hidden syntax for make rules
.PHONY:		all clean fclean re