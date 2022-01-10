# desafio-kubedev-wordpress
Objetivo deste desafio e preparar um ambientes para receber o CMS "content management system" que no caso será o wordpress. A demanda para este projeto é que seja todo feito em container. 
## Definir CMS e seus requisitos
  * CMS  Wordpress
     * requisitos
        * PHP
        * Mysql ou MariaDB
        * Apache ou nginx
  * Utilizar imagem oficial do docker hub que já contém várias das dependências.
  * Utilizar docker-compose para facilitar o trabalho com o projeto.
## Definir versões
  * Imagem Wordpress versão 5.8
  * Banco de dados MariaDB 10.7
## Versões de imagem do  wordpress
  * wordpress:5.8.3-apache
    - É uma versão que contem o CMS wodpress com php padrão built-in e webserver apache, rodando diretamente na porta 80.
  * wordpress:5.8.3-fpm
    - É um versão apenas com fastCGI php-fpm que é uma alternativa ao interpretador do php padrão, pode ser usado no apache como no nginx.
    - está solução roda na porta padrão 9000
    - Necessita de um servidor web como nginx ou apache.
    - php-fpm realiza apenas o serviço de application server.
  * wordpress:5.8.3-fpm-alpine
    - É uma versão também com fastCGI php-fpm agora usando um linux mais leve no caso o alpine.
## Resumo do projeto
  Ambiente como é focado para aprendizado irá conter wordpress com apache e fastCGI, utilizando  de docker-composes diferentes.
## Requisito de configurações
  * **Variaveis wordpress**
    - WORDPRESS_DB_HOST= mariadb 
    - WORDPRESS_DB_USER= mariauser
    - WORDPRESS_DB_PASSWORD= mariapwd
    - WORDPRESS_DB_NAME= mywordpress
  * **Variáveis MariaDB**
    - MARIADB_DATABASE= mywordpress
    - MARIADB_USER= mariauser
    - MARIADB_RANDOM_ROOT_PASSWORD= '1'  *Definir que irá exibir nos logs stdout a senha de root.*
    - MARIADB_PASSWORD= mariapwd
  * **Wordpress com fpm**
    - É necessário instalar o web server nginx, e definir o mesmo volume de armazenamento do site wordpress para o servidor nginx.

