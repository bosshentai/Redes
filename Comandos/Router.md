
## Mudar nome
```
Router> enable
Router# config terminal
Router(config)# hostname R1
R1(config)#
```

## Adicionar Password
Requisito minimo 10 Caracteres para todas as passwords
```
Router(config)# security passwords min-length 10
```

Atribuir password para o modo exec privillegiado.
```
Router(config): enable secrete <password>
```

Atriburir <strong>password</strong> a consola, estabelecer um tempo limite, ativar o login e adicionando o comando <strong>logging synchronous</strong> 
```
Router(config)# line con 0
Router(config-line)# password <password>
Router(config-line)# exec-timeout 5 0 
Router(config-line)# login
Router(config-line)# logging synchronous
Router(config-line)# exit
Router(config)#
```

Atribuir <strong>password</strong> a <strong><i>vty</i></strong> , estabelecer um tempo limite, ativar o login e adicionando o  comando <strong>logging synchronous</strong>
```
Router(config)# line vty 0 4 
Router(config-line)# password <password>
Router(config-line)# exec-timeout 5 0 
Router(config-line)# login
Router(config-line)# logging synchronous
Router(config-line)# exit
Router(config)
```

Emita para cifrar todas as password
```
Router(config)# service password-encryption
```

Criar um banner para avisar as pessoas que o acesso nao autorizado.
```
Router(config)# banner motd # <message> #
```

## Guardar configuração 

```
Router# copy running-config startup-config
Destination filename [startup-config]?
Buildin configuration...
[OK]
Router#
```
ou 
```
Router#rw

```


## Configuração da Interface
```
Router(config)#interface gigabitEthernet 0/0
Router(config-if)#description Connection to Switch 
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#no shutdow
Router(config-if)#exit
Router(config)#exit
Router#
```

## Configuração Estatico


## Configuração Dinamico
#### RIP
#cmd
```
R2(config)#router rip
R2(config-router)# version 2 
R2(config-router)#no auto-summary
R2(config-router)#network 192.168.1.0
R2(config-router)#network 192.168.0.0
R2(config-router)#passive-interface gi0/0
```

