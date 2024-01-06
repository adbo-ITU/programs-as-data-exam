build:
	~/bin/fsharp/fslex --unicode CLex.fsl
	~/bin/fsharp/fsyacc --module CPar CPar.fsy

compile: build
	# I MODIFIED ListCC.fs to see AST!
	fsharpc --standalone -r ~/bin/fsharp/FsLexYacc.Runtime.dll Absyn.fs CPar.fs CLex.fs Parse.fs Machine.fs Comp.fs ListCC.fs -o listcc.exe
	mono listcc.exe stack.lc

compile-vm:
	gcc -Wall -g -o listmachine ./ListVM/ListVM/listmachine.c

run-vm: compile-vm
	./listmachine ./stack.out
