```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
		
	!Configuração da interface GigabitEthernet 0/1 para acesso a Internet
	interface gigabitEthernet 0/1
	
		!Descrição da Interface
		description Interface de acesso a Internet do Grupo-01
		
		!Configuração do endereçamento IP Dinâmico via DHCP Client
		ip address dhcp
		
		!Inicializando a Interface
		no shutdown
		
		!Saindo das configurações da interface
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config

!Visualizando as configurações de endereçamento IPv4
show ip interface brief

!Visualizando as informações de Roteamento
show ip route

!Pingar os servidores do SENAC Tatuapé no Router
ping 10.26.40.191
ping 10.26.40.190

!Pingar o Endereço IPv4 do Google no Router
ping 8.8.8.8

!Desktops Linux Mint ou Windows 10 deverá pingar via DNS
ping 8.8.8.8
ping google.com
```
