<pre>
(5 points) Write a program only using SIC instructions for the following. Define three one-word
constants ALPHA, BETA and GAMMA, initialized to 1, 2 and 3, respectively. Now, perform the operation
BETA + GAMMA * ALPHA and store the final result into a memory word named RESULT. You may
refer to Appendix A of the book for appropriate instructions required for this program.
☞ You may receive zero point if your program cannot be used to generate error-free lst and obj files
in sicasm. Test your program thoroughly using sicasm and sicsim.
2. (5 points) Textbook, Page 40, Problem 8. You may refer to Appendix A of the book for appropriate
instructions required for this program.
☞ You may receive zero point if your program cannot be used to generate error-free lst and obj files
in sicasm. Test your program thoroughly using sicasm and sicsim.
</pre>

<pre>
        START 100

        LDA   BETA    .load accumulator with BETA .A <-- (BETA) 
        ADD   GAMMA   .Add GAMA to the accumulator .A <-- (A) + (GAMMA)
        SUB   ALPHA   .Subtract ALPHA from the accumulator .A <-- (A) - ALPHA

        STA   RESULT  .Store the accumulator in RESULT word .RESULT <-- (A)

ALPHA   Word  1       .?what does this mean? .ALPHA = 1
BETA    Word  2       .?what does this mean? .BETA = 2
GAMMA   Word  3       .?what does this mean? .GAMMA = 3

RESULT  RESW  1       .RESERVES ONE WORD declare variable 
        END
</pre>

<pre>.
hw2_2   START   100
        
        LDA     ZERO    .load accumulator with zero             .A <--(ZERO)
        STA     Value   .store accumulator into Value           .VALUE <--(A)
        
        LDA     ZERO    .load accumulator with zero             .A <-- (ZERO)
        STA     INDEX   .store accumulator into index           .INDEX <-- (A)
        LDX     INDEX   .?what is an x??.load x into index.     .X <-- (INDEX)
        
LOOP    LDA     VALUE   .load accumulator with value            .A <-- (VALUE)
        LDX     INDEX   .?what is an x??.load x into index.     .X <--(INDEX)
        STA     ARRAY,X 
        
        LDA     INDEX   .load accumulator with index.           .A <--(INDEX)
        ADD     THREE   .add three to the accumulator           .A <-- (A) + 3
        STA     INDEX   .store the accumulator into index       .INDEX <-- (A) 
        COMP    THUN                                    .(A):(THUN, THUN+1, THUN+2) & SET CC
        
        JLT     LOOP                                    .if CC is <, then "JUMP to LOOP"
        
VALUE   RESW    1       .reserves word
INDEX   RESW    1       .reserves word
ZERO    WORD    0       .zero=0
THREE   WORD    3       .Three=3
THUN    WORD    300     .THUN = 300
ARRAY   RESW    100     .reserves an array of 100 words
        END     hw2_2   .end program
</pre>
## put in a contender
<pre>
.The following program initializes an array of 100 words with the integer 0.
INIT_ARRAY 	START	100 		.Load the program at loc 100
		LDA	ZERO 		.A <--(Zero)
		STA	VALUE2ST	.VALUE2ST	

		LDA	ZERO 		.A <--(Zero)
		STA	INDEX 		.INDEX <--(A)
		LDX	INDEX		.X <-- (A)

LOOP_START	LDA	VALUE2ST	.A <--(VALUE2ST)	

		LDX	INDEX 		.A <-- (INDEX)
		ADD	THREE 		.A <-- (A) + 3
		STA	INDEX  		.INDEX <-- (A)
		COMP	THREEHUNDRED    .(A) : (THREEHUNDRED, THREEHUNDRED+1, THREEHUNDRED+2) and set CC accordingly

		JLT	LOOP_START	.if CC is <, then jump to LOOP_START

VALUE2ST	RESW	1		.Reserve a word and call it VALUE2ST
INDEX		RESW	1		.Reserve a word and call it INDEX
ALPHA		RESW	100		.Reserve an array of 100 words and call it SRC_ARRAY

ZERO		WORD	0		.Define a word constant initialized to 0
ONE		WORD	1		.Define a word constant initialized to 1
THREE		WORD	3		.Define a word constant initialized to 3
THREEHUNDRED	WORD	300		.Define a word constant initialized to 300
		END	INIT_ARRAY	.End of program
</pre>
