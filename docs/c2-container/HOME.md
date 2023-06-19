# c2-container

![diagram](https://www.plantuml.com/plantuml/svg/0/jLJBSjD04BphAmPVR5SbzeKJfoJ6PHuXWJoAugIQI1DBU7T7x4CufFYOL0wSEF85_Z5c9MCxiLC51owgtTcPtkwUMHquZzO7hP9dfSbKo0aAxoltOZYq-7KmBNqHhe8Zcx7nPFmWOpt4t9PeQXMgC1mztt-lqFZBTyT3XPwSbr0wYjbpFwZ-2pAMXcoBdHmVVZgzl4W_lhvubHwF9-EJbxr-agooqYCE9aTxqtEUirbAywn0CwNKtJXFUWywvsLS80Y_ArQkMTIes9Bhz6yJW1LMJwFFYXJLbAsmZyM7xLfphEesvzsEn2SSlsVaAZPkSLUJWeeja8bYBLfWqAGA2RK1ptBcBG42NvFr22I86eLwH0vQljQJrQN1d05zMVCUS017dt4lLbLaSV5ZSTyo4SYSkWCOAvGKkxW3cbCMV2mc3VNYJdnsu0jBcBjOSirMJ43d5ZzDPjdmeDFV5FyXKA1qFFSzh30hA9tXzGmV-gV9E9oIG4VrXqqUl8rvpLuk-4OcNWB2JrA5xozoq5iQ5o5a22eRrTSasljWk6Kc1hqvFprvYXDRyIUDhJMavAxJk8THku-NBvSmOHcfQTkSZAueaed5nctV3cBMfWYeK0w_19BkuOx6IukTp4yc-ksMI09BKx5AUh6lv524TO-OPzsd9BNLcI_PR0YxM4V_Lju36f5SBi6Ar1CYyZ_4eAacKvTBvRlSaE6IUS9bQmLPv8YUCrAFvcHNX_JQyyQ5VwXg6hGgUfIs_Kx7ZOgOfjS4jz9sMpvYHNvxQlFr-rdns0dmwBsqL70DTj_yAvRJ_Jr93aIQ_Df-0m00)

No segundo nível podemos verificar, de forma mais detalhada, como a arquitetura do _Code Invest_ está interligada aos seus componentes, além das tecnologias que fazem parte deste ecossistema.

### Requisitos funcionais

- Simulador da bolsa possui um algoritmo ligeiramente complexo para fazer o match das ordens de compra e venda

### Requisitos não funcionais

- As operações devem ser "_in memory_" a fim aumentar a agilidade na execução do mesmo, e para isso as principais alocações precisam ficar na memória _heap_

- Garantia de _memory safe_ a partir do recurso de _channels_ da linguagem Go

### Algoritmo de _match_ das ordens de compra e venda

Esse algoritmo consiste em 2 filas (uma de compra e uma de venda) e será feito comparações entre elas para conseguir conciliar a oferta com a demanda da melhor forma possível. Veja a ilustração abaixo:

![](../../assets/funcionamento-das-filas.png)

Cada vez que uma ordem de compra e venda dão "match", é gerado uma transação que será publicada no Apache Kafka no formato JSON.

### _Memory safe_ com _channels_

A fim de evitar erros como _race condition_ o qual ocorre quando 2 ou + threads tentam alterar um valor ao mesmo tempo.

Para isso, como solução foi adotado o recurso de _channels_ da linguagem Go que fornece um "canal" de comunicação entre 2 ou + threads e o dado que está nesse canal será coletado por uma dessas threads conectadas a esse canal.

O papel das _channels_ na aplicação é para que todas as ordens de compra e venda sejam enviadas a um único _channel_ de input para serem registradas no "livro" (_Book_) de compra/venda.

![](../../assets/book-channel.png)

Além disso, quando ocorre um "match" é criado uma transação que será enviada a um _channel_ de output para assim ser armazenado no Apache Kafka

![](../../assets/book-transaction-channel.png)
