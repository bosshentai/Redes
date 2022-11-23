Ip da rede <strong> 192.168.22.0/24</strong>
![[signal-2022-11-23-091531.jpeg]]

O objectivo do trabalho é criar redes com 30 host para as 5 redes ligadas aos switch e 2 host para ligação entre os router.

<strong>1º</strong> Criar uma nova mascara 

o /24 é 255.255.255.0.

a formula de sub-rede : 2^n

Cada sub-rede deve ter suporte para pelo menos 30 hosts;
no minimo devemos ter 6 sub-redes;

A rede principal suporta 254 maquinas entao 30(Pc) * 6 (sub-redes) = 180.

Foi também tido em conta que serão “perdidos” dois endereços por cada sub-rede: o **endereço de sub-rede** que identificará essa  sub-rede e o **endereço de broadcast** de casa sub-rede.

Entao o devera ter 32 pc's (**30** é o números de PCs **+ 1** que é o endereço para a sub-rede e **+1** endereço de broadcast, que dá um total de 32)

Novo ip da rede 192.168.22.0/27