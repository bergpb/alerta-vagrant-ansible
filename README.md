### Alerta

##### Deploy da aplicação alerta utilizando Vagrant e Ansible

Tenha o `vagrant` e `ansible` instalados na máquina.  

Execute o comando `vagrant up` e após finalizar acesse o endereço: [http://172.17.177.40](http://172.17.177.40)

Cadastre o primeiro usuário com o username `admin` para ter as permissões de administrador, caso deseje alterar o username altere o arquivo `roles/alerta/files/alertad.conf` e execute o comando `vagrant provision`.

Enviando um alerta: `alerta --endpoint-url http://172.17.177.40/api send --resource net01 --event down --severity major --environment Development --service Network --text 'net01 is down.'`

Enviando um heartbeat: `alerta --endpoint-url http://172.17.177.40/api heartbeat --origin dc1-oem-01 --timeout 60 -s major`

Mais informações consulte a documentação: [https://docs.alerta.io/en/latest/](https://docs.alerta.io/en/latest/)
