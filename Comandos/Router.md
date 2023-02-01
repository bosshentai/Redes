
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

## Criar Rotas
```
router(config)# ip route <ip rede> <mascara> <ip do salto>
router(config)# ip route 192.168.3.0 255.255.255.0 192.168.2.2
```



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

#### OSPF
```
R2(config)#router ospf 10
R2(config-router)#passive-interface gigabitEthernet 0/0
R2(config-router)#network 192.168.1.0 0.0.0.3 area 0 
R2(config-router)#network 192.168.0.0 0.0.0.255 area 0
R2(config-router)#network 192.168.0.0 0.0.0.31 area 0
```

# DHCP
```
ip dhcp excluded-address 192.168.0.1 192.168.0.50
ip dhcp pool pool_name
network 192.168.0.0 255.255.255.0
default-router 192.168.0.1

dns-server 8.8.8.8
```


# ACL

```
r2(config)#access-list 1 deny host 192.168.1.3
r2(config)#access-list 1 permit any
r2(config)#acess-list 1 deny any
```

### Depois
```
r2(config)#interface giga 0/0
r2(config-if)#ip access-group 1 out
```



# Voip

## router

```
ip dhcp excluded-address 192.168.20.1 192.168.20.30

ip dhcp pool Voice
network 192.168.20.0 255.255.255.0
default-router 192.168.20.1
option 150 ip 192.168.20.1
dns-server 8.8.8.8
```

### configurar o telefone da sua casa

```
telephony-service
max-ephones 5 (total de telefone fisicos)
max-dn 5 (total de numeros de telefone)
ip source-address 192.168.20.1 port 2000
```

```
ephone-dn 1
number 200

ephone-dn 2
number 201

ephone-dn 3
number 202

ephone-dn 4
number 203

```

```
ephone 1 
button 1:2

ephone 2 
button 1:1
```


