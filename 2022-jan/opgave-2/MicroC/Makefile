build:
	~/bin/fsharp/fslex --unicode CLex.fsl
	~/bin/fsharp/fsyacc --module CPar CPar.fsy

run: build
	fsharpi -r ~/bin/fsharp/FsLexYacc.Runtime.dll Absyn.fs CPar.fs CLex.fs Parse.fs Interp.fs ParseAndRun.fs
