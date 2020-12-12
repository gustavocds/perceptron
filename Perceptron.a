.data

tamanhoVetor:	.word 10
vies: 	        .word 3
vetPesos:       .word 1 -2 -3 -4 -5 -6 -7 -8 -9 -11
vetEntradas:    .word 0  1  0  1  0  1  0  1  0  1 

.text


main:
  lw $s6, tamanhoVetor  
  li $t0, 0               # contador de iterações
  li $t1, 1               # step de iterações 
  lw $s2, vies            # vies do perceptron
  li $s3, 0               # somatorio do percetpron
  la $s0, vetEntradas     # ponteiro do vetor de entrada
  la $s1, vetPesos        # ponteiro do vetor de peso
  
perceptron:
	lw $s4, ($s0)         # carregando valor vetEntradas[t0]
	lw $s5, ($s1)         # carregando valor vetPesos[t0]
	mul $t2, $s4, $s5     # produto do vetEntradas[t0] x vetPesos[t0]
	add $t2, $t2, $s2     # somar o produto com o vies;
	add $s3, $s3, $t2     # acumulador do perceptron
    add $t0, $t0, $t1     # incrementar contador
	add $s0, $s0, 4       # incrementar ponteiro do vetEntradas
	add $s1, $s1, 4       # incrementar ponteiro do vetPesos
bne $s6, $t0, perceptron

li $t0, 0                 
ble $s3, $t0, negativo    # confere se o resultado é maior ou igual 0
li $a0, 1			      # indica que numero é positivo
j exit

negativo: 
	li $a0, 0			  #indica que o numero é negativo

exit:                     # finaliza programa
	
