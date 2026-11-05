# CliniData — Healthcare Analytics Dashboard

**Plataforma de Análise e Visualização de Dados de Atendimentos Clínicos**

**Tecnologias:** Python | Pandas | KNIME | Power BI | GitHub

**Status:** Planejamento e Especificação Técnica

**Modalidade:** Projeto Acadêmico Individual

## Sobre o Projeto

O **CliniData** é um projeto de análise de dados voltado ao acompanhamento de atendimentos clínicos por meio de indicadores e dashboards interativos.

A proposta é transformar registros operacionais em informações organizadas, acessíveis e visualmente compreensíveis, contribuindo para a identificação de padrões, o monitoramento da demanda e o apoio à tomada de decisões administrativas.

O projeto integra ferramentas de tratamento, processamento e visualização de dados, utilizando Python, KNIME e Power BI.

---

## 1. Termo de Abertura do Projeto (Project Charter)

### 1.1 Título do Projeto

**CliniData — Healthcare Analytics Dashboard**

### 1.2 Problema Real

Clínicas e unidades de saúde produzem diariamente informações relacionadas a atendimentos, especialidades e cancelamentos.

Entretanto, quando esses dados são armazenados em planilhas sem padronização ou mecanismos adequados de análise, torna-se difícil identificar tendências, acompanhar indicadores operacionais e obter informações relevantes para a gestão.

Essa dificuldade pode comprometer a compreensão da demanda e tornar o processo de tomada de decisão menos eficiente.

### 1.3 Proposta de Valor

O CliniData propõe uma solução de Business Intelligence (BI) capaz de transformar dados brutos de atendimentos clínicos em indicadores e visualizações interativas.

O diferencial está na integração entre o tratamento visual de dados com KNIME, o processamento analítico com Python e a apresentação dos resultados no Power BI.

A solução busca oferecer uma visão objetiva e organizada dos atendimentos, facilitando análises administrativas.

### 1.4 Escopo do Projeto

**Dentro do escopo (In Scope):**

- Importação de registros fictícios de atendimentos em formato CSV.
- Limpeza, padronização e transformação dos dados.
- Identificação de registros duplicados e inconsistências.
- Processamento e validação dos dados utilizando Python.
- Cálculo de indicadores operacionais.
- Criação de dashboard interativo no Power BI.
- Aplicação de filtros por período, especialidade e status.
- Documentação e versionamento do projeto no GitHub.

**Fora do escopo (Out of Scope):**

- Cadastro e gerenciamento de pacientes reais.
- Armazenamento de informações médicas sensíveis.
- Prontuários eletrônicos.
- Agendamento ou cancelamento real de consultas.
- Integração com hospitais ou sistemas externos.
- Autenticação e gerenciamento de usuários.
- Previsões clínicas utilizando Inteligência Artificial.
- Implantação de uma plataforma web própria.

---

## 2. Histórias de Usuário (User Stories)

**US01 — Visualização de Atendimentos**

Como gestor de uma clínica, quero visualizar a quantidade de atendimentos realizados por período, para que eu possa acompanhar a demanda da unidade.

**US02 — Análise por Especialidade**

Como gestor administrativo, quero filtrar os atendimentos por especialidade, para que eu possa identificar quais serviços apresentam maior demanda.

**US03 — Monitoramento de Cancelamentos**

Como responsável administrativo, quero visualizar a quantidade e a taxa de cancelamentos, para que eu possa acompanhar esse indicador e identificar possíveis problemas operacionais.

**US04 — Qualidade dos Dados**

Como analista de dados, quero identificar e tratar registros inconsistentes, para que os indicadores apresentados sejam confiáveis.

**US05 — Visualização Interativa**

Como gestor, quero interagir com gráficos e filtros em um dashboard, para que eu possa explorar os indicadores sem precisar manipular planilhas manualmente.

---

## 3. Requisitos do Sistema

### 3.1 Requisitos Funcionais (RF)

| ID | Descrição |
|---|---|
| RF01 | O sistema deve importar registros fictícios de atendimentos a partir de arquivos CSV. |
| RF02 | O processamento deve identificar e tratar registros duplicados, datas inválidas e campos obrigatórios ausentes. |
| RF03 | O sistema deve calcular a quantidade total de registros, os atendimentos realizados e os cancelamentos. |
| RF04 | O sistema deve calcular a taxa percentual de cancelamento. |
| RF05 | O dashboard deve apresentar gráficos de atendimentos por mês e por especialidade. |
| RF06 | O dashboard deve permitir filtros por período, especialidade e status. |
| RF07 | O processamento deve gerar arquivos CSV tratados para importação no Power BI. |
| RF08 | O dashboard deve atualizar os indicadores de acordo com os filtros selecionados. |

### 3.2 Requisitos Não Funcionais (RNF)

| ID | Descrição |
|---|---|
| RNF01 | O projeto deve utilizar exclusivamente dados fictícios, sem informações pessoais de pacientes reais. |
| RNF02 | Os scripts Python devem possuir organização modular e dependências documentadas. |
| RNF03 | O dashboard deve apresentar uma interface intuitiva, com indicadores, títulos e legendas legíveis. |
| RNF04 | O processamento deve ser executável localmente com as ferramentas e dependências documentadas. |
| RNF05 | Os arquivos e a documentação devem ser versionados em um repositório GitHub. |
| RNF06 | As regras de tratamento dos dados devem ser documentadas para permitir a reprodução dos resultados. |

### 3.3 Indicadores Planejados (KPIs)

O dashboard deverá apresentar:

- **Total de registros:** quantidade total de atendimentos registrados na base, incluindo os cancelados.
- **Atendimentos realizados:** quantidade de registros com status "Realizado".
- **Atendimentos cancelados:** quantidade de registros com status "Cancelado".
- **Taxa de cancelamento:** percentual de registros cancelados em relação ao total de registros.
- **Atendimentos por especialidade:** distribuição dos atendimentos realizados entre as especialidades.
- **Evolução mensal:** quantidade de atendimentos realizados ao longo dos meses.

A taxa de cancelamento será calculada pela fórmula:

**Taxa de cancelamento (%) = (Atendimentos cancelados / Total de registros) × 100**

Quando não houver registros no conjunto selecionado, a taxa deverá ser apresentada como indisponível, evitando divisão por zero.

---

## 4. Caso de Uso Principal e Tratamento de Erros

### 4.1 Caso de Uso Principal

**UC01 — Consultar Indicadores de Atendimentos Clínicos**

**Ator principal:** Gestor administrativo.

**Pré-condição:** Os dados fictícios devem ter sido importados, tratados e disponibilizados no dashboard.

### 4.2 Fluxo Principal

1. O analista disponibiliza o arquivo CSV com registros fictícios de atendimentos.
2. O KNIME importa o arquivo e executa as etapas de limpeza, padronização e transformação.
3. O Python valida os dados tratados e calcula os indicadores planejados.
4. Os resultados são exportados para arquivos CSV.
5. O Power BI importa os arquivos processados e apresenta os indicadores no dashboard.
6. O gestor acessa o relatório e seleciona um período ou especialidade.
7. O Power BI aplica os filtros e atualiza automaticamente os gráficos e indicadores.
8. O gestor visualiza os resultados e identifica padrões de atendimento.

**Pós-condição:** Os indicadores correspondentes aos filtros selecionados são apresentados corretamente.

### 4.3 Fluxos de Exceção

**EX01 — Arquivo não encontrado**

Caso o arquivo de entrada não esteja disponível, o processamento deverá informar sua ausência e interromper a execução.

**EX02 — Dados inválidos**

Caso sejam identificadas datas inválidas ou registros inconsistentes, o processo deverá registrar as ocorrências e aplicar as regras de tratamento definidas.

**EX03 — Campos obrigatórios ausentes**

Caso o arquivo não apresente colunas obrigatórias, o processamento deverá ser interrompido com uma mensagem que identifique os campos ausentes.

**EX04 — Ausência de resultados**

Caso os filtros selecionados não retornem registros, o dashboard deverá informar que não existem dados disponíveis para a seleção.

**EX05 — Duplicidade de registros**

Caso sejam identificados registros com identificadores repetidos, o KNIME deverá aplicar a regra de remoção de duplicatas, mantendo um único registro por identificador e registrando a quantidade removida.

---

## 5. Arquitetura e Escolha da Stack Tecnológica

### 5.1 Arquitetura Proposta

O projeto utilizará uma arquitetura de processamento local, organizada em etapas sequenciais.

**Fluxo de dados:**

1. **CSV:** fonte inicial de dados fictícios.
2. **KNIME:** extração, limpeza, padronização e transformação dos dados.
3. **Python + Pandas:** validação, análise e geração de indicadores.
4. **CSV Processado:** armazenamento dos resultados.
5. **Power BI:** visualização e exploração interativa dos indicadores.
6. **GitHub:** versionamento, organização e documentação do projeto.

### 5.2 Tecnologias Utilizadas

| Camada | Tecnologia | Responsabilidade |
|---|---|---|
| Interface / Frontend | Power BI | Construção de dashboards e visualizações interativas |
| Lógica / Processamento | Python | Validação e processamento analítico |
| Biblioteca de dados | Pandas | Manipulação e análise de tabelas |
| ETL | KNIME Analytics Platform | Limpeza, transformação e organização dos registros |
| Armazenamento | CSV | Persistência local dos dados fictícios e processados |
| Versionamento | Git e GitHub | Controle de versões e documentação |

### 5.3 Justificativa Tecnológica

A combinação dessas ferramentas permite construir um fluxo completo de análise de dados sem exigir uma infraestrutura complexa de servidores.

O KNIME oferece recursos visuais de transformação, o Python proporciona flexibilidade para validações e cálculos analíticos, enquanto o Power BI disponibiliza uma interface interativa para exploração dos resultados.

A utilização de arquivos CSV simplifica o armazenamento e favorece a reprodução do projeto em ambiente acadêmico.

### 5.4 Estrutura Planejada do Repositório

**clinidata/**

- `data/` — arquivos CSV originais e processados.
- `python/` — scripts Python para validação e análise.
- `knime/` — workflow de tratamento dos dados.
- `powerbi/` — arquivo do dashboard em formato PBIX.
- `images/` — capturas de tela dos resultados.
- `README.md` — documentação principal do projeto.
- `requirements.txt` — dependências Python.
- `.gitignore` — configuração de arquivos ignorados no versionamento.
- `LICENSE` — licença MIT.

---

## 6. Critérios de Aceite e Definition of Done

### 6.1 Critérios de Aceite

| ID | Critério de Aceite |
|---|---|
| CA01 | O processamento deve importar corretamente um arquivo CSV com as colunas obrigatórias. |
| CA02 | O workflow deve identificar e remover registros duplicados conforme a regra definida. |
| CA03 | O Python deve calcular corretamente os totais e a taxa de cancelamento com base nos dados processados. |
| CA04 | O Power BI deve apresentar gráficos de atendimentos mensais e por especialidade. |
| CA05 | Os filtros devem atualizar corretamente os indicadores exibidos no dashboard. |
| CA06 | O sistema deve tratar arquivos ausentes e estruturas inválidas sem falhas silenciosas. |
| CA07 | O dashboard deve apresentar uma indicação adequada quando não existirem registros para os filtros aplicados. |
| CA08 | O repositório deve disponibilizar arquivos e instruções suficientes para reproduzir o fluxo de análise. |

### 6.2 Definition of Done (DoD)

O projeto será considerado concluído quando:

- [ ] A base fictícia de atendimentos estiver estruturada.
- [ ] O workflow do KNIME estiver implementado e validado.
- [ ] Os scripts Python estiverem funcionando corretamente.
- [ ] As regras de tratamento e os indicadores estiverem documentados.
- [ ] Os arquivos processados puderem ser importados no Power BI.
- [ ] O dashboard apresentar os indicadores e gráficos planejados.
- [ ] Os filtros estiverem funcionando corretamente.
- [ ] Os fluxos de exceção tiverem sido testados.
- [ ] O código, o workflow e o dashboard estiverem organizados no GitHub.
- [ ] O README apresentar instruções de instalação, execução e reprodução dos resultados.

---

## Resultado Esperado

Ao final do desenvolvimento, espera-se obter um protótipo funcional de Business Intelligence aplicado à gestão de atendimentos clínicos.

O CliniData deverá demonstrar a integração entre ferramentas de ETL, programação e visualização de dados, oferecendo indicadores organizados para apoiar análises administrativas.

Além de atender aos objetivos acadêmicos, o projeto poderá contribuir para o desenvolvimento de competências práticas em Python, análise de dados, qualidade de dados, Power BI e documentação de software.

---

## Licença

Este projeto está disponibilizado sob a **MIT License**. Consulte o arquivo `LICENSE` para mais informações.

**CliniData — Transformando dados em informações para melhores decisões.**
