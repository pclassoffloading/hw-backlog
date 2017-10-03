<pre>
SUM	START	0
FIRST	LDX    #0
		LDA    #0
		+LDB   #TABLE2
		BASE 	TABLE2
LOOP	ADD 	TABLE,X
		ADD 	TABLE2,X
		TIX	COUNT
		JLT 	LOOP
		+STA 	TOTAL
		RSUB
COUNT 	RESW 	1
TABLE 	RESW	2000
TABLE2 	RESW 	2000
TOTAL 	RESW 	1
		END 	FIRST
</pre>

## re-formatted
<pre>
SUM	    START 0       .note
FIRST	  LDX   #0      .note
		    LDA   #0      .note
		    +LDB  #TABLE2 .note
		    BASE 	TABLE2  .note
LOOP	  ADD 	TABLE,X .note
		    ADD 	TABLE2,X.note
		    TIX	  COUNT   .note
		    JLT 	LOOP    .note
		    +STA 	TOTAL   .note
		    RSUB          .note
COUNT 	RESW 	1       .note
TABLE 	RESW	2000    .note
TABLE2 	RESW 	2000    .note
TOTAL 	RESW 	1       .note
		    END 	FIRST   .note
</pre>
