#
#
CPP = c++
CPPFLAGS = -Wall -Wextra -Werror -I$(INCDIR) -std=c++17
MAKEFLAGS += -s

INCDIR = inc
SRCDIR = src
OBJDIR = obj

SRCS = $(SRCDIR)/main.cpp \
	$(SRCDIR)/MateriaSource.cpp \
	$(SRCDIR)/Ice.cpp \
	$(SRCDIR)/Cure.cpp \
	$(SRCDIR)/Character.cpp \
	$(SRCDIR)/Interfaces/ICharacter.cpp \
	$(SRCDIR)/Interfaces/IMateriaSource.cpp \
	$(SRCDIR)/Abstracts/AMateria.cpp

OBJS = $(SRCS:$(SRCDIR)/%.cpp=$(OBJDIR)/%.o)
# OBJS = $(addprefix $(OBJDIR)/, $(notdir $(SRCS:.cpp=.o)))

NAME = interface

$(NAME): $(OBJS)
	@printf "[.]   📦 Compiling '\033[33m$(NAME)\033[0m'...\r"
	$(CPP) $(CPPFLAGS) $(OBJS) -o $(NAME)
	@echo "🚀 '\033[33m$(NAME)\033[0m' compiled \033[32msuccessfully\033[0m!"

$(OBJDIR)/%.o: $(SRCDIR)/%.cpp
	@mkdir -p $(dir $@)
	$(CPP) $(CPPFLAGS) -c $< -o $@

$(OBJDIR):
	@mkdir -p $(OBJDIR)

all: $(NAME)

clean:
	rm -f $(OBJS)
	rm -rf $(OBJDIR)

fclean: clean
	@printf "[.]   🧹 Removing '\033[33m$(NAME)\033[0m' build...\r"
	rm -f $(NAME)
	printf "[✅]  🧹 Removed '\033[33m$(NAME)\033[0m' build...  \n"

re: fclean all

.PHONY: all clean fclean re
