# Ramanujan-Numbers
Assembly code [SimpleRISC] to compute second ramanujan number
```c
          .text
          .globl __ start 
__ start:
          mov r5, 0    /*temp*/
          mov r0, 0    /*flag*/
          mov r1, 0    /*num1*/
          mov r2, 0    /*num2*/ 
          mov r3, 0    /*result*/
          mov r4, 0    /*current num*/
.loop0:
          add r4, 1
          mov r1, 0
.loop1:
          add r1, 1
          mov r2, 0
.loop2:
          add r2, 1
          b .sumofcube 
.continue:
          cmp r4,r3
          beq .found
.contd:
          cmp r0,2
          beq .return
          cmp r1,r2
          blt .loop2
          beq .loop1
          cmp r1,r2
          beq .loop0

.sumofcube:
          mov r5,r1
          mul r5,r1
          mul r5,r1
          mov r3,r5
          mov r5,r2
          mul r5,r2
          mul r5,r2
          add r3,r5
          b .continue



.found:
          add r0, 1
          b .contd
.return:
          ret r4

##
##    ##
```
