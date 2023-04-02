#DEBUG		=-gflv
#LDFLAGS	= -Debug
DEP		=-depend !Depend

CFLAGS		=$(DEP) -IC: -Wa -Otime -throwback -DDEBUG=0
ASFLAGS		=$(DEP) -throwback
BCPFLAGS	=-sa -tb -ow $(DEP)
LIBS		= C:o.stubs C:o.tholib

.SUFFIXES: .o .c .s .b .^ .tab .bin .zip

.c.o:;		cc $(CFLAGS) -c -o $@ $<
.c.s:;		cc $(CFLAGS) -S -o $@ $<
.s.o:;		objasm $(ASflags) -o $@ $<
.b.^:;		bcp $(BCPFLAGS) $< -o $@
		access $@ WR/r
.o.^:;		link $(LDFLAGS) $(LIBS) $< -o $@
		squeeze -f $@
		access $@ WR/r

all:		^.mksprite

mks=		o.mksprite o.file_aff o.file_de1 o.mks_asm
^.mksprite:	$(mks)
		link $(LDFLAGS) $(LIBS) $(mks) -o $@
		squeeze -f $@
		access $@ WR/r

# Dynamic dependencies:
o.mksprite:	c.mksprite
o.mksprite:	C:h.swis
o.mksprite:	C:h.kernel
o.mksprite:	C:h.tholib
o.mksprite:	C:h.kernel
o.mksprite:	C:h.time
o.mksprite:	C:h.swis
o.mksprite:	h.mksprite
o.mksprite:	C:h.kernel
o.mksprite:	C:h.tholib
o.mksprite:	h.mks_asm
o.mksprite:	C:h.tholib
o.mksprite:	h.mksprite
o.mksprite:	h.file_aff
o.mksprite:	C:h.kernel
o.mksprite:	C:h.tholib
o.mksprite:	h.mksprite
o.mksprite:	h.file_de1
o.mksprite:	C:h.kernel
o.mksprite:	C:h.tholib
o.mksprite:	h.mksprite
o.file_aff:	c.file_aff
o.file_aff:	C:h.tholib
o.file_aff:	C:h.kernel
o.file_aff:	C:h.time
o.file_aff:	C:h.swis
o.file_aff:	h.mksprite
o.file_aff:	C:h.kernel
o.file_aff:	C:h.tholib
o.file_aff:	h.mks_asm
o.file_aff:	C:h.tholib
o.file_aff:	h.mksprite
o.file_de1:	c.file_de1
o.file_de1:	C:h.math
o.file_de1:	C:h.string
o.file_de1:	C:h.swis
o.file_de1:	C:h.kernel
o.file_de1:	C:h.tholib
o.file_de1:	C:h.kernel
o.file_de1:	C:h.time
o.file_de1:	C:h.swis
o.file_de1:	h.mksprite
o.file_de1:	C:h.kernel
o.file_de1:	C:h.tholib
o.file_de1:	h.mks_asm
o.file_de1:	C:h.tholib
o.file_de1:	h.mksprite
o.mks_asm: s.mks_asm
o.mks_asm: C:h.SWINames
o.mks_asm: s.asmhdr
o.mks_asm: s.tab8_32g
