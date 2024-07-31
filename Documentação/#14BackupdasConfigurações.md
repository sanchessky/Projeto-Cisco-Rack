## Backup das Configurações


1-Backup das configurações do Router e Switch

```python    
!modo exec privilegiado
eneble                  
!Salvando as configurações
copy running-config startup-config
!Salvando uma cópia das configuraçõe
copy startup-config flash:
!Visualizando o conteúdo da Flash
dir flash:
!historico 
show running-config


!!!  Salvar no seu bloco de nota o Backup   !!!

