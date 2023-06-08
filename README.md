# mariadb-in-docker
banco de dados MongoDB e a ferramenta de interface Mongo Express 



**Título: Configurando um Banco de Dados MariaDB e phpMyAdmin com Docker Compose**

Olá pessoal! Hoje, gostaria de compartilhar com vocês como configurar facilmente um ambiente de banco de dados MariaDB e uma ferramenta de interface phpMyAdmin usando o Docker Compose. Essa configuração é útil para desenvolvedores e administradores de banco de dados que desejam ter um ambiente de desenvolvimento local sem complicações. Vamos dar uma olhada no código do Docker Compose passo a passo:

1. Primeiro, certifique-se de ter o Docker e o Docker Compose instalados em seu sistema. Se você ainda não os possui, pode encontrá-los em **https://www.docker.com/get-started**.
2. Em seguida, crie um arquivo chamado **`docker-compose.yml`** em seu projeto e cole o seguinte código:

https://github.com/CLAUDIO-FERNANDO/mariadb-in-docker/blob/main/docker-compose%20.yml

Agora, vamos entender o que cada parte do código faz:
- Definimos a versão do Docker Compose como **`3.1`**.
- Criamos uma rede chamada **`net-maria`** para permitir a comunicação entre os serviços.
- Criamos um volume chamado **`volume-maria`** para persistir os dados do banco de dados.
- Configuramos o serviço **`maria-db`** para usar a imagem do MariaDB, reiniciando sempre que necessário. Montamos o volume **`volume-maria`** no diretório de dados do MariaDB e configuramos as variáveis de ambiente para definir a senha do root, o nome do banco de dados, o nome de usuário e a senha.
- Configuramos o serviço **`PHP-MY-ADMIN`** para usar a imagem do phpMyAdmin, reiniciando sempre que necessário. Mapeamos a porta **`8080`** do host para a porta **`80`** do contêiner e configuramos as variáveis de ambiente para definir o host do banco de dados (serviço **`maria-db`**) e a senha do root.

* Salve o arquivo **`docker-compose.yml`**.

 Agora, abra o terminal, navegue até a pasta do projeto e execute o comando **`docker-compose up -d`**. Isso iniciará os contêineres em segundo plano, criando o ambiente de banco

Agora, você pode acessar o phpMyAdmin em **`http://localhost:8080`** e fazer login com o usuário root e a senha definida no arquivo Docker Compose.
