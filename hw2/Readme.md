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
        
        LDA     INDEX
        ADD     THREE
        STA     INDEX   
        COMP    THUN
        
        JLT     LOOP
        
VALUE   RESW    1       .reserves word
INDEX   RESW    1
ZERO    WORD    0       
THREE   WORD    3
THUN    WORD    300     
ARRAY   RESW    100
        END     hw2_2
</pre>

