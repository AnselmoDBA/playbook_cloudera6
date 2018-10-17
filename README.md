# Playbooks de instalação do Cloudera

'Atualizado:' 17.10.2018

Esses PLaybooks tem o intuito de automatizar algumas partes da instalação de um Cluster Cloudera, os mesmos estão divididos em:
* install_cloudera6_inicial.yml - Esse Script faz a configuração básica do Cloudera 6 em todos os nodes, tanto que esse deve ser rodado para o grupo todo, instala os pre-reqs, faz a configuração dos repositórios do Cloudera 6, instala o mariadb e outras funções.
* install_cloudera6_final.yml - Esse script realiza a configuração do Cloudera Manager server no primeiro node, onde vai rodar a aplicação de futura instalação e administração do cluster.
* install_cloudera5_inicial.yml - Esse Script faz a configuração básica do Cloudera 5 em todos os nodes, tanto que esse deve ser rodado para o grupo todo, instala os pre-reqs, faz a configuração dos repositórios do Cloudera 6, instala o mariadb e outras funções.
* install_cloudera5_final.yml - Esse script realiza a configuração do Cloudera Manager server no primeiro node, onde vai rodar a aplicação de futura instalação e administração do cluster.

## Pasta confs:
Na pasta confs estão arquivos e RPMs que serão necessários para algumas instalações, nesse diretório temos tambem os arquivos de configuração de algumas aplicações e do próprio S.O, como:
* Hosts
* sysctl.comf
* limits

Esses arquivos devem ser editados conforme a necessidade do novo cluster antes de executado o playbook.

## Pré requisitos para execução do playbook:
Essa execução depende de algumas coisas:
* O usuário da maquina de onde estou rodando o playbook deve ter SSH sem senha para os destinos. Para o user de execução (remote_user)
* O usuário destino deve ter privilégios de sudo sem senha (NOPASSWD), caso contrario usar o root e fazer o procedimento de cima para root.
* Todos os hosts devem estar cadastrados no /etc/ansible/hosts
* Deve ser configurado o remote_user (usuário com privilegio de root ou root) no arquivo de configuração do Ansible (/etc/ansible/ansible.cnf)


