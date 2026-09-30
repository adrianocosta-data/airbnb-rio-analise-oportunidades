# Análise de Oportunidades para Novos Anfitriões — Airbnb Rio

Projeto de análise de dados desenvolvido no **Power BI** com dados públicos do **Inside Airbnb** para identificar bairros do Rio de Janeiro com potencial para novos anfitriões de locação de curta temporada.

A análise combina três dimensões principais — **receita estimada, ocupação e concorrência** — para comparar bairros sob diferentes perspectivas e apoiar uma triagem inicial de oportunidades.

**Tecnologias:** Power BI • Power Query • DAX • Git • GitHub

[Ver dashboard em PDF](03-visualizacoes/analise-final.pdf) •
[Arquivo Power BI](02-powerbi/airbnb-rio-analise-final.pbix) •
[Dicionário de dados](04-documentacao/dicionario-de-dados.xlsx)

O dashboard foi desenvolvido em duas camadas:

- **Visão Simplificada:** leitura rápida dos principais indicadores, ranking e destaques de oportunidade.
- **Visão Analítica:** exploração mais detalhada das relações entre receita, ocupação e concorrência.

## Dashboard

### Visão Simplificada

![Visão Simplificada](03-visualizacoes/visão-simplificada.png)

### Principais achados

- **Leblon** aparece como a melhor oportunidade geral no cenário padrão do modelo.
- **Ipanema** se destaca pela combinação entre receita estimada e ocupação.
- **Urca** apresenta uma combinação favorável entre receita e menor pressão competitiva.

> O ranking é uma ferramenta de triagem e depende dos filtros e dos pesos atribuídos a receita, ocupação e concorrência.
---

## Objetivo do Projeto

Identificar quais bairros do Rio de Janeiro apresentam melhores oportunidades para novos hosts de locação de curta temporada, considerando:

- potencial de receita;
- consistência da demanda;
- pressão competitiva.

O objetivo é transformar os dados públicos do Airbnb em informações úteis para apoiar decisões de entrada e expansão no mercado de hospedagem de curta duração.

---

## Critérios de Sucesso

O projeto será considerado bem-sucedido se conseguir:

- identificar bairros com maior potencial de receita;
- encontrar regiões com boa demanda e menor pressão competitiva;
- criar um ranking de oportunidades para novos hosts;
- comparar bairros sob diferentes perspectivas de desempenho;
- transformar os resultados em recomendações acionáveis;
- explicitar as limitações da análise e evitar conclusões além do que os dados permitem.

---

## Problema de Negócio

Um investidor ou novo host interessado no mercado de locação de curta temporada no Rio de Janeiro não possui, de forma imediata, uma visão clara sobre quais bairros combinam:

- bom potencial de faturamento;
- demanda consistente;
- menor pressão competitiva.

Bairros muito procurados podem apresentar receitas elevadas, mas também forte concorrência. Por outro lado, regiões menos saturadas podem oferecer oportunidades interessantes mesmo com menor volume absoluto de receita.

A análise busca organizar essas diferentes dimensões para identificar bairros que merecem maior atenção e apoiar decisões mais informadas sobre onde iniciar ou expandir operações de hospedagem.

> **Importante:** a análise não estima retorno financeiro real sobre o investimento, pois não inclui custos de aquisição, financiamento, manutenção, impostos ou operação do imóvel.

---

## Hipóteses Iniciais

Antes da construção do dashboard, foram definidas algumas hipóteses para orientar a exploração dos dados.

1. **Zona Sul com alta receita e alta concorrência**  
   Bairros como Copacabana e Ipanema tendem a apresentar receitas elevadas devido à forte demanda turística, mas também enfrentam maior pressão competitiva.

2. **Menor saturação pode compensar menor receita**  
   Bairros menos turísticos podem apresentar faturamento inferior aos destinos tradicionais, porém oferecer oportunidades devido ao menor número de anúncios concorrentes.

3. **Imóveis inteiros apresentam maior potencial de receita**  
   Anúncios classificados como casa ou apartamento inteiro tendem a gerar receitas superiores às de quartos privados ou compartilhados.

4. **Avaliações podem estar associadas à ocupação**  
   Bairros ou anúncios com melhores avaliações dos hóspedes podem apresentar maiores taxas de ocupação.

5. **Existem oportunidades além dos bairros turísticos tradicionais**  
   Alguns bairros podem apresentar um equilíbrio mais favorável entre receita, ocupação e concorrência, tornando-se alternativas interessantes para novos anfitriões.

---

## Perguntas de Negócio

### 1. Potencial de Receita

- Quais bairros apresentam maior receita estimada?
- Qual é o ADR estimado por bairro?
- Como o potencial de receita varia entre os diferentes tipos de acomodação?
- Quais bairros apresentam maior RevPAR estimado?
- A sazonalidade influencia significativamente os resultados observados?

### 2. Consistência da Demanda

- Quais bairros apresentam as maiores e menores taxas de ocupação estimada?
- Existem bairros com boa ocupação mesmo fora dos destinos turísticos mais conhecidos?
- Existe relação entre avaliações dos hóspedes e ocupação?
- Os resultados sugerem demanda consistente ou dependência de períodos específicos?

### 3. Pressão Competitiva

- Quais bairros concentram o maior número de anúncios?
- Quais áreas apresentam maior pressão competitiva?
- Existe relação entre maior concorrência e menor ocupação?
- Quais bairros combinam receita relevante com menor número de concorrentes?

### 4. Oportunidades para Novos Hosts

- Quais bairros oferecem o melhor equilíbrio entre receita, ocupação e concorrência?
- Quais bairros se destacam quando receita e ocupação recebem maior atenção?
- Quais bairros apresentam boa receita com menor pressão competitiva?
- O ranking de oportunidade altera a percepção obtida ao analisar apenas receita?
- Quais regiões merecem investigação adicional antes de uma decisão de entrada no mercado?

---

## Escopo da Análise

Para evitar comparações pouco representativas, o ranking principal considera apenas bairros com **pelo menos 100 anúncios** na base analisada.

Os bairros são avaliados principalmente por três dimensões:

- **Receita:** capacidade de geração de receita estimada.
- **Demanda:** representada pela ocupação estimada.
- **Concorrência:** representada pelo número de anúncios ativos.

O projeto identifica sinais de oportunidade no mercado de hospedagem, mas não substitui uma análise completa de investimento imobiliário.

---

## Dados Utilizados

Os dados são públicos e foram obtidos no **Inside Airbnb**, referentes ao município do Rio de Janeiro.

A coleta utilizada no projeto corresponde a **24 de junho de 2026**.

### `listings.csv`

Base principal da análise, com **48.713 anúncios**.

Entre as variáveis utilizadas estão:

- identificador do anúncio;
- bairro;
- latitude e longitude;
- tipo de acomodação;
- capacidade;
- quartos e camas;
- preço da diária;
- avaliações;
- disponibilidade;
- receita estimada nos últimos 365 dias;
- ocupação estimada nos últimos 365 dias.

### `calendar.csv`

Base complementar com a disponibilidade diária dos anúncios.

O calendário utilizado cobre aproximadamente um ano:

**26/06/2026 a 25/06/2027**

Ele foi usado principalmente para investigar a disponibilidade e compreender as limitações da métrica de ocupação estimada.

---

## Controle de Qualidade dos Dados

Durante o projeto foi identificado um problema de compatibilidade entre uma versão inicial do `calendar.csv` e a base de anúncios.

Ao comparar os identificadores dos anúncios entre as duas tabelas, nenhuma correspondência foi encontrada.

Uma nova versão do `calendar.csv`, correspondente à coleta de **24/06/2026**, foi então obtida no Inside Airbnb. Após a substituição, os identificadores da base principal passaram a encontrar correspondência no calendário.

Esse processo foi importante para evitar a utilização de bases pertencentes a coletas incompatíveis.

---

## Preparação dos Dados

A limpeza e transformação foram realizadas principalmente no **Power Query**.

As principais etapas incluíram:

- seleção das colunas relevantes;
- definição dos tipos de dados;
- limpeza do campo de preço;
- conversão das variáveis numéricas;
- renomeação das colunas para português;
- tradução das categorias de tipo de acomodação;
- padronização dos nomes dos bairros;
- tratamento de inconsistências de grafia e acentuação;
- construção de uma dimensão de região;
- validação dos relacionamentos entre as tabelas.

### Padronização dos bairros

Foram encontradas diferenças de escrita entre os nomes dos bairros, incluindo:

- diferenças de acentuação;
- grafias diferentes;
- bairros presentes na tabela de anúncios, mas ausentes inicialmente na dimensão de região.

Essas inconsistências foram corrigidas antes da utilização dos filtros por região.

---

## Modelo de Dados

O modelo foi estruturado principalmente a partir das seguintes tabelas:

- `fato_anuncios` — informações dos anúncios;
- `calendar` — disponibilidade diária;
- `Dim região` — classificação dos bairros por região;
- `Medidas` — medidas DAX utilizadas no dashboard.

A tabela `fato_anuncios` funciona como a principal fonte das análises de bairro, receita, ocupação e concorrência.

O relacionamento entre `fato_anuncios` e `calendar` utiliza o identificador do anúncio:

`fato_anuncios[ID Anúncio]` → `calendar[listing_id]`

---

## Métricas e KPIs

### Receita Mediana Estimada

A mediana foi priorizada em diversas análises porque a distribuição de preços e receitas apresenta valores extremos.

Isso reduz a influência dos outliers e representa melhor o desempenho típico dos anúncios de um bairro.

### ADR Estimado

**ADR (Average Daily Rate)** representa o valor médio da diária.

Ele ajuda a compreender quanto os anúncios conseguem cobrar pelas noites comercializadas.

### Taxa de Ocupação Estimada

A ocupação utilizada na análise vem da variável:

`estimated_occupancy_l365d`

No dashboard, a medida é calculada como a média da ocupação estimada dos anúncios no contexto selecionado.

Essa variável representa uma **estimativa**, e não reservas diretamente observadas.

### RevPAR Estimado

**RevPAR (Revenue per Available Room)** combina preço e ocupação em um único indicador.

Conceitualmente:

`RevPAR = ADR × Taxa de Ocupação`

### Número de Anúncios

O número de anúncios é utilizado como aproximação da **pressão competitiva** existente em cada bairro.

Quanto maior a quantidade de anúncios, maior tende a ser a quantidade de anfitriões disputando a mesma demanda.

---

## Índice de Oportunidade

Para comparar os bairros em múltiplas dimensões foi criado um **Índice de Oportunidade**.

O índice combina:

- **Receita:** 40%;
- **Ocupação:** 30%;
- **Concorrência:** 30%.

### Fórmula conceitual

`Índice de Oportunidade = Receita × 40% + Ocupação × 30% + Concorrência × 30%`

Os componentes foram normalizados antes da combinação para permitir a comparação de variáveis em escalas diferentes.

### Score de Receita

Representa a posição relativa do bairro em relação à receita mediana estimada.

### Score de Ocupação

Representa a posição relativa do bairro em relação à taxa de ocupação estimada.

### Score de Concorrência

O número de anúncios foi transformado em um score no qual:

**menor concorrência → maior pontuação**

Como alguns bairros possuem quantidade de anúncios muito superior aos demais, foi utilizada transformação logarítmica antes da normalização para reduzir a influência de valores extremos.

---

## Critério de Elegibilidade

O ranking considera apenas bairros com:

**100 ou mais anúncios**

Esse limite foi adotado para reduzir a influência de bairros com poucas observações, nos quais pequenas variações poderiam produzir rankings pouco representativos.

O valor de 100 anúncios é uma decisão metodológica deste projeto e não representa um padrão definido pelo Inside Airbnb.

---

## Interpretação do Ranking

O ranking deve ser interpretado como uma ferramenta de **triagem de oportunidades**, e não como uma recomendação automática de investimento.

Um bairro bem classificado apresenta uma combinação relativamente favorável entre:

- receita estimada;
- ocupação estimada;
- pressão competitiva.

Entretanto, o índice não considera fatores como:

- preço de aquisição do imóvel;
- aluguel;
- condomínio;
- impostos;
- manutenção;
- financiamento;
- regulamentação;
- custos operacionais.

Por isso, um bairro com score elevado deve ser entendido como um candidato para investigação adicional.

---

# Respostas às Perguntas de Negócio

## 1. Potencial de Receita

### Quais bairros apresentam maior potencial de receita?

Os resultados mostram que bairros da Zona Sul continuam aparecendo entre os mercados com maior potencial de receita estimada.

No cenário padrão da Visão Simplificada, bairros como **Leblon e Ipanema** aparecem entre os principais destaques.

Entretanto, analisar somente receita pode ser enganoso, pois bairros com maior faturamento potencial também podem apresentar níveis elevados de concorrência.

### Qual é o ADR estimado por bairro?

O ADR varia significativamente entre os bairros.

Bairros mais valorizados e com forte demanda turística tendem a apresentar tarifas diárias mais elevadas.

O ADR foi utilizado principalmente em conjunto com a ocupação para construir o RevPAR estimado.

### Como o potencial de receita varia entre os tipos de acomodação?

O dashboard permite filtrar a análise por tipo de acomodação e comparar:

- imóvel inteiro;
- quarto privado;
- quarto compartilhado;
- quarto de hotel.

A tipologia altera de forma relevante os resultados observados.

Entretanto, esta versão do projeto não realizou um teste estatístico específico para determinar se imóveis inteiros apresentam receita sistematicamente superior às demais categorias em todos os bairros.

**Conclusão:** a pergunta pode ser explorada pelo dashboard, mas não foi respondida de forma conclusiva nesta versão.

### Como a sazonalidade influencia a receita?

A sazonalidade não foi analisada em profundidade nesta versão do projeto.

O `calendar.csv` cobre aproximadamente um ano, mas foi utilizado principalmente para investigar disponibilidade e validar a integração entre as bases.

**Status: não avaliada de forma conclusiva.**

---

## 2. Consistência da Demanda

### Quais bairros apresentam maiores taxas de ocupação estimada?

A taxa de ocupação varia entre os bairros e foi utilizada como principal indicador de demanda no ranking.

Bairros com ocupação elevada não são necessariamente os melhores candidatos para novos hosts, pois também podem apresentar maior concorrência.

### A indisponibilidade do calendário confirma a ocupação estimada?

Não diretamente.

Durante o projeto, a taxa de ocupação estimada foi comparada com a proporção de datas indisponíveis do `calendar.csv`.

Em bairros como Copacabana e Ipanema foram observadas diferenças relevantes entre as duas métricas.

Isso não significa necessariamente que a ocupação estimada esteja incorreta, pois:

- a ocupação do Inside Airbnb é uma estimativa;
- datas indisponíveis podem representar reservas;
- datas também podem ser bloqueadas pelo próprio anfitrião;
- as métricas possuem metodologias diferentes.

Portanto, a indisponibilidade foi utilizada como indicador complementar, e não como validação direta da ocupação estimada.

### Existe relação entre avaliações e ocupação?

A hipótese foi considerada durante a definição inicial do projeto, mas não foi testada de forma suficientemente aprofundada para estabelecer uma conclusão confiável.

**Status: não avaliada de forma conclusiva.**

### Existem bairros com boa demanda fora dos destinos turísticos tradicionais?

Sim.

A análise mostra que observar apenas os bairros turísticos mais conhecidos pode esconder mercados com combinações interessantes de ocupação, receita e menor concorrência.

---

## 3. Pressão Competitiva

### Quais bairros concentram maior número de anúncios?

A quantidade de anúncios varia fortemente entre os bairros.

Destinos turísticos tradicionais apresentam maior concentração de imóveis, o que pode aumentar a pressão competitiva enfrentada por novos anfitriões.

### Existe relação entre alta concorrência e menor ocupação?

Os dados permitem comparar as duas dimensões, mas não foi estabelecida uma relação causal entre concorrência e ocupação.

Um bairro pode apresentar simultaneamente:

- alta concorrência;
- alta ocupação;
- alta receita.

Portanto, concorrência elevada não deve ser interpretada automaticamente como baixa demanda.

### Quais bairros combinam boa receita com menor concorrência?

Essa pergunta é representada diretamente no gráfico de:

**RevPAR estimado × número de anúncios**

O gráfico ajuda a identificar bairros posicionados mais à direita e abaixo, combinando:

- maior RevPAR estimado;
- menor número de anúncios.

Esses bairros são tratados como candidatos para investigação adicional, e não como recomendações automáticas de investimento.

---

## 4. Oportunidades para Novos Hosts

### Quais bairros oferecem o melhor equilíbrio entre receita, ocupação e concorrência?

Para responder essa pergunta foi criado o **Índice de Oportunidade**.

No cenário padrão da Visão Simplificada, o dashboard destaca:

- **Leblon** — melhor oportunidade geral segundo o índice;
- **Ipanema** — destaque em receita + ocupação;
- **Urca** — destaque em receita + menor concorrência.

Esses resultados são dinâmicos e podem mudar quando o usuário altera os filtros de região, bairro ou tipo de acomodação.

### O ranking muda a percepção obtida ao analisar apenas receita?

Sim.

Um bairro com receita elevada pode perder posições quando também apresenta:

- alta concorrência;
- menor ocupação relativa.

Da mesma forma, um bairro com receita um pouco menor pode subir no ranking ao apresentar:

- boa ocupação;
- menor pressão competitiva.

Esse é o principal valor do Índice de Oportunidade: evitar decisões baseadas em uma única métrica.

### Quais bairros representam oportunidades pouco exploradas?

A análise identifica bairros que merecem investigação adicional quando apresentam combinações favoráveis de:

- RevPAR;
- ocupação;
- menor número de anúncios.

Esses bairros devem ser tratados como candidatos para uma segunda etapa de análise, incluindo custos imobiliários e operacionais.

---

# Validação das Hipóteses Iniciais

| Hipótese | Resultado | Interpretação |
|---|---|---|
| Zona Sul apresenta alta receita e alta concorrência | Parcialmente confirmada | Bairros da Zona Sul aparecem entre os destaques de receita, mas o nível de concorrência varia entre eles. |
| Bairros menos turísticos podem compensar menor receita com menor concorrência | Parcialmente confirmada | A análise encontrou bairros que ganham relevância quando a concorrência é considerada, mas isso não garante maior retorno financeiro. |
| Imóveis inteiros geram mais receita que quartos privados | Não avaliada de forma conclusiva | O dashboard permite a comparação, mas não foi realizado teste específico suficiente para confirmar a hipótese em toda a amostra. |
| Melhores avaliações estão associadas a maior ocupação | Não avaliada de forma conclusiva | A relação não foi testada de maneira suficiente para sustentar uma conclusão. |
| Existem bairros com melhor equilíbrio entre receita, ocupação e concorrência | Confirmada dentro do modelo | O Índice de Oportunidade identifica diferenças relevantes quando as três dimensões são analisadas conjuntamente. |

---

# Principais Resultados

A análise mostrou que avaliar bairros apenas pela receita estimada não é suficiente para identificar oportunidades para novos hosts.

Os principais resultados foram:

- bairros da Zona Sul aparecem com frequência entre os maiores níveis de receita e ocupação;
- mercados mais valorizados também podem apresentar maior pressão competitiva;
- alguns bairros ganham relevância quando receita, ocupação e concorrência são avaliadas em conjunto;
- o Índice de Oportunidade altera a leitura obtida quando se observa apenas faturamento;
- a concorrência precisa ser interpretada junto com a demanda;
- o uso de mediana reduziu a influência de valores extremos;
- a comparação com o `calendar.csv` mostrou que indisponibilidade e ocupação estimada não são métricas equivalentes.

Na configuração padrão da Visão Simplificada, o dashboard destaca:

- **Leblon** — melhor oportunidade geral segundo o índice;
- **Ipanema** — destaque na combinação entre receita e ocupação;
- **Urca** — destaque na combinação entre receita e menor pressão competitiva.

Esses resultados são dinâmicos e podem mudar conforme os filtros aplicados no dashboard.

---

# Recomendações

Os resultados devem ser utilizados como ponto de partida para uma análise de investimento mais detalhada.

Para um novo host, recomenda-se:

1. **Não escolher um bairro apenas pela receita estimada.**  
   Avaliar conjuntamente ocupação e pressão competitiva.

2. **Investigar os bairros destacados pelo ranking.**  
   O score serve como ferramenta de triagem, indicando mercados que merecem análise adicional.

3. **Comparar diferentes tipos de acomodação.**  
   O desempenho pode mudar significativamente entre imóveis inteiros, quartos privados e outras categorias.

4. **Avaliar custos antes da decisão final.**  
   Preço de aquisição, aluguel, condomínio, manutenção, impostos e financiamento podem alterar completamente a viabilidade econômica.

5. **Considerar o contexto local.**  
   Regulamentação, infraestrutura, segurança, mobilidade e perfil dos hóspedes não estão totalmente representados na base analisada.

O dashboard identifica sinais de oportunidade, mas não determina automaticamente onde investir.

---

# Limitações da Análise

## Ocupação estimada

A variável de ocupação utilizada é uma estimativa produzida pelo Inside Airbnb.

Ela não representa diretamente reservas confirmadas.

A indisponibilidade presente no `calendar.csv` também não pode ser tratada como ocupação real, pois uma data pode estar indisponível por diferentes motivos, incluindo bloqueios realizados pelo anfitrião.

## Custos não considerados

A análise não inclui:

- preço de aquisição do imóvel;
- aluguel;
- financiamento;
- condomínio;
- impostos;
- manutenção;
- limpeza;
- taxas de plataformas;
- custos operacionais.

Por esse motivo, o projeto não calcula retorno sobre investimento real.

## Pesos do Índice de Oportunidade

O ranking utiliza:

- Receita: 40%;
- Ocupação: 30%;
- Concorrência: 30%.

Outras combinações de pesos podem produzir rankings diferentes.

## Critério mínimo de anúncios

O ranking considera apenas bairros com pelo menos 100 anúncios.

O limite foi definido para reduzir a influência de amostras pequenas, mas permanece uma decisão metodológica do projeto.

## Concorrência

O número de anúncios é utilizado como aproximação da pressão competitiva.

Essa métrica não considera fatores como:

- qualidade dos imóveis concorrentes;
- preço;
- avaliações;
- capacidade;
- disponibilidade;
- localização dentro do próprio bairro.

## Sazonalidade

A sazonalidade não foi analisada em profundidade nesta versão.

Apesar da utilização do `calendar.csv`, não foi construída uma análise temporal completa de receita e demanda ao longo do ano.

## Relações entre variáveis

Relações observadas entre receita, ocupação, concorrência ou avaliações não devem ser interpretadas automaticamente como relações causais.

Os resultados são descritivos e exploratórios.

---

# Ferramentas Utilizadas

- **Power BI Desktop** — modelagem, medidas, visualizações e dashboard;
- **Power Query** — limpeza, transformação e padronização dos dados;
- **DAX** — métricas, scores e ranking de oportunidade;
- **Figma** — desenvolvimento e ajuste do layout visual;
- **Inside Airbnb** — fonte dos dados públicos.

### Principais técnicas aplicadas

- tratamento e transformação de dados;
- modelagem relacional;
- criação de tabela dimensão;
- padronização de categorias;
- criação de medidas DAX;
- normalização de indicadores;
- construção de ranking multicritério;
- análise de receita, demanda e concorrência;
- validação de relacionamentos entre bases;
- construção de dashboards orientados a perguntas de negócio.

---

# Dashboard

O dashboard foi dividido em duas páginas com objetivos diferentes.

## Visão Simplificada

A **Visão Simplificada** foi desenvolvida para permitir uma leitura rápida dos principais resultados.

Ela apresenta:

- filtros por região, bairro e tipo de acomodação;
- receita mediana anual;
- ADR estimado;
- RevPAR estimado;
- taxa de ocupação estimada;
- ranking de oportunidade;
- relação entre receita e ocupação;
- relação entre receita e concorrência;
- destaques dinâmicos de oportunidade;
- recomendação;
- limitações resumidas da análise.

---

## Visão Analítica

A **Visão Analítica** foi desenvolvida para permitir uma investigação mais detalhada dos resultados.

Ela permite explorar:

- receita estimada por bairro;
- ADR;
- RevPAR;
- ocupação estimada;
- número de anúncios;
- pressão competitiva;
- relação entre RevPAR e concorrência;
- bairros que merecem investigação adicional;
- diferenças entre tipos de acomodação e regiões.

Enquanto a Visão Simplificada prioriza comunicação e síntese, a Visão Analítica oferece maior profundidade para explorar os fatores que explicam os resultados.

![Visão Analítica](03-visualizacoes/visão-analítica.png)
---

# Conclusão

O projeto mostrou que identificar oportunidades para novos hosts exige mais do que observar quais bairros apresentam maior receita estimada.

Mercados com alto faturamento também podem apresentar forte concorrência, enquanto bairros com receita um pouco menor podem oferecer combinações interessantes de demanda e menor saturação.

Para representar esse equilíbrio, foi criado um **Índice de Oportunidade**, combinando:

- receita — 40%;
- ocupação — 30%;
- concorrência — 30%.

A análise mostra que o ranking multidimensional produz uma leitura diferente daquela obtida ao considerar apenas receita.

No cenário padrão do dashboard, **Leblon, Ipanema e Urca** aparecem sob diferentes perspectivas de oportunidade. Esses resultados, porém, dependem das métricas, dos pesos definidos e dos filtros selecionados.

O projeto também evidenciou a importância da qualidade dos dados. Durante a análise foi identificado um `calendar.csv` incompatível com a base de anúncios, e a comparação dos identificadores permitiu detectar e corrigir o problema antes que ele afetasse as conclusões.

Por fim, os resultados devem ser interpretados como uma ferramenta de **triagem e apoio à decisão**, e não como uma recomendação automática de investimento.

Uma decisão real exigiria complementar a análise com informações como:

- preço de aquisição ou aluguel do imóvel;
- custos operacionais;
- impostos e condomínio;
- regulamentação;
- sazonalidade;
- características específicas do imóvel;
- contexto urbano e localização dentro de cada bairro.

O principal resultado do projeto, portanto, não é indicar simplesmente “onde investir”, mas oferecer uma estrutura de análise que permita comparar bairros de forma mais consistente e identificar quais mercados merecem investigação adicional.
