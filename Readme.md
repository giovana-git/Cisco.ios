# Comandos gerais Cisco IOS 



**TROCAR HOSTNAME DOS ESQUIPAMENTOS**
```
>enable
#configure terminal 
(config)#hostname <hostname> 
```

**CONFIGURAR UM BANNER**	
```
>enable
#configure terminal 
(config)#banner motd "texto"

EX: (config)#banner motd "Acesso apenas para o Departamento de TI" 
```  
  


**CONFIGURAR SENHA NA CONSOLE**
```

>enable
#configure terminal
(config)#line console 0
(config-line)#password <senha>
(config-line)#login (NÃO ESQUECER O LOGIN, CASO CONTRÁRIO A SENHA NÃO SERÁ HABILITADA) 
``` 

  
CONFIGURAR SENHA NA ENABLE


>enable
#configure terminal 
(config)#enable secret (UTILIZAR SECRET POIS VEM CRIPTOGRAFADA) 
  
  


  
!VERIFICAR AS CONFIGURAÇÕES QUE ESTÃO RODANDO NO EQUIPAMENTO 


>enable 
#show running-config 


!HABILITAR SERVIÇO DE CRIPTOGRAFIA 

>enable
#configure terminal
(config)#service password-encryption 


!DESFAZER UM COMANDO NO IOS 

Digitar NO antes do comando!!! 


!DESATIVAR UMA INTERFACE 

>enable
#configure terminal
(config)#interface <nomenclatura-da-interface>
(config-if)#shutdown 

EX: (config)#interface g0/0 


!DESATIVAR/ATIVAR VÁRIAS INTERFACES DE UMA VEZ 

>enable
#configure terminal
(config)#interface range <intervalo> 

EX: 
>enable
#configure terminal
(config)#interface range g0/0-2 
(config-if-range)#shutdown 



!VER RESUMO DAS INTERFACES 

>enable
#show ip interface brief 


!SALVAR CONFIGURAÇÕES 

>enable
#write memory 
ou 
#copy running-config startup-config 


!RESETAR EQUIPAMENTO 

>enable 
#write erase 



!CONFIGURAR IP NA INTERFACE 


>enable
#configure terminal
(config)#interface <nome-da-interface> 
(config)#ip address <ip> + <máscara-de-subrede-em-decimal> 



	

	
	
!COLOCAR DESCRIÇÃO EM UMA INTERFACE 

>enable 
#configure terminal 
(config)#interface <nome> 
(config-if)#description <descrição> 
  
  
  
  
  
  
