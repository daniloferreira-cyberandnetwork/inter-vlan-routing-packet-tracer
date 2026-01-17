# inter-vlan-routing-packet-tracer
Projeto de rede criado no Cisco Packet Tracer com VLANs, trunk e inter-VLAN routing usando Router-on-a-Stick. Inclui configuração de switch, subinterfaces no router e testes de conectividade.
Inter-VLAN Routing com Router-on-a-Stick (Packet Tracer)
📌 Descrição do Projeto

Projeto de rede desenvolvido no Cisco Packet Tracer com o objetivo de implementar VLANs, porta trunk e roteamento entre VLANs utilizando a técnica Router-on-a-Stick.
O projeto simula um ambiente corporativo básico, com separação de redes e comunicação controlada entre elas.

🧠 Conhecimentos aplicados

Criação e configuração de VLANs

Configuração de porta trunk (802.1Q)

Inter-VLAN Routing com Router-on-a-Stick

Criação de subinterfaces no roteador

Endereçamento IP

Testes de conectividade com ping

Diagnóstico de problemas físicos e lógicos

🖧 Topologia da Rede

1 Roteador Cisco

1 Switch Cisco

2 VLANs:

VLAN 10 – Rede 192.168.10.0/24

VLAN 20 – Rede 192.168.20.0/24

PCs conectados em VLANs diferentes

Comunicação entre VLANs através do roteador

🗂️ Endereçamento IP
VLAN	Rede	Gateway
VLAN 10	192.168.10.0/24	192.168.10.1
VLAN 20	192.168.20.0/24	192.168.20.1
⚙️ Configurações
🔹 Switch
enable
configure terminal

vlan 10
name ADMIN
vlan 20
name TI

interface fastEthernet 0/1
switchport mode trunk
no shutdown

interface fastEthernet 0/2
switchport mode access
switchport access vlan 10

interface fastEthernet 0/3
switchport mode access
switchport access vlan 20
end

🔹 Router (Router-on-a-Stick)
enable
configure terminal

interface gigabitEthernet 0/0
no shutdown

interface gigabitEthernet 0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface gigabitEthernet 0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
end

🧪 Testes Realizados

📸 Evidências do Projeto

🖧 Topologia da Rede
prints/topologia

🔀 Porta Trunk no Switch
prints/switch

🌐 Interfaces do Router
prints/router

🧪 Testes de Conectividade
VLAN 10 → Gateway
prints/testes/ping-vlan10.png

VLAN 20 → Gateway
prints/testes/ping-vlan20.png

Comunicação entre VLANs
prints/testes
✅ RESULTADO

A comunicação entre as VLANs foi estabelecida com sucesso através do Router-on-a-Stick, validando a configuração do ambiente.

Ping dos PCs para o gateway da própria VLAN ✅

Ping entre VLANs (VLAN 10 ↔ VLAN 20) ✅

Verificação da porta trunk com show interfaces trunk ✅

Verificação das interfaces do roteador com show ip interface brief ✅

📁 Arquivos do Projeto

Arquivo .pkt do Cisco Packet Tracer

README.md com documentação

Prints dos testes de conectividade

🎯 Objetivo

Demonstrar conhecimentos práticos em redes de computadores, VLANs e roteamento, aplicáveis a ambientes corporativos e compatíveis com vagas de nível júnior na área de redes.

🛠️ Ferramentas Utilizadas

Cisco Packet Tracer

Cisco IOS

📌 Observação:
Este projeto foi desenvolvido para fins de aprendizado e portfólio profissional.
