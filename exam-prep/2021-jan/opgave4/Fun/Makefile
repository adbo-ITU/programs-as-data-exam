build:
	~/bin/fsharp/fslex --unicode FunLex.fsl
	~/bin/fsharp/fsyacc --module FunPar FunPar.fsy

run: build
	fsharpi -r ~/bin/fsharp/FsLexYacc.Runtime.dll Absyn.fs FunPar.fs FunLex.fs Parse.fs HigherFun.fs ParseAndRunHigher.fs
