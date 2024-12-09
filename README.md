# Relatório da AV3
 
## Alunos

- Guilherme de Farias Loureiro (2214635)
- Nilo José Martins Jereissati (2110887)

## Disciplina: 

Projeto de Redes Convergentes

## Professor: 

Paulo Barros

## Imagem do projeto

## Comandos Utilizados

### SWITCH 0

Switch>enable
Switch#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#interface range fastethernet 0/2-24
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#vlan 2
Switch(config-vlan)#interface range fastethernet 0/7-8
Switch(config-if-range)#switchport voice vlan 2
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#w
Building configuration...
[OK]
Switch#

### ROUTER 0

Router>enable
Router#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface fastethernet 0/0
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up

Router(config-if)#interface fastethernet 0/0.1
Router(config-subif)#
%LINK-5-CHANGED: Interface FastEthernet0/0.1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0.1, changed state to up

Router(config-subif)#encapsulation dot1q 1
Router(config-subif)#ip address 192.168.10.1 255.255.255.228
Bad mask 0xFFFFFFE4 for address 192.168.10.1
Router(config-subif)#ip address 192.168.10.1 255.255.255.128
Router(config-subif)#interface fastethernet 0/0.2
Router(config-subif)#
%LINK-5-CHANGED: Interface FastEthernet0/0.2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0.2, changed state to up

Router(config-subif)#encapsulation dot1q 2
Router(config-subif)#ip address 192.168.10.129 255.255.255.240
Router(config-subif)#ip helper-address 192.168.10.2
Router(config-subif)#interface fastethernet 0/1
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up

Router(config-if)#ip address 128.12.1.1 255.255.255.252
Router(config-if)#interface fastethernet 1/0
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet1/0, changed state to up

Router(config-if)#ip address 128.12.1.10 255.255.255.252
Router(config-if)#router rip
Router(config-router)#network 128.12.1.0
Router(config-router)#network 128.12.1.8

Router(config-router)#telephony-service
Router(config-telephony)#max-dn 5
Router(config-telephony)#max-ephones 5
Router(config-telephony)#ip source-address 192.168.10.1 port 2000
Router(config-telephony)#auto assign 1 to 5
Router(config-telephony)#ephone-dn 1
Router(config-ephone-dn)#%LINK-3-UPDOWN: Interface ephone_dsp DN 1.1, changed state to up

Router(config-ephone-dn)#number 10
Router(config-ephone-dn)#ephone-dn 2
Router(config-ephone-dn)#%LINK-3-UPDOWN: Interface ephone_dsp DN 2.1, changed state to up

Router(config-ephone-dn)#number 11
Router(config-ephone-dn)#dial-peer voice 1 voip
Router(config-dial-peer)#destination-pattern 2.
Router(config-dial-peer)#session target ipv4:128.12.1.2
Router(config-dial-peer)#dial-peer voice 2 voip
Router(config-dial-peer)#destination-pattern 3.
Router(config-dial-peer)#session target ipv4:128.12.1.9

### ROUTER 1

Router>enable
Router#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface fastethernet 0/0
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up

Router(config-if)#ip address 128.12.1.2 255.255.255.252
Router(config-if)#interface fastethernet 0/1
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up

Router(config-if)#ip address 128.12.1.5 255.255.255.252
Router(config-if)#router rip
Router(config-router)#network 128.12.1.0
Router(config-router)#network 128.12.1.4

### ROUTER 2

Router>enable
Router#configure terminak
                        ^
% Invalid input detected at '^' marker.
	
Router#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface fastethernet 0/1
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/1, changed state to up

Router(config-if)#ip address 128.12.1.6 255.255.255.252
Router(config-if)#interface fastethernet 0/0
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up

Router(config-if)#ip address 128.12.1.9 255.255.255.252
Router(config-if)#router rip
Router(config-router)#network 128.12.1.4
Router(config-router)#network 128.12.1.8