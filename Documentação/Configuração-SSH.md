Autor: Thiago Sanches<br>
Instagram: https://www.instagram.com/espetacular_sanches<br>
LinkedIn Thiago Sanches: https://www.linkedin.com/in/thiagosanches07/<br>
Github: https://github.com/sanchessky<br>
Data de criação: 05/07/2024<br>




Configuração do SSH Server no Switch Cisco Catalyst 3560 <br>

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
		
		!Configuração do nome de domínio, obrigatório para a configuração do SSH
		ip domain-name senac.br
	
		!Criação da chave de criptografia e habilitação do serviço de SSH
		!Utilizar módulo de criptografia de 1024 bits
		crypto key generate rsa general-keys modulus 1024
		
		!Habilitando a versão 2 do serviço do SSH
		ip ssh version 2
		
		!Habilitar o tempo de inatividade para novas conexões do SSH
		ip ssh time-out 60
		
		!Habilitar o número máximo de tentativas de conexão do SSH
		ip ssh authentication-retries 2

		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config

!Visualizando as configurações do SSH Server
show ip ssh

!Visualizando das chaves públicas RSA
show crypto key mypubkey rsa

!Visualizando as conexões ativas do SSH Server
show ssh (só vai funcionar quando você se conectar remoto no Switch)

!Visualizando as conexões remotas estabelecidas no Switch
show users (só vai funcionar quando você se conectar remoto no Switch)
```

Configuração do SSH Server no Router Cisco 2911 <br>

```python
!Acessando o modo Exec Privilegiado
enable

	!Acessar modo de configuração global
	configure terminal
		
		!Configuração do nome de domínio, obrigatório para a configuração do SSH
		ip domain-name senac.br
	
		!Criação da chave de criptografia e habilitação do serviço de SSH
		!Utilizar módulo de criptografia de 1024 bits
		crypto key generate rsa general-keys modulus 1024
		
		!Habilitando a versão 2 do serviço do SSH
		ip ssh version 2
		
		!Habilitar o tempo de inatividade para novas conexões do SSH
		ip ssh time-out 60
		
		!Habilitar o número máximo de tentativas de conexão do SSH
		ip ssh authentication-retries 2

		!Saindo de todos os níveis
		end

!Salvando as configurações
copy running-config startup-config
	
!Visualizando as configurações
show running-config

!Visualizando as configurações do SSH Server
show ip ssh

!Visualizando das chaves públicas RSA
show crypto key mypubkey rsa

!Visualizando as conexões ativas do SSH Server
show ssh (só vai funcionar quando você se conectar remoto no Router)

!Visualizando as conexões remotas estabelecidas no Router
show users (só vai funcionar quando você se conectar remoto no Router)
```
