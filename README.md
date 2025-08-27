# DIO-Forma-o-SQL-Database-Specialist
Repositorio para projetos praticos do curso Formação SQL Database Specialist da plataforma DIO.
# Modulo Entidade relacional com banco de dados 
## Projeto 1- Refinar um modelo de banco de dados relacional para e-comerce
### Objetivo: 
Modelar um contexto reduzido de e-commerce. Podendo escolher a ferramenta de modelagem para realizar o desafio. O modelo deve conter nescessariamente os seguintes pontos:

Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
Entrega – Possui status e código de rastreio;

### Procedimentos:
Primeiramente foi feito o mapeamento dos processos do e-commerce através de um  modelo de processo (BPMN / fluxograma de negócio) visando: Mostrar fluxo de atividades (ex.: Marketing → Pedido → Processamento → Entrega); Focar em como o sistema ou a empresa funcionam; Elementos representados: ações, etapas, eventos, decisões. Cabe destacar que como uma atividade para fins educaiconais algumas dimensões do negocio foram omitidas do sistemas visando a simplificação da atividade, notoriamente:
+ Tratamentos de exceção e cenários de erro
+ Presença loops de retry, rollback de transações,validação de pagamento antes do disparo da entrega 
+ Prevenção de  Fraudes
+ Escabilidade em momentos de alta demanda devido a ausencia de paralelismos e checkpoints
<img width="873" height="380" alt="Flux_ecomerce" src="https://github.com/user-attachments/assets/eabd850a-c26c-4143-9cc3-fea15377fff5" />



Finalizado a modelagem dos processo foram  ultlizadas ferrametas de IA generativa e  tecncias de prompt enginering para gerar uma modelagem em formato DER visual (diagrama entidade-relacionamento).
<img width="691" height="768" alt="der_ecommerce" src="https://github.com/user-attachments/assets/d89fc388-8fa5-44f0-af01-2905f65fdc86" />



## Projeto 2- Modelar um modelo de banco de dados relacional para uma garagem
### Objetivo: 
Modelar simplificadamente um  sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânicaque faz revisões e reparaos . Podendo escolher a ferramenta de modelagem para realizar o desafio. O modelo deve conter nescessariamente os seguintes pontos:


+Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas
+Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
+A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
+O valor de cada peça também irá compor a OSO cliente autoriza a execução dos serviços
+A mesma equipe avalia e executa os serviços
+Os mecânicos possuem código, nome, endereço e especialidade
+Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

### Procedimentos:
Primeiramente foi feito o mapeamento dos processos do e-commerce através de um  modelo de processo (BPMN / fluxograma de negócio) visando: Mostrar fluxo de atividades, Focar em como o sistema ou a empresa funcionam; Elementos representados: ações, etapas, eventos, decisões. Cabe destacar que como uma atividade para fins educaiconais algumas dimensões do negocio foram omitidas do sistemas visando a simplificação da atividade, notoriamente:
+ Tratamentos de exceção e cenários de erro
+ Presença loops de retry, rollback de transações,validação de pagamento antes do disparo da entrega 
+ Prevenção de  Fraudes
+ Escabilidade em momentos de alta demanda devido a ausencia de paralelismos e checkpoints

<img width="821" height="226" alt="flux_garage" src="https://github.com/user-attachments/assets/7bac8fba-feee-4793-88d2-1873ec252ff4" />


Finalizado a modelagem dos processo foram  ultlizadas ferrametas de IA generativa e  tecncias de prompt enginering para gerar uma modelagem em formato DER visual (diagrama entidade-relacionamento).
<img width="877" height="804" alt="DER_Garage" src="https://github.com/user-attachments/assets/a8b4ea63-e51f-49c8-b0e8-8bc2f65472dd" />

