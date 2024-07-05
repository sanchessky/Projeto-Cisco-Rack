Configuração SVI (Switch Virtual Interface) no Switch Cisco Catalyst 3560 

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
	
	!Configuração do gateway padrão IPv4 do SVI
	!Utilizado para acessar remotamente o equipamento
	!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 129 
	!(QUARTA ETAPA: Determinação dos Endereços de SVI (Switch Virtual Interface) e Gateway de cada Grupo)
	ip default-gateway 172.16.???.254
  
	!Configuração da interface virtual VLAN SVI
	!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 77
	!(TERCEIRA ETAPA: Determinação das Redes (Sub-Redes) e VLAN (Virtual-LAN) de Cada Grupo)
	interface vlan ???
		
		!Configuração da descrição
		description Interface SVI de Gerenciamento do Grupo-0???
		
		!Configuração do endereçamento IPv4 do SVI
		!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 129
		!(QUARTA ETAPA: Determinação dos Endereços de SVI (Switch Virtual Interface) e Gateway de cada Grupo)
		ip address 172.16.???.253 255.255.255.0
		
		!Inicializando a interface
		no shutdown
		
		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config

!Visualizando as configurações de endereçamento IPv4
show ip interface brief

!Visualizando as informações de VLAN
show vlan brief

!Visualizando informações detalhadas da VLAN
show vlan id ???
```
