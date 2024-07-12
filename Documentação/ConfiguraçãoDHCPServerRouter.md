Autor: Thiago Sanches<br>
Instagram: https://www.instagram.com/espetacular_sanches<br>
LinkedIn Thiago Sanches: https://www.linkedin.com/in/thiagosanches07/<br>
Github: https://github.com/sanchessky<br>
Data de criação: 11/07/2024<br>
Atualizado: 12/07/2024<br>

Configuração do SSH Server no Router <br>



## PRIMEIRA ETAPA: Configuração do DHCP Server no Router Cisco 2911

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal

		!Configurando o Pool do DHCP Server da VLAN do Primeiro Usuário
		!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 186 
		!(SEXTA ETAPA: Determinação das Sub-Interfaces de Gateway de cada VLAN dos Grupos)
		ip dhcp excluded-address 172.16.11.1 172.16.11.100
		ip dhcp excluded-address 172.16.11.200 172.16.11.254
		ip dhcp pool vlan-11
			network 172.16.10.0 255.255.255.0
			default-router 172.16.10.254
			dns-server 8.8.8.8 8.8.4.4
			domain-name senac.br
			exit

		!Configurando o Pool do DHCP Server da VLAN do Segundo Usuário	
		ip dhcp excluded-address 172.16.12.1 172.16.12.100
		ip dhcp excluded-address 172.16.12.200 172.16.12.254
		ip dhcp pool vlan-12
			network 172.16.12.0 255.255.255.0
			default-router 172.16.12.254
			dns-server 8.8.8.8 8.8.4.4
			domain-name senac.br
			exit

		!Configurando o Pool do DHCP Server da VLAN do Terceiro Usuário	
		ip dhcp excluded-address 172.16.13.1 172.16.13.100
		ip dhcp excluded-address 172.16.13.200 172.16.13.254
		ip dhcp pool vlan-13
			network 172.16.13.0 255.255.255.0
			default-router 172.16.12.254
			dns-server 8.8.8.8 8.8.4.4
			domain-name senac.br
			exit

		!Configurando o Pool do DHCP Server da VLAN do Quarto Usuário	
		ip dhcp excluded-address 172.16.14.1 172.16.14.100
		ip dhcp excluded-address 172.16.14.200 172.16.14.254
		ip dhcp pool vlan-14
			network 172.16.14.0 255.255.255.0
			default-router 172.16.14.254
			dns-server 8.8.8.8 8.8.4.4
			domain-name senac.br
			exit

		!Configurando o Pool do DHCP Server da VLAN Wireless
		ip dhcp excluded-address 172.16.15.1 172.16.15.100
		ip dhcp excluded-address 172.16.15.200 172.16.15.254
		ip dhcp pool vlan-15
			network 172.16.15.0 255.255.255.0
			default-router 172.16.15.254
			dns-server 8.8.8.8 8.8.4.4
			domain-name senac.br
			end
