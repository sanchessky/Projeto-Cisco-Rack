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
		description Interface Serial do Grupo-01 para Grupo-???
		
		!Configuração do endereçamento IPv4
		!Verificar a tabela de endereçamento IP dos Grupos
		!Sempre vai ser o Endereço IPv4 IMPAR na Interface Serial 0/0/0
		ip address 192.168.1.??? 255.255.255.252
		
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
		description Interface Serial do Grupo-??? para Grupo-???
		
		!Configuração do endereçamento IP
		!Verificar a tabela de endereçamento IP dos Grupos
		!Sempre vai ser o Endereço IPv4 PAR na Interface Serial 0/0/1
		ip address 192.168.1.??? 255.255.255.252
		
		!Configurando a Largura de Banda
		bandwidth 64
		
		!Habilitando a interface
		no shutdown
		
		!Saindo das configurações da interface
		end

!Salvando as configurações
copy running-config startup-config
