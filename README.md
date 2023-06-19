### Visão Geral

Este repositório do GitHub contém um projeto de simulação de uma corretora de valores, com funcionalidades completas de compra e venda de ações através do home broker, visualização de indicadores financeiros via gráfico, além de outras características.

### Objetivo

O objetivo deste projeto é fornecer uma plataforma simulada de corretora de valores que permita aos usuários realizar operações de compra e venda de ações, acompanhar os indicadores financeiros em tempo real através de gráficos e receber notificações sobre mudanças significativas no mercado de ações. O projeto é construído usando tecnologias modernas como Go, Next.js, Nest.js, React e Apache Kafka.

### Principais Características

1. **Home Broker**: O projeto oferece uma interface intuitiva de home broker, permitindo que os usuários realizem operações de compra e venda de ações de forma rápida e fácil. Eles podem visualizar informações detalhadas sobre as ações, incluindo preços, volume de negociação e tendências históricas.

2. **Visualização de Indicadores**: O sistema utiliza gráficos interativos para exibir os principais indicadores financeiros, como preço das ações ao longo do tempo, volume de negociação, médias móveis, índices de mercado, entre outros. Os usuários podem personalizar a exibição dos gráficos e explorar diferentes períodos de tempo.

3. **Notificações de Mercado**: Os usuários têm a opção de receber notificações em tempo real sobre eventos relevantes no mercado de ações. Isso pode incluir mudanças significativas nos preços das ações, anúncios de empresas, divulgação de resultados financeiros, entre outros. As notificações são entregues através de diferentes canais, como e-mail, SMS ou notificações push.

4. **Integração com Apache Kafka**: O projeto utiliza o Apache Kafka como sistema de mensagens para processar e transmitir dados em tempo real. Ele permite que as informações de mercado sejam atualizadas continuamente e distribuídas para os usuários de forma eficiente e escalável.

### Tecnologias Utilizadas

O projeto faz uso das seguintes tecnologias:

- **Go**: É a linguagem de programação principal utilizada para desenvolver a lógica de negócios do projeto. Go é conhecida por sua eficiência, simplicidade e suporte para concorrência, tornando-a uma escolha adequada para aplicações de alto desempenho e escaláveis.

- **Next.js**: É um framework de desenvolvimento web em React que permite a criação de aplicações SSR (Server-Side Rendering) e SSG (Static Site Generation). Ele é usado para construir a interface do usuário da aplicação, fornecendo uma experiência interativa e responsiva.

- **Nest.js**: É um framework back-end em Node.js que facilita a criação de aplicativos escaláveis e eficientes. Ele fornece recursos como injeção de dependência, arquitetura em camadas e uma sintaxe declarativa para simplificar o desenvolvimento do servidor de aplicação.

- **React**: É uma biblioteca JavaScript para construção de interfaces de usuário. O React é usado em conjunto com o Next.js para criar componentes reutilizáveis, gerenciar o estado da aplicação e criar uma experiência de usuário

 dinâmica e responsiva.

- **Apache Kafka**: É uma plataforma de streaming distribuída que permite o processamento e a transmissão de eventos em tempo real. Ele é usado para a transmissão de dados do mercado de ações, atualizações de preços e notificações para os usuários do sistema.

### Contribuição

Contribuições para este projeto são bem-vindas. Se você deseja contribuir, siga as práticas recomendadas para desenvolvimento, faça fork do repositório, crie uma branch específica para sua contribuição e envie um pull request quando estiver pronto.

Lembre-se de fornecer uma descrição clara das alterações que você está propondo e adicione testes adequados para garantir a qualidade do código.

### Licença

Este projeto é licenciado sob a [MIT License](https://opensource.org/licenses/MIT), o que significa que você é livre para usá-lo, modificá-lo e distribuí-lo sob os termos da licença.

### Aviso Legal

Este projeto é uma simulação e não representa uma corretora de valores real. As operações realizadas e os indicadores exibidos são apenas para fins ilustrativos. Não deve ser considerado como aconselhamento financeiro ou recomendação de investimento. Sempre consulte um profissional financeiro qualificado antes de tomar qualquer decisão de investimento.