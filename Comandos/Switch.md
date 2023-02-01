```
switch(config)# no ip domain-lookup
```

## Mudar nome
```
Switch> enable
Switch(config)# config terminal
Switch# hostname S1
```

## Config password
```
Switch(config)# service password-encryption
Switch(config)# enable secret class
Swicth(config)# banner motd # O acessao nao autorizado e proibido #
```

## Criar Vlan
### adicionar nome a vlan
```
Switch(config)#vlan 500
Switch(config-vlan)# name teste
Switch(config-vlan)# exit
```
### Atribuir um ip a vlan
```
Switch(config)# interface vlan500
Switch(config-if)# ip address 192.168.1.2 255.255.255.0
Switch(config-if)# no shutdown
Switch(config-if)# exit
Switch(config)
```

## Configurar Trunk
```
Switch(config)# interface range gigabitEther 0/1-2
Swicth(config-if-range)#switchport  mode trunk
Switch(config-if-range)#switchport trunk allowed vlan 500,501,502
Switch(config-if-range)#exit
Switch(config)#
```

### Atribuir as porta do swicth uma vlan
<strong>Exemplo 1 :</strong>
```
Switch(config)# interface range f0/1-24,g0/1-2
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 500
Switch(config-if-range)# exit
Switch(config)# 
```
<strong>Exemplo 2 :</strong>
```
Switch(config)# interface range FastEthernet 0/7-12
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 500
Swicth(config-if-range)# exit
```


### Vlan configure voip 
```
interface FastEthernet 0/1
switchport access vlan 10

switchport voice vlan 20 
```