all: foo.c bar.c foobar.c main.c
	gcc -c -Wall -fPIC foo.c bar.c foobar.c
	gcc -shared -o libfoo.so foo.o
	gcc -shared -o libbar.so bar.o
	gcc -shared -o libfoobar.so foobar.o -L. -lfoo -lbar -Wl,-rpath,'$$ORIGIN'
	gcc -c -Wall main.c
	gcc -o prog main.o -L. -lfoobar -Wl,-rpath,'$$ORIGIN'

.PHONY: clean

clean:
	@rm -rf *.o *.so prog
