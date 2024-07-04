Autor: Thiago Sanches<br>
Instagram: https://www.instagram.com/espetacular_sanches<br>
LinkedIn Thiago Sanches: https://www.linkedin.com/in/thiagosanches07/<br>
Github: https://github.com/sanchessky<br>
Data de criação: 04/07/2024<br>




1- Nome dos Switches, Routers e Access Point de Cada Grupo


    Grupo-01:   Hostname Switch 3560: sw-g01   Hostname Router 2911: rt-g01   Access Point: ap-g01

02. Todo o cenário será configurado utilizando VLAN (Virtual-LAN), será determinado 6 (seis) VLAN's por Grupo, sendo elas

		a) 01 (uma)    VLAN de SVI (Switch Virtual Interface - Gerenciamento da Switch 3560)
		b) 04 (quatro) VLAN's para cada usuário na rede (4 integrantes do grupo - Desktops)
		c) 01 (uma)    VLAN de Rede Sem-Fio (Wi-Fi/Wireless)


03. Determinação das Sub-Redes e VLAN de cada Grupo.

		Grupo-01:   Subredes:   172.16.10.0/24   VLAN:  10  -  utilizada no SVI do Switch Layer 3
		            Subredes:   172.16.11.0/24   VLAN:  11  -  utilizada pelo primeiro usuário da rede
		            Subredes:   172.16.12.0/24   VLAN:  12  -  utilizada pelo segundo usuário da rede
		            Subredes:   172.16.13.0/24   VLAN:  13  -  utilizada pelo terceiro usuário da rede
		            Subredes:   172.16.14.0/24   VLAN:  14  -  utilizada pelo quarto usuário da rede
		            Subredes:   172.16.15.0/24   VLAN:  15  -  utilizada pela rede sem-fio

Determinação dos Endereços de SVI (Switch Virtual Interface) e Gateway de cada Grupo <br>

01. Determinação do endereço IPv4 da VLAN de SVI e Gateway do Switch Layer 3

		Grupo-01:  SVI:  172.16.10.253/24  -  Gateway: 172.16.10.254
