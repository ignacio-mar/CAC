.data 
texto: .asciiz "......."; el mensaje a mostrar
control: .word32 0x10000
dato: .word32 0x10008
.text
lwu $s0, dato($0)
lwu $s1, control($0)
daddi $t0,$0,9
daddi $t2,$0,0
daddi $t3,$0,7
loop: sd $t0,0($s1)
lbu $t1,0($s0)
sb $t1,texto($t2)
daddi $t2,$t2,1
daddi $t3,$t3,-1
bnez $t3,loop
daddi $t0,$0,6
sd $t0,0($s1)
daddi $t4,$0,texto
sd $t4,0($s0)
daddi $t5,$0,4
sd $t5,0($s1)
halt

