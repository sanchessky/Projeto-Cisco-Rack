Autor: Allan Vítor<br>
Instagram: https://www.instagram.com/allankkjjj<br>
LinkedIn Allan Vítor: [https://www.linkedin.com/in/HubOpsVitor/](https://br.linkedin.com/in/allan-v%C3%ADtor-siqueira-silva-8249802b2)<br>
Github: https://github.com/HubOpsVitor<br>
Data de criação: 29/07/2024<br>

## PRIMEIRA ETAPA: Configuração da Interface Serial no Router Cisco 2911

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
		
	!Configuração da interface Serial0/0/0
	interface serial 0/0/0
	
		!Descrição da Interface Serial
		!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 232
		!(SÉTIMA ETAPA: Determinação da Interface Serial de WAN dos Grupos e seu Endereçamento IPv4)
		description Interface Serial do Grupo-01 para Grupo-02
		
		!Configuração do endereçamento IPv4
		!Verificar a tabela de endereçamento IP dos Grupos
		!Sempre vai ser o Endereço IPv4 IMPAR na Interface Serial 0/0/0
		ip address 192.168.1.1 255.255.255.252
		
		!Configurando o Clock Rate, Velocidade do Link
		clock rate 64000
		
		!Configurando a Largura de Banda
		bandwidth 64
		
		!Habilitando a interface
		no shutdown
		
		!Saindo das configurações da interface
		exit
		
	!Configuração da interface Serial0/0/1
	interface serial 0/0/1
	
		!Descrição da Interface
		!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 232
		!(SÉTIMA ETAPA: Determinação da Interface Serial de WAN dos Grupos e seu Endereçamento IPv4)
		description Interface Serial do Grupo-06 para Grupo-01
		
		!Configuração do endereçamento IP
		!Verificar a tabela de endereçamento IP dos Grupos
		!Sempre vai ser o Endereço IPv4 PAR na Interface Serial 0/0/1
		ip address 192.168.1.22 255.255.255.252
		
		!Configurando a Largura de Banda
		bandwidth 64
		
		!Habilitando a interface
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

ROUTER VIZINHO-DCE <---> DTE-0/0/1_SEU ROUTER_DCE-0/0/0 <---> DTE-ROUTER VIZINHO

!Pingar a SUA Interface Serial 0/0/0 (SEMPRE SERÁ O IPv4 PAR)
ping 192.168.1.??? (serial 0/0/0)

!Pingar a SUA Interface Serial 0/0/1 (SEMPRE SERÁ O IPv4 IMPAR)
ping 192.168.1.??? (serial 0/0/1)

!Pingar a Interface Serial 0/0/0 do SEU VIZINHO (SEMPRE SERÁ O IPv4 IMPAR)
ping 192.168.1.??? (serial 0/0/0)

!Pingar a Interface Serial 0/0/1 do SEU VIZINHO (SEMPRE SERÁ O IPv4 PAR)
ping 192.168.1.??? (serial 0/0/0)
```
