##move_and_collide
##### Faz com que o personagem se mova e consiga colidir com algo

	move_and_collide(hveloc, vveloc, obj_parede)


##floor 
#####auxilia para dividir a tela em 4 lados

	dir = floor((point_direction(x, y, mouse_x, mouse_y)+45)/90)

##Point_direction
##### Captura onde o lado de algum objeto em relação a outro
##### No caso acima, o relação do personagem e do mouse

	point_direction(x, y, mouse_x, mouse_y


##length_dir
##### Cria um circulo teorico em volta do objeto o qual é dividido em 4 lados / angulos
##### Auxilia em casos que se deseja alterar uma sprite para outra em relação a um lado por exemplo

	var _dir = point_direction(x, y,mouse_x, mouse_y)
	var _xx = lengthdir_x(5, _dir)
	var _yy = lengthdir_y(5, _dir)

##Sprite_index
##### Indica qual sprite será utilizado no objeto

	sprite_index = spr_personagem_padrao


##image_index
##### Ele seleciona qual frame do sprite ira iniciar a animação
##### Auxilia em efeito de loop
	
	image_index = 2

##instance_create_layer
##### ELe cria um objeto baseado no ponto x e y de um outro obj
##### Utilizado para criar hitboxes

	var _inst = instance_create_layer( x , y, "Instances", obj_dash)
	_inst.sprite_index = sprite_index;

##keyboard_check
##### Verifica se alguma tecla do teclado foi pressionada 
##### Obs:(existem variações para esse comando, como pressed e released)
##### Obs 2: Para teclas como letras e numeros é necessário utilizar o comando ord(), outras teclas tem o prefixo vk
##### como "vk_space" por exemplo


	direita = keyboard_check(ord("D"));
	esquerda = keyboard_check(ord("A"));
	cima = keyboard_check(ord("W"));
	baixo = keyboard_check(ord("S"));

	//faz com que a movimentação ocorra,  
	hveloc = (direita - esquerda) ;
	//faz com que a movimentação ocorra,  
	vveloc = (baixo - cima) ;

##mouse_check
##### Semelhante ao keyboard, porém em relação ao mouse. O funcionamento é o mesmo, porém com opções mb_left e mb_right por exemplo

