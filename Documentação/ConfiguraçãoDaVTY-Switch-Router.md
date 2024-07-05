Configuração das Linhas Virtuais do Switch Cisco Catalyst 3560 <br>

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal

	!Acessando as linhas virtuais
	line vty 0 4
		
		!Habilitando senha do tipo Password Tipo-7
		password 123@senac
		
		!Forçando fazer login com usuário e senha local
		login local 
		
		!Sincronizando os logs na tela
		logging synchronous
		
		!Habilitando o tempo de inatividade do terminal
		exec-timeout 5 30
		
		!Configuração do tipo de protocolo de transporte de entrada
		transport input ssh
		
		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config
```

Configuração das Linhas Virtuais do Router Cisco 2911 <br>

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
  
	!Acessando as linhas virtuais
	line vty 0 4
		
		!Habilitando senha do tipo Password Tipo-7
		password 123@senac
		
		!Forçando fazer login com usuário e senha local
		login local 
		
		!Sincronizando os logs na tela
		logging synchronous
		
		!Habilitando o tempo de inatividade do terminal
		exec-timeout 5 30
		
		!Configuração do tipo de protocolo de transporte de entrada
		transport input ssh
		
		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config
```
