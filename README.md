# aws-infra-atividade
Atividade da disciplina Infraestrutura em Nuvem com AWS

Atividade Prática: Configuração de Infraestrutura Básica na AWS

Primeiro para a parte da coneção SSH foi criado o par de chaves chamadas "aws_aula" seguindo a configuração padrão passada (RSA e como uso Windows .ppk):
![print1](AWS%20Prints/AWS_PRINT_1.png)
![print2](AWS%20Prints/AWS_PRINT_2.png)

Após isso foi criado o grupo de segurança SSH usando como regras de entrada o HTTP e SSH com qualquer origem:
![print3](AWS%20Prints/AWS_PRINT_3.png)
![print4](AWS%20Prints/AWS_PRINT_4.png)
![print5](AWS%20Prints/AWS_PRINT_5.png)

Depois foi criada a instancia EC2, escolhendo a imagem Amazon Linux 2023 AMI, arquitetura 64 bits (x86), tipo t2.micro, o par de charves "aws_aula", o grupo de segurança "aws-ssh", 20 GiB de armazenamento no gp3, perfil de instância IAM LabInstanceProfile e os dados do usuário com o script passado (user_data_ec2_zona_a.sh):
![print6](AWS%20Prints/AWS_PRINT_6.png)
![print7](AWS%20Prints/AWS_PRINT_7.png)
![print8](AWS%20Prints/AWS_PRINT_8.png)
![print9](AWS%20Prints/AWS_PRINT_9.png)
![print10](AWS%20Prints/AWS_PRINT_10.png)
![print11](AWS%20Prints/AWS_PRINT_11.png)

Criado grupo de segurança HTTP com regra de entrada HTTP com qualquer origem:
![print12](AWS%20Prints/AWS_PRINT_12.png)

Criado grupo de segurança para o banco de dados com duas regras de entrada para o PostgreSQL, a principal com origem no grupo web (criado acima) e a de testes com origem no grupo dev (criado para a primeira atividade):
![print13](AWS%20Prints/AWS_PRINT_13.png)
![print14](AWS%20Prints/AWS_PRINT_14.png)

Criado banco de dados RDS com o modo de criação padrão, engine PostgreSQL 17.2-R1, modelo gratuito, nome da instância "AWS_DB, autogerenciado com a senha padrão usada em aula, armazenamento de 20 GiB do tipo gp3, Performance Insights desativado, nome do banco de dados "aws_db", backup desativado e grupo de segurança "aws_db" criado anteriormente:
![print15](AWS%20Prints/AWS_PRINT_15.png)
![print16](AWS%20Prints/AWS_PRINT_16.png)
![print17](AWS%20Prints/AWS_PRINT_17.png)
![print18](AWS%20Prints/AWS_PRINT_18.png)
![print19](AWS%20Prints/AWS_PRINT_19.png)
![print20](AWS%20Prints/AWS_PRINT_20.png)
![print21](AWS%20Prints/AWS_PRINT_21.png)
![print22](AWS%20Prints/AWS_PRINT_22.png)
