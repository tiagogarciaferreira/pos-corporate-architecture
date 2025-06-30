# 🏛️ Corporate Architecture – Documento de Definição de Arquitetura

Este repositório contém o trabalho desenvolvido para a disciplina de **Corporate Architecture**, com foco na criação de um **Documento de Definição de Arquitetura (DDA)**.

# ESTUDO DE CASO

Venda Geral é uma empresa de compras coletivas que tem como sua principal fonte de receita a venda de cupons de desconto em produtos de estabelecimentos comerciais parceiros, onde um percentual de toda a receita recebida pelo parceiro, ao final da promoção, é repassado à Venda Geral como pagamento dos serviços prestados de marketing e propaganda. Este percentual varia de acordo com os valores acertados em contrato de parceria entre a Venda Geral e seus parceiros.

A cadeia de valor da Venda Geral que o serviço de vendas de cupons é formada dos seguintes processos: 

1. Processos de estratégia:  
   1. Realizar Planejamento Estratégico  
      * Objetivo: Avaliar as tendências de mercado de consumo e definir o plano estratégico adequado. O plano estratégico consiste dos objetivos e ações estratégicas.  
   2. Planejar Ações de Marketing  
      * Objetivo: Traduzir as ações estratégicas do plano estratégico em ações de marketing, que podem ser de três tipos: campanhas publicitárias em canais de comunicação (TV, rádio, jornal, quiosques em shopping, etc.), links patrocinados na Internet e cupons de venda com descontos em produtos de parceiros. Todas as ações de marketing são tratadas como projetos pela Venda Geral.  
2. Processos core business:  
   1. Estabelecer Parcerias  
      * Objetivo: Negociar e formar parcerias com estabelecimentos comerciais rentáveis, gerando uma minuta de contrato que deve ser encaminhada ao Dept. de Contratação para efetivação do contrato.  
   2. Gerir Relacionamento com Consumidores  
      * Objetivo: Tratar qualquer manifestação dos consumidores (reclamações, sugestões, devoluções de cupons, etc.) que compram os cupons de desconto emitidos numa campanha.  
   3. Vender Cupons  
      * Objetivo: Oferecer um canal de vendas para os consumidores comprarem cupons de descontos dos produtos dos parceiros  
   4. Implementar Campanhas  
      * Objetivo: Executar as campanhas previamente planejadas. Eventualmente, uma nova campanha pode exigir uma nova solução de TI para disponibilizar no mercado (ex.: aplicativos móveis).  
3. Processos de suporte:  
   1. Gerir Finanças  
      * Objetivo: Emitir as notas fiscais relativas à venda dos cupons e ao pagamento dos serviços prestados em outras campanhas  
   2. Gerir Contratos  
      * Objetivos: Transformar uma minuta de contrato em um contrato assinado entre as partes, garantindo a fiscalização e o encerramento do contrato, aplicando as penalidades cabíveis quando um dos itens não for cumprido pelo parceiro.  
   3. Prover Assessoria Jurídica  
      * Objetivo: Respaldar as negociações de parceria, a gestão de contratos e o tratamento de manifestações do cliente ao emitir um parecer jurídico ao órgão solicitante.  
   4. Provisionar Soluções de TI  
      * Objetivos: Desenvolver uma solução de TI através de um projeto que esteja alinhado às ações de marketing planejadas ou à implementação de uma campanha 

Na Venda Geral, estão disponíveis as seguintes aplicações: 

* CRM (Customer Relationship Management) adquirido junto a um fornecedor X;  
* ERP (Enterprise Resource Planning) adquirido junto a um fornecedor X e que utiliza os seguintes pacotes e módulos pré-configurados:  
  * Módulo Contratos;  
  * Módulo Financeiro;  
* Sistema de Gerenciamento de Projetos desenvolvido internamente pela equipe de TI;  
* Sistema de Venda de Cupons (e-commerce) desenvolvido internamente pela equipe de TI;  
* Sistema de Registro e Acompanhamento de Negociação de Contratos desenvolvidos pela equipe de TI;  
* Google Ads para patrocinar links da Venda Geral nos sites de busca.

As principais entidades de informação que fluem entre os processos de negócio e são sustentados pelas aplicações são: 

* Anúncio;  
* Campanha;  
* Consumidor;  
* Contrato;  
* Cupom;  
* Parceiro;  
* Projeto;  
* Objetivo Estratégico;  
* Ação Estratégica;  
* Nota fiscal.

Recentemente, a Venda Geral mudou sua estratégia e decidiu investir, também, no mercado de varejo. Com essa estratégia em mente, o grupo decidiu adquirir a *Zé Pequeno Eletro*, uma empresa média de venda de eletrônicos e eletrodomésticos no varejo. O negócio da Zé Pequeno Eletro é baseado, basicamente, nos seguintes processos:

1. Processos *core business*:  
   1. Vender Produtos  
   2. Faturar Pedido  
   3. Entregar Pedido   
2. Processos de suporte:  
   1. Gerir Estoque  
   2. Gerenciar Logística de Produtos  
   3. Gerir Relacionamento com Clientes  
   4. Gerenciar Finanças

Para suportar estes processos, a Zé Pequeno Eletro contava com as seguintes aplicações, que foram compradas junto a diferentes fornecedores de software:

* Sistema de Clientes;  
* Sistema de Pedidos;  
* Sistema de Finanças;  
* Sistema de Distribuição de Produtos (Estoques e Centros de Distribuição).

Sua equipe foi contratada pelo CEO da Venda Geral para planejar como a Venda Geral deve ser arquitetada para suportar a nova estratégia. Escolha para o seu trabalho um possível direcionamento estratégico em relação ao modelo operacional que deverá ser respeitado na arquitetura futura, explicando a arquitetura de todos os processos com matrizes e diagramas:

* Centralização: integração e padronização da operação na Venda Geral  
  Neste modelo, a operação da Zé Pequeno Eletro deixa de existir e passa a ocorrer dentro da Venda Geral. Neste cenário, o objetivo está em racionalizar recursos e soluções, evitando duplicidade, para ter uma operação mais enxuta em uma única empresa.  
  Principais direcionamentos:  
  * Minimizar a diversidade de sistemas (maior integração entre as soluções);  
  * Reusar, com menor ou maior grau de adaptação, sempre que possível, os processos da Venda Geral para sustentar as novas operações de varejo;  
  * Todos os processos devem ser automatizados, ou suportados por pelo menos uma aplicação.  
* Diversidade: operação em empresas separadas, porém com integração/coordenação na parte de suporte pela Venda Geral  
  Neste modelo, os processos do core business das duas empresas continuam operando em separado (duas empresas distintas e independentes), porém é necessário integrar os resultados e informações para uma camada de suporte unificada. Neste cenário, o objetivo está em preservar os processos e sistemas, buscando a adaptação centralizada na Venda Geral da parte de suporte à operação.  
  Principais direcionamentos:  
  * Preservar os componentes do core business das duas empresas (resultados devem ser integrados);  
  * Buscar soluções integradas na Venda Geral para a camada de suporte e estratégia;  
  * Todos os processos devem ser automatizados, ou suportados por pelo menos uma aplicação.

> Projeto acadêmico desenvolvido para fins educacionais.
