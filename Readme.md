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

  
**CONFIGURAR SENHA NA ENABLE**
```
>enable
#configure terminal 
(config)#enable secret (UTILIZAR SECRET POIS VEM CRIPTOGRAFADA) 
 ``` 
  


  
**VERIFICAR AS CONFIGURAÇÕES QUE ESTÃO RODANDO NO EQUIPAMENTO** 
```
>enable 
#show running-config 
```


**HABILITAR SERVIÇO DE CRIPTOGRAFIA** 
```
>enable
#configure terminal
(config)#service password-encryption 
```

**DESFAZER UM COMANDO NO IOS** 
```
Digitar NO antes do comando!!! 
```

**DESATIVAR UMA INTERFACE** 
```
>enable
#configure terminal
(config)#interface <nomenclatura-da-interface>
(config-if)#shutdown 

EX: (config)#interface g0/0 
```


**DESATIVAR/ATIVAR VÁRIAS INTERFACES DE UMA VEZ**  
```
>enable
#configure terminal
(config)#interface range <intervalo> 

EX: 
>enable
#configure terminal
(config)#interface range g0/0-2 
(config-if-range)#shutdown 
```



**VER RESUMO DAS INTERFACES** 
```
>enable
#show ip interface brief 
```

**SALVAR CONFIGURAÇÕES** 
```
>enable
#write memory 
ou 
#copy running-config startup-config 
```

**RESETAR EQUIPAMENTO** 
```
>enable 
#write erase 
```


**CONFIGURAR IP NA INTERFACE** 
```
>enable
#configure terminal
(config)#interface <nome-da-interface> 
(config)#ip address <ip> + <máscara-de-subrede-em-decimal> 
```


**COLOCAR DESCRIÇÃO EM UMA INTERFACE** 
```
>enable 
#configure terminal 
(config)#interface <nome> 
(config-if)#description <descrição> 
```
 
# SSH 

**DEFINIR NOME DE DOMÍNIO**
```
>enable 
#configure terminal 
(config)#ip domain-name <nome-de-domínio> 
```

**GERAR CHAVE DE CRIPTOGRAFIA** 
```
>enable 
#configure terminal 
(config)#crypto key generate rsa general-keys modulus <tamanho-de-bits> <360-4000> 
``` 

**CRIAR USUÁRIOS** 
```
>enable 
#configure terminal 
(config)#username <usuário> privilege <privilégio> secret <senha-do-usuário> 

EX - (config)#username Giovana privilege 15 secret Senha*Segura 
```

**ATIVAR SSH NAS LINHAS DE VTY** 
```
>enable 
#configure terminal 
(config)#line vty 0 15 
(config-line)#transport input ssh 
(config-line)#login local 
```

**ATIVAR LOGIN LOCAL NA CONSOLE** 
```
>enable 
#configure terminal 
(config)#line console 0 
(config-line)#login local 
```

**Configurar as VTY para usar TELNET**
```
>enable
#configure terminal
(config)#line vty 0 15
(config-line)#password <senha>
(config-line)#login
```



# CONFIGURAÇÕES EXCLUSIVAS PARA O ROTEADOR 

**VISUALIZAR TABELA DE ROTEAMENTO** 
```
>enable 
#show ip route 

LEGENDAS DA TABELA: 
C = REDE QUE ELE ESTÁ CONECTADO 
L = ENDEREÇO QUE ELE ESTÁ USANDO NA REDE 
/32 = IP DE UM HOST
S = ROTA ESTÁTICA 
S* = ROTA PADRÃO 
```

**CONFIGURAR SUBINTERFACES** 
```
>enable
#configure terminal 
(config)#interface <nome-da-subinterface> 

  EX - (config)#interface g0/0.10 
  10 = NÚMERO DA VLAN ATRELADA 

(config)#interface <nome-da-subinterface>
(config-subif)#encapsulation dot1q <número-da-vlan> 
(config-subif)#ip address <ip> + <máscara> 
```


**CONFIGURAR UMA ROTÁ ESTÁTICA (IPv4)** 
```
>enable
#configure terminal 
(config)#ip route <id-da-rede-de-destino> + <máscara-da-rede-de-destino> <ip-do-roteador-que-conhece-a-rede> 

EX - (config)#ip route 192.168.0.10> + 255.255.255.128 + 200.200.100.2
```

**CONFIGURAR UMA ROTA PADRÃO (IPv4)** 
```
>enable
#configure terminal 
(config)#ip route 0.0.0.0 0.0.0.0 <nome-da-interface-de-saída> 

EX - (config)#ip route 0.0.0.0 0.0.0.0 s0/0/0 
```


**ATIVAR O ROTEAMENTO IPv6** 
```
>enable
#configure terminal 
(config)#ipv6 unicast-routing 
```


**INSERIR IPv6 EM UMA INTERFACE** 
```
>enable
#configure terminal 
(config)#interface <nome-da-interface>
(config-if)#ipv6 address <endereço>/<prefixo> 
```



























  
