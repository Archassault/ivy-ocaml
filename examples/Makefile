# $Id: Makefile 3442 2011-01-03 17:39:47Z hattenberger $

OCAMLC = ocamlc -I .. 
OCAMLMLI = ocamlc -I .. 
OCAMLOPT = ocamlopt
OCAMLDEP=ocamldep

all: ivyprobe.out glibivyprobe.out

ivyprobe.out : ivyprobe.cmo ivyivyprobe.cmo
	$(OCAMLC) -custom -o $@ unix.cma ivy-ocaml.cma $^

glibivyprobe.out : ivyprobe.cmo glibivyprobe.cmo
	$(OCAMLC) -custom -o $@ unix.cma glibivy-ocaml.cma $^

#tkivyprobe.out : ivyprobe.cmo tkivyprobe.cmo
#	$(OCAMLC) -custom -o $@ unix.cma -I +labltk labltk.cma -I . $^
#tkivyprobe.cmo : OCAMLFLAGS=-I +labltk

%.cmo : %.ml
	$(OCAMLC) -c $<

clean:
	\rm -f *.cm* *.o *.a .depend *~ *.out *.opt .depend *.so

.depend:
	$(OCAMLDEP) $(INCLUDES) *.mli *.ml > .depend

include .depend
