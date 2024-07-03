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
