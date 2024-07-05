Autor: Thiago Sanches<br>
Instagram: https://www.instagram.com/espetacular_sanches<br>
LinkedIn Thiago Sanches: https://www.linkedin.com/in/thiagosanches07/<br>
Github: https://github.com/sanchessky<br>
Data de criação: 04/07/2024<br>
Atualizado por Allan Vítor 05/07/2024




## SEGUNDA ETAPA: Usuário e Senha padrão dos Switches e Routers Cisco de cada Grupo.<br>
1- Nome dos Switches, Routers e Access Point de Cada Grupo<br>


    Grupo-01:   Hostname Switch 3560: sw-g01   Hostname Router 2911: rt-g01   Access Point: ap-g01

## TERCEIRA ETAPA: Determinação das Redes (Sub-Redes) e VLAN (Virtual-LAN) de Cada Grupo<br>
Todo o cenário será configurado utilizando VLAN (Virtual-LAN), será determinado 6 (seis) VLAN's por Grupo, sendo elas

		a) 01 (uma)    VLAN de SVI (Switch Virtual Interface - Gerenciamento da Switch 3560)
		b) 04 (quatro) VLAN's para cada usuário na rede (4 integrantes do grupo - Desktops)
		c) 01 (uma)    VLAN de Rede Sem-Fio (Wi-Fi/Wireless)


Determinação das Sub-Redes e VLAN de cada Grupo.<br>

		Grupo-01:   Subredes:   172.16.10.0/24   VLAN:  10  -  utilizada no SVI do Switch Layer 3
		            Subredes:   172.16.11.0/24   VLAN:  11  -  utilizada pelo primeiro usuário da rede
		            Subredes:   172.16.12.0/24   VLAN:  12  -  utilizada pelo segundo usuário da rede
		            Subredes:   172.16.13.0/24   VLAN:  13  -  utilizada pelo terceiro usuário da rede
		            Subredes:   172.16.14.0/24   VLAN:  14  -  utilizada pelo quarto usuário da rede
		            Subredes:   172.16.15.0/24   VLAN:  15  -  utilizada pela rede sem-fio

## QUARTA ETAPA: Determinação dos Endereços de SVI (Switch Virtual Interface) e Gateway de cada Grupo<br>
Determinação do endereço IPv4 da VLAN de SVI e Gateway do Switch Layer 3<br>

		Grupo-01:  SVI:  172.16.10.253/24  -  Gateway: 172.16.10.254

## QUINTA ETAPA: Determinação das Portas de Rede de cada VLAN dos Usuários dos Grupos

**OBSERVAÇÃO IMPORTANTE: a Porta de Rede: FastEthernet 0/1 não será utilizada nas configurações.**

**OBSERVAÇÃO IMPORTANTE: O nome da VLAN deverá ser o Primeiro Nome dos Alunos do Grupo, exemplo: Robson Vaamonde - nome da VLAN 11: robson (sempre em minúsculo), Leandro Ramos - nome da VLAN 12: leandro, etc...**

**OBSERVAÇÃO: CASO O GRUPO NÃO TENHA 04 (QUATRO) ALUNOS, DESCONSIDERAR A CRIAÇÃO DAS VLAN'S CORRESPONDENTE, EXEMPLO: GRUPO COM 3 (TRÊS) ALUNOS DESCONSIDERAR A QUARTA VLAN DO GRUPO MAIS MANTER A VLAN DA REDE SEM-FIO COM O SEU NÚMERO E NOME**

01. Determinação das Portas de Rede das VLAN do Switch 3560

		Grupo-01:   Porta: 2    VLAN: 11    Nome: ??Primeiro_Nome_do_Primeiro_Aluno??
		            Porta: 3    VLAN: 12    Nome: ??Primeiro_Nome_do_Segundo_Aluno??
		            Porta: 4    VLAN: 13    Nome: ??Primeiro_Nome_do_Terceiro_Aluno??
		            Porta: 5    VLAN: 14    Nome: ??Primeiro_Nome_do_Quarto_Aluno??
		            Porta: 6    VLAN: 15    Nome: wifi01

				Vlan 11 - allan  | 172.16.11.254
				Vlan 12 - arthur | 172.16.12.254
				Vlan 13 - eder   | 172.16.13.254
				Vlan 14 - thiago | 172.16.14.254
