﻿# modelo-conceitual-bd1
### Entidades e Atributos:

1. **Cliente**
   - **Atributos:** id_cliente (chave primária), nome, email, telefone.
   Representa os clientes do sistema.

2. **Endereço**
   - **Atributos:** rua, bairro, cidade, estado, pais_id_endereco.
   - **Descrição:** Guarda as informações sobre os endereços que podem estar associados a clientes ou locais de entrega.

3. **Pedido**
   - **Atributos:** id_pedido (chave primária), data_pedido, status, total.
   - **Descrição:** Contém informações sobre os pedidos realizados pelos clientes, incluindo a data, status do pedido e valor total.

4. **ItemPedido**
   - **Descrição:** Entidade associativa que relaciona os pedidos com os produtos, representando os itens dentro de um pedido.

5. **Produto**
   - **Atributos:** id_produto (chave primária), nome, descrição, preço.
   - **Descrição:** Detalha os produtos disponíveis para compra, com seu nome, descrição e preço.

6. **Estoque**
   - **Atributos:** id_estoque (chave primária), quantidade, tipo, localização.
   - **Descrição:** Gerencia as informações de estoque de cada produto, incluindo a quantidade disponível e a localização.

7. **Pagamento**
   - **Atributos:** id_pagamento (chave primária), status, tipo, data_pagamento.
   - **Descrição:** Trata dos registros de pagamento relacionados aos pedidos, detalhando o status, o tipo de pagamento e a data em que foi realizado.

8. **Cartão**
   - **Atributos:** codigo_id_cartao (chave primária), número, nome.
   - **Descrição:** Contém informações sobre os cartões de crédito/débito usados pelos clientes para realizar pagamentos.

### Relacionamentos:

1. **Cliente e Endereço:** Um cliente pode ter vários endereços, mas um endereço está associado a apenas um cliente (cardinalidade 1:N). Este relacionamento é chamado "localiza".

2. **Cliente e Pedido:** Um cliente pode realizar vários pedidos, mas cada pedido é feito por um único cliente (cardinalidade 1:N). Este relacionamento é denominado "Realiza".

3. **Pedido e ItemPedido:** Um pedido pode ter vários itens, e um item pertence a um único pedido (cardinalidade 1:N).

4. **ItemPedido e Produto:** Um produto pode estar em vários itens de pedidos, e um item de pedido refere-se a um único produto (cardinalidade 1:N).

5. **Produto e Estoque:** Cada produto tem um único registro de estoque, e cada registro de estoque refere-se a um único produto (cardinalidade 1:1). Este relacionamento é chamado "possui".

6. **Pedido e Pagamento:** Cada pedido tem um único pagamento, e cada pagamento está relacionado a um único pedido (cardinalidade 1:1). Este relacionamento é chamado "Paga".

7. **Pagamento e Cartão:** Um pagamento pode ser realizado com vários cartões (embora na prática isso seja menos comum), e um cartão pode ser utilizado para vários pagamentos (cardinalidade N:1). Este relacionamento é chamado "RealizadoCom".

8. **Cartão e Cliente:** Um cliente pode utilizar vários cartões, mas cada cartão é utilizado por um único cliente (cardinalidade 1:N). Este relacionamento é chamado "utiliza".
