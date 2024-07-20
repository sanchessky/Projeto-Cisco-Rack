Autor: Thiago Sanches<br>


## PRIMEIRA ETAPA: Configuração Base do Switch Cisco Catalyst Layer-3 3560 

```python
!Acessando o modo Exec Privilegiado
enable

!Configuração de data/hora em inglês, abreviado ou completo
!Exemplo: October ou Oct
!Primeiro Hora no formato: 00:00:00 (hora:minutos:segundos) depois Data no formato: Dia Mês Ano
clock set ??:??:?? ?? ???????? ????

	!Acessar modo de Configuração Global
	configure terminal

	!Configuração do nome do Switch 3560
	!Obrigatório para a configuração do SSH e demais serviços de redes
	!Mudar o nome do Switch 3560 para cada equipamento do seu grupo
	!OBSERVAÇÃO IMPORTANTE: veja o arquivo 00-DocumentacaoDaRede.txt a partir da linha: 68 
	!(#03_ Nome dos Switches, Routers e Access Point de Cada Grupo:)
	hostname sw-g???

	!Habilitar o serviço de Criptografia de Senhas do Tipo-7 Password 
	service password-encryption
	
	!Habilitar o serviço de marcação de Data/Hora detalhado nos Logs
	service timestamps log datetime msec
	
	!Verificar tentativas de conexão simultâneas, fazer o bloqueio de um
	!período determinado de tempo, proteção contra Brute Force
	login block-for 120 attempts 4 within 60

	!Desativar a resolução de nomes de domínio
	no ip domain-lookup

	!Configuração do Banner da mensagem do dia
	!Desafio: Buscar na Internet imagens ASCII para o Banner
	!Dica de site: https://manytools.org/hacker-tools/ascii-banner/
	banner motd #AVISO: acesso autorizado somente a funcionarios#

	!Habilitar a senha do Tipo-5 secret para o modo enable privilegiado
	enable secret 123@senac
  
	!Criação dos usuários, senhas do Tipo-5 e privilégios diferenciados
	!Consultar Planilha de Nomes de Usuários
	!OBSERVAÇÃO: Caso o grupo tenha menos integrantes, desconsiderar a
	!criação de 04 (quatro) usuários
	username ???nome_do_primeiro_integrante??? privilege 15 secret 123@senac
	username ???nome_do_segundo_integrante??? privilege 15 secret 123@senac
	username ???nome_do_terceiro_integrante??? privilege 15 secret 123@senac
	username ???nome_do_quarto_integrante??? privilege 15 secret 123@senac
	
	!Acessando a linha console
	line console 0
		
		!Habilitando senha do Tipo-7 Password 
		password 123@senac
		
		!Forçando fazer login com usuário e senha
		login local
		
		!Sincronizando os logs na tela
		logging synchronous
		
		!Habilitando o tempo de inatividade do console
		exec-timeout 5 30
		
		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config

!Saindo do modo EXEC privilegiado
disable
exit
```
