build:
	~/bin/fsharp/fslex --unicode CLex.fsl
	~/bin/fsharp/fsyacc --module CPar CPar.fsy

compile: build
	# fsharpi -r ~/bin/fsharp/FsLexYacc.Runtime.dll Absyn.fs CPar.fs CLex.fs Parse.fs Machine.fs Comp.fs ParseAndComp.fs
	# I MODIFIED ListCC.fs to see AST!
	fsharpc --standalone -r ~/bin/fsharp/FsLexYacc.Runtime.dll Absyn.fs CPar.fs CLex.fs Parse.fs Machine.fs Comp.fs ListCC.fs -o listcc.exe
	mono listcc.exe exam10.lc

# docker-build:
# 	docker build -t prdat .
#
# docker-run:
# 	docker run --name prdat --rm -it -v "$(shell pwd)":/hygge prdat
#
# docker: docker-build docker-run

compile-vm:
	gcc -Wall -g -o listmachine ./ListVM/ListVM/listmachine.c

run-vm: compile-vm
	./listmachine ./exam10.out
