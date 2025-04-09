# INFRAESTRUTURA COMO CÓDIGO - SCRIPT SHELL
## Desafio proposto pela [Digital Innovation One](https://www.dio.me)

## Sobre o projeto:
### O objetivo desse processo é configurar uma estrutura organizada de usuários e permissões para diferentes diretórios, garantindo que apenas os usuários autorizados possam acessar ou modificar determinados arquivos e diretórios.

### Utilizando Scripts Shell, na VM Ubuntu da AWS, por meio do PuTTY, fiz a criação de uma estrutura de usuários, diretórios e permissões, para o gerenciamento de maquinas em um ambiente de trabalho.

## Ferramentas Utilizadas:
![AWS](https://img.shields.io/badge/Amazon_AWS-232F3E?style=flat&logo=amazon-web-services&logoColor=white) ![Shell](https://img.shields.io/badge/Shell_Script-121011?style=flat&logo=gnu-bash&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white) ![GIT](https://img.shields.io/badge/GIT-E44C30?flat&logo=git&logoColor=white) 

## Passos para Clonagem:

### Clonagem do projeto:
```sh

     git clone https://github.com/Duda-Dz/Infraestrutura-AWS-Ubuntu-DIO.git
     
```
## Para Adicionar Para Execução:
```sh
chmod +x script-apache.sh

```
### Executando o projeto:
```sh

./iacl.sh

```
## Passo a Passo da Codificação:

### Para fazer a codificação abra o arquivo no editor Nano ou Vi:
```sh

nano iacl.sh

```
ou 

```sh

sudo nano iacl.sh

```
### OBS: Todo arquivo com Script Shell, tem extenção .sh

### Realizando o Script Shell dentro do Nano ou Vi:
```sh

#!/bin/bash

echo "Criando diretórios..."

mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec

echo "criando grupos de usuarios..."

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "criando usuarios..."

useradd carlos -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_ADM
useradd maria -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_ADM
useradd joao -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_ADM

useradd debora -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_VEN
useradd sebastiana -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_VEN
useradd roberto -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_VEN

useradd josefina -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_SEC
useradd amanda -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_SEC
useradd rogerio -m -s /bin/bash -p $(openssl passwd -6 Senha123) -g GRP_SEC

echo "criando permissões dos diretorios..."

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec

chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico

echo "fim...."

```
ou

```sh

#!/bin/bash

echo "Criando diretórios..."

mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec

echo "criando grupos de usuarios..."

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "criando usuarios..."

useradd carlos -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_ADM
useradd maria -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_ADM
useradd joao -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_ADM

useradd debora -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_VEN
useradd sebastiana -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_VEN
useradd roberto -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_VEN

useradd josefina -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -g GRP_SEC
useradd amanda -m -s /bin/bash -p $(openssl passwd -6 crypt 123) -g GRP_SEC
useradd rogerio -m -s /bin/bash -p $(openssl passwd -6 crypt 123) -g GRP_SEC

echo "criando permissões dos diretorios..."

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec

chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico

echo "fim...."
```
### OBS: Todo script deve ter:
```sh

#!/bin/bash

```
## Para Adicionar Para Execução:
```sh
chmod +x script-apache.sh

```
### Para executar o script:
```sh

./iacl.sh

```

