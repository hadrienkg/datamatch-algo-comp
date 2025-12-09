.PHONY: all

all:
	@echo "Usage: make scoring, make <num>, or make answers-<num>"


CPPFLAGS = -std=c++17

answers-%:
	@g++ $(CPPFLAGS) tests/test$*.cpp answers.o -o test$*_sol
	@./test$*_sol
	@rm test$*_sol

scoring:
	@g++ $(CPPFLAGS) -c scoring.cc -o scoring.o


9:
	@g++ $(CPPFLAGS) -c scoring.cc -o scoring.o
	@g++ $(CPPFLAGS) tests/test$@.cpp scoring.o -o test$@
	@./test$@; rc=$$?; rm -f test$@; exit $$rc

%:
	@g++ $(CPPFLAGS) -c scoring.cc -o scoring.o
	@g++ $(CPPFLAGS) tests/test$@.cpp scoring.o -o test$@
	@sh -c 'set -e; ./test$@; rc=$$?; if [ $$rc -eq 0 ]; then echo "Test $@ passed"; else echo "Test $@ failed"; fi; rm -f test$@; exit $$rc'
