# Produtividade com linux

### Configurando acentos para teclado em inglês no linux
__Terminal__
> setxkbmap -model abnt -layout us -variant intl
 <br>
> setxkbmap -model abnt2 -layout br -variant abnt2

### Configurando Portas / TCP
#### Liberando Portas 
__Terminal__
> sudo ufw allow 5432/tcp

### Services execute linux 
__Terminal__
> sudo systemctl restart postgres

### Setting remote Postgresql
__Allow remote acess__
> vim  /etc/postgresql/12/main/postgresql.conf
 <br>
__Modify from__
 <br> 
> #listen_addresses = 'localhost'
 <br>
__to__
 <br> 
> #listen_addresses = '*'
 <br>
> vim /etc/postgresql/12/main/pg_hba.conf
 <br>
---------------------------------------------------------------------
 <br>
__Modify IPv4 local connections__
 <br>
> host    all             all             127.0.0.1/32            md5
 <br>
__to__
 <br>
> host    all             all             0.0.0.0/0            md5
 <br>
