# Autor: Jhony Araújo <jhony.gabriell214@gmail.com>
# Data de criação: Fev/2022

## Deploy de Aplicação Ruby on Rails com Ansible

Playbook Ansible para configurar aplicação Rails + Puma + Nginx

## Requerimentos

    + Servidor: CentOS 7 ou superior com banco de dados e Nginx pré-instalados
    
    + Cliente: Ansible 2.9 ou superior

    + Extensão do ansible para instalação do RVM
  
## Configuração

Copiar `group_vars/all.yml.example` para `group_vars/all.yml` e definir os valores.

Copiar `hosts.example` para `hosts` e definir o IP do servidor juntamente com a porta de acesso SSH.

Instalar extensão para instalação do RVM: `ansible-galaxy install rvm.ruby`

Editar site.yml e definir a versão do Ruby que deseja instalar 

## Execução

Gerar pares de chave SSH: `ssh-keygen`

Copiar chaves para o(s) servidor(es) de destino: `ssh-copy-id USER@IP` 

Executar playbook: `ansible-playbook site.yml -i hosts`

Após a execução é necessário popular o banco de dados ou aplicar o dump da aplicação.

## Considerações

Deploy realizado com Ruby na versão 2.5.8 e Rails 5.2.0