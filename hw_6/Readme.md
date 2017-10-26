hw_6

<pre>
SUM	START	4000
FIRST	LDX    ZERO
		LDA    ZERO
LOOP	ADD 	TABLE,X
		TIX	COUNT
		JLT 	LOOP
		STA 	TOTAL
		RSUB
TABLE 	RESW	2000
COUNT 	RESW 	1
ZERO    WORD  0
TOTAL 	RESW 	1
		END 	FIRST
</pre>

## re-formatted
<pre>
SUM	    START 4000    .note
FIRST	  LDX   ZERO    .note
		    LDA   ZERO    .note
LOOP	  ADD 	TABLE,X .note
		    TIX	  COUNT   .note
		    JLT 	LOOP    .note
		    STA 	TOTAL   .note
		    RSUB          .note
TABLE 	RESW	2000    .note
COUNT   RESW  1       .note
ZERO    WORD  0       .note
TOTAL 	RESW 	1       .note
		    END 	FIRST   .note
</pre>
