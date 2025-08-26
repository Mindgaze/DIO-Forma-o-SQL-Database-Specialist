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

Finalizado a modelagem dos processo foram  ultlizadas ferrametas de IA generativa e  tecncias de prompt enginering para gerar uma modelagem em formato DER visual (diagrama entidade-relacionamento) com as seguintes caractristicas: 
#### 1. Cliente

cliente_id (PK)

nome

email

telefone

tipo_cliente (ENUM: PF, PJ)

#### 2. Cliente_PF (especialização 1:1)

cliente_id (PK, FK → Cliente)

cpf

#### 3. Cliente_PJ (especialização 1:1)

cliente_id (PK, FK → Cliente)

cnpj

razao_social

#### 4. Produto

produto_id (PK)

nome

descricao

preco

categoria

#### 5. Estoque

estoque_id (PK)

produto_id (FK → Produto)

quantidade_disponivel

quantidade_reservada

disponibilidade (boolean/status)

estimativa_entrega (dias)

#### 6. Pedido

pedido_id (PK)

cliente_id (FK → Cliente)

data_pedido

valor_total

status_pedido (ex.: aberto, pago, enviado, cancelado)

#### 7. ItemPedido

item_id (PK)

pedido_id (FK → Pedido)

produto_id (FK → Produto)

quantidade

preco_unitario

#### 8. FormaPagamento

pagamento_id (PK)

tipo (cartão, boleto, pix)

detalhes (ex.: últimos dígitos cartão)

#### 9. Pedido_Pagamento (N:N)

pedido_id (FK → Pedido)

pagamento_id (FK → FormaPagamento)

valor_pago

#### 10. Entrega

entrega_id (PK)

pedido_id (FK → Pedido)

status_entrega (ex.: em trânsito, entregue, devolvido)

codigo_rastreio

data_envio

data_entrega_prevista

data_entrega_real

 #### Principais Relações

Cliente 1:1 Cliente_PF/PJ (garante exclusividade PF ou PJ).

Cliente 1:N Pedido.

Pedido 1:N ItemPedido.

Produto 1:N ItemPedido.

Produto 1:1/N Estoque.

Pedido N:N FormaPagamento via Pedido_Pagamento.

Pedido 1:1 Entrega.
