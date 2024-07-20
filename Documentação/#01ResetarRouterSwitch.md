Autor: Thiago Sanches<br>
Instagram: https://www.instagram.com/espetacular_sanches<br>
LinkedIn Thiago Sanches: https://www.linkedin.com/in/thiagosanches07/<br>
Github: https://github.com/sanchessky<br>
Data de criação: 04/07/2024<br>



Limpando as configurações residuais dos outros grupos do Switch 3560.

```python
Switch>
	
	!Acessar o modo privilegiado de comandos 
	Switch> enable

	!Remover o banco de dados de VLAN da Flash: 
	Switch# delete flash:vlan.dat

	!Remover os backups anteriores das turmas: 
	Switch# delete flash:startup-config

	!Reiniciar o Switch para testar as configurações
	Switch# reload

```
 Reset do Roteador (Router) 2911

**OBSERVAÇÃO IMPORTANTE: Utilizar o PuTTY para acessar o Switch utilizando o Cabo Console.**

01. Parar a inicialização do IOS do Router Cisco 2911 utilizando as teclas de atalho: **Ctrl + Break** (No PuTTY utilizar o Botão direito do Mouse na Barra de Título e selecionar as opções: **Send Command: Break**)

**CUIDADO!!!!!! com a Chave de Registro que você vai digitar no ROMmon (veja os tópicos das Obs: 1 e 2)**

02. Nas configurações do Cisco ROMmon digite a chave em hexadecimal: confreg 0x2142 <Enter>

```python
rommon 1> confreg 0x2142 
```

03. Após a mudança da chave, digite: reset <Enter> para reiniciar o Router Cisco 2911.

```python
rommon 2> reset
```

04. O Router Cisco 2911 vai inicializar sem ler o arquivo de configuração: **startup-config** da NVRAM.

05. Limpando as configurações do Router Cisco 2911 e voltando a ler o arquivo de configuração: *startup-config* da NVRAM.

```python
Router>
	
	!Acessar o modo privilegiado de comandos 
	Router> enable

	!Limpando as configuração da NVRAM
	Router# erase startup-config

	!Remover os backups anteriores das turmas: 
	Router# delete flash:startup-config

	!Entrar no modo de configuração global
	Router# configure terminal

		!Alterar o registro de inicialização do Router
		Router (config)# config-register 0x2102 

		!Saindo de dos os modos de configuração
		Router (config)# end

	!Salvando as configurações da RAM para a NVRAM
	Router# copy running-config startup-config 

	!Reiniciar o Router para testar as configurações
	Router# reload

	!Após a reiniciar o Router Cisco 2911 verifique a chave de registro
	!Valor está na última linha referente ao cofreg 0x2102
	Router> enable
	Router# show version
		Configuration register is 0x2102
```
