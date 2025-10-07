# DesafioCodegirlsAWS-EC2-DIO
Esse repositório tem como objetivo consolidar os meus conhecimentos em gerenciamento de instâncias EC2 na AWS, para o desafio da DIO. Contém as minhas anotações e visões sobre o meu entendimento da matéria, servindo como material de apoio para demonstrar o meu aprendizado na prática.

## ➤ Fluxo de requisição de acesso com EC2, EBS, RDS e S3.

 O diagrama abaixo representa uma aplicação web hospedada em uma instância EC2 (Elastic Compute Cloud) do tipo IAAS (infraestutura como serviço), que interage com diferentes serviços de armazenamento e banco de dados da AWS:
 
 - **EBS (Elastic Block Store)** - Serviço para oferecer armazenamento em blocos, funciona como volumes ou discos rígidos para a instância EC2.

- **RDS** (Relational Database service) - Serviço gerenciado de banco de daods relacional, um tipo de "EC2 especializado".

- **S3** (Simples Storage Service) - Serviço de armazenamento de objetos, guardar arquivos de forma definitiva e acessa-los de forma simples.(arquivos, imagens, vídeos, etc). 

#### A arquitetura está exemplificada no seguindo diagrama:
![Diagrama EC2](images/diagrama-ec2.png)

 ### Fluxo de dados | Contextualização 
   Se o usuário acessa o web site hospedado no EC2 e faz upload de um aqruivo (foto, vídeo, print, etc), ele será armazenado no S3. Caso o sistema tenha que salvar informações novas ou até iniciais do cadastro desse usuário, isso vai para o RDS. Já o EBS é responsável por armazenar os arquivos temporários e de configurações da instância EC2.


## ➤ Fluxo de atualização de perfil de usuário com S3, Lambda e Dynamo DB. 
Esse fluxo mostra como funciona a atualização de uma foto de perfil usando serviços da AWS:  

- **S3 (Simple Storage Service)** - É um serviço de **armazenamento de objetos**, usado para guardar e acessar arquivos com mais facilidade. 
- **Lambda AWS** - Serviço de **computação sem servidor (serverless)**. Executa códigos automaticamente em resposta a eventos, sem precisar gerenciar servidores.  
- **Amazon DynamoDB** → **Banco de dados NoSQL** que é gerenciado pela AWS. Escalável e rápido para salvar e consultar informações.  

#### A arquitetura está exemplificada no diagrama a seguir: 

 ![Diagrama S3](images/diagrama-s3.png).

  ### Contextualização 
 1. O usuário envia uma nova foto de perfil.  
 2. A imagem é salva no **S3**.  
 3. O envio dispara uma função **Lambda**, que processa a imagem (por exemplo: validar e registrar o evento).  
 4. Os detalhes da imagem (metadados, como nome do arquivo e data do upload) são armazenados no **DynamoDB**. 

 ## ➤ Projeto de Arquitetura para E-commerce

Este projeto tem como base um trabalho anterior que realizei, voltado para um e-commerce de miniaturas, itens de decoração e ursos de pelúcia. A ideia é adaptar esse projeto para a nuvem utilizando os serviços da AWS, aplicando todos os conceitos aprendidos durante os estudos que tive até aqui.

Um e-commerce, naturalmente, precisa lidar com diferentes demandas. Com isso em mente, para gerar uma boa experinência do usuário e a funcionalidade do aplicativo, é fundamental planejar uma arquitetura que suporte variações de tráfego e ofereça estabilidade contra falhas. Garantindo escalabilidade, segurança e organização.






