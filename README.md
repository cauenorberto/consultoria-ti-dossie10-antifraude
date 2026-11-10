[consultoria_de_ti_dossi_10.md](https://github.com/user-attachments/files/34553448/consultoria_de_ti_dossi_10.md)
# Escudo 60+: Solução Antifraude Comportamental para Proteção de Idosos

**Entrega 2 - Consultoria de TI**

**Turma:** 2N2026.2 | **Professor:** Cid Andrade

**Dossiê Escolhido:** 10 - Antifraude e golpes contra idosos

## 1. Abertura

* **Título do Projeto:** Escudo 60+: 

* **Dossiê Escolhido:** 10 - Antifraude e golpes contra idosos

* **Recorte Escolhido:** Foco estrito na prevenção de fraudes por engenharia social (falsas centrais de atendimento e transferências atípicas via Pix) direcionadas a idosos na faixa etária acima de 65 anos utilizando aplicativos bancários.

* **Integrantes:**

  * Cauê Norberto| GitHub: \[cauenorberto\] | Área: Ciência de Dados | RGM: \[48009661\]

  * Luan Henrique | GitHub: \[luanhenrique-dev] | Área: Cibersegurança | RGM: \[47914564\]

  * Thiago Nielsen | GitHub: \[ThiagoNielsen2008\] | Área: Engenharia de Dados | RGM: \[47917041\]

  * Giovana Moura | GitHub: \[giomoura09032008\] | Área: Engenharia de Dados | RGM: \[47932112\]

## 2. Análise do Problema

* **Quem é afetado, onde e quanto:** Segundo dados recentes da Unifesp e levantamentos de órgãos de proteção ao consumidor, as fraudes digitais contra pessoas idosas dispararam no Brasil, com vítimas com idade média superior a 67 anos. A Febraban indicam que as tentativas de golpes atingem fortemente a população sênior, comprometendo aposentadorias e reservas de uma vida inteira.
O público-alvo primário compreende aposentados, pensionistas e idosos com 65 anos ou mais, parcela da população que concentra grande parte das economias de uma vida e que, historicamente, possui menor familiaridade com os riscos inerentes ao ecossistema de pagamentos instantâneos. O problema é nacional, mas com forte incidência nos grandes centros urbanos, onde o volume de transações digitais é massivo.
Levantamentos recentes do setor bancário indicam que as tentativas de golpes digitais atingem fortemente a população sênior, com destaque para índices que colocam os idosos entre os grupos mais vulneráveis às fraudes por engenharia social ([Radar Febraban](https://febrabantech.febraban.org.br/conteudoPublicado/79dbebb1-db67-467d-b21b-42afb44807cf)).

* **Causas (com destaque tecnológico):** O principal vetor não é a quebra de criptografia dos bancos, mas sim a **engenharia social** (que responde por cerca de 40% das fraudes financeiras no país). Os criminosos manipulam psicologicamente o idoso — utilizando falsas centrais de atendimento, urgência inventada ou engenharia social por telefone/WhatsApp —, induzindo-o a realizar transações voluntárias ou a entregar senhas e códigos de segurança.
Enquanto o fator socioeconômico envolve a vulnerabilidade emocional e a menor literacia digital, as causas que competem diretamente à tecnologia residem em dois pilares:
1. **Falta de barreiras comportamentais contextuais:** Os aplicativos bancários tradicionais validam a transação com base apenas em senhas ou biometria estática do próprio usuário, sem avaliar se o titular está sob coação ou sendo manipulado naquele exato instante.
2. **Complexidade excessiva e opacidade das interfaces:** Menus cheios de atalhos e alertas genéricos em texto miúdo acabam por confundir o idoso, que frequentemente clica em links maliciosos ou aceita o espelhamento da tela do smartphone acreditando falar com o gerente do banco.

* **O que já existe e por que não basta:** Atualmente, os bancos utilizam alertas genéricos por SMS ou notificações push padrão. No entanto, o público idoso muitas vezes não compreende o aviso, ignora o texto técnico ou é coagido pelo golpista a ignorar o alerta, tornando ineficientes as barreiras puramente textuais e passivas.

## 3. Proposta tecnológica

* **Jornada do usuário:** O *Escudo 60+* atua como um modo assistido no aplicativo do banco. Ao detectar uma transação atípica para uma chave Pix desconhecida ou sob coação simulada, o sistema ativa uma interface simplificada de alto contraste e aciona automaticamente uma **"Rede de Apoio de Confiança"** (um familiar ou cuidador pré-cadastrado) para validar a operação em conjunto com o idoso, sem jargões complexos.

### Visão Geral da Arquitetura e Jornada do Usuário (Modo Assistido 60+) 
Quando o sistema identifica uma operação atípica (ex: Pix de alto valor para uma chave recém-adicionada em horário incomum), o aplicativo aciona o **Modo Assistido 60+**. A interface se transforma: o fundo escurece levemente, as fontes aumentam de forma destacada, um áudio explicativo integrado narra os detalhes da transação e uma pausa de segurança de 30 minutos é ativada. Simultaneamente, uma notificação push enriquecida é disparada para um familiar ou cuidador pré-cadastrado ("Guardião"), permitindo uma validação cruzada antes da liberação dos fundos.

* **Arquitetura da Solução:**

  * *Camada de Ingestão (Engenharia de Dados):* Pipelines em tempo real que capturam metadados de transações e padrões de navegação no app.

  * *Camada de Inteligência (Ciência de Dados):* Modelos de *behavioral analytics* que avaliam o desvio de comportamento do idoso (horário incomum, valor atípico, velocidade de digitação alterada por nervosismo).

  * *Camada de Proteção (Cibersegurança):* Bloqueio preventivo de espelhamento de tela (*screen mirroring*) e detecção de aplicativos maliciosos de acesso remoto instalados no dispositivo móvel.


### Detalhamento Técnico dividido por Área, destacando os pontos de cada um.

| Área de Atuação | Responsável | Componentes Tecnológicos / Stack | Papel Crítico no Projeto |
| :--- | :--- | :--- | :--- |
| **Engenharia de Dados** | Thiago Nielsen | Apache Kafka, Apache Spark Streaming, Data Lake AWS (S3 / Delta Lake) | Ingestão em tempo real de metadados transacionais e construção de streams de eventos de navegação para processamento sem latência perceptível. |
| **Ciência de Dados** | Cauê Norberto | Python, Scikit-Learn, LightGBM, Modelos de *Behavioral Analytics* | Desenvolvimento do motor preditivo para identificar desvios sutis no padrão de digitação, velocidade de navegação e comportamento atípico. |
| **Cibersegurança** | Luan Henrique | OWASP Mobile Top 10, SDKs de Detecção de *Screen Mirroring*, AES-256 | Blindagem do dispositivo contra ferramentas de acesso remoto não autorizado, detecção de espelhamento de tela malicioso e criptografia ponta a ponta. |
| **Gestão e Cloud** | Giovana Moura | AWS Elastic Container Service (ECS), Terraform, Ferramentas de FinOps | Orquestração da infraestrutura elástica em nuvem, dimensionamento de custos operacionais e governança de conformidade com TI verde. |
* **Papel das áreas:** Engenharia e Ciência de Dados estruturam o fluxo preditivo; Cibersegurança blinda o dispositivo contra malwares; Gestão e Cloud garantem a escalabilidade segura da infraestrutura em nuvem e a conformidade regulatória.

* **O que a tecnologia não resolve:** A tecnologia mitiga a execução do golpe digital, mas não substitui totalmente a educação financeira e o suporte familiar contínuo contra pressões psicológicas presenciais ou telefônicas externas.

## 4. Análise Ética
### 4.1 Matriz de Riscos

| Risco Mapeado | Categoria | Impacto | Probabilidade | Medida de Mitigação e Controle |
| :--- | :--- | :--- | :--- | :--- |
| **1. Falsos Positivos** | Operacional | Alto | Média | Criação de um canal de contestação humanizado e rápido via ligação prioritária direto na tela de bloqueio. |
| **2. Vazamento de Dados** | Privacidade | Alto | Baixa | Anonimização de dados em trânsito e armazenamento com criptografia AES-256 rigorosa. |
| **3. Exclusão Digital** | Acessibilidade | Médio | Média | Possibilidade de validação alternativa por biometria reforçada ou suporte assistido em agência física. |
| **4. Fadiga de Alertas** | Experiência | Baixo | Média | Calibragem inteligente de limiares de risco para disparar avisos apenas em desvios comportamentais críticos. |
| **5. Uso Indevido de Privilégios** | Governança | Alto | Baixa | Trilha de auditoria imutável (*Access Logs*) para qualquer consulta a dados cadastrais de clientes. |

* **Decisão de implantação:** Implantar com controles restritos. A solução é viável e socialmente urgente, desde que sejam aplicadas travas rígidas de privacidade e validação humana para evitar constrangimentos ao usuário idoso.

* **Controles antes de entrar em produção:**

  1. *Transparência:* Avisos claros em linguagem acessível sobre quais dados de comportamento são analisados.

  2. *Revisão humana:* Sempre que houver bloqueio severo, um atendente especializado (humano) entra em contato por voz com o idoso.

  3. *Minimização de dados:* Coleta estritamente necessária para a detecção da fraude, descartando logs desnecessários.

  4. *Segurança:* Proteção contra interceptação de rede e mascaramento de dados sensíveis na interface.

  5. *Teste de viés:* Auditorias periódicas para garantir que o algoritmo não discrimine idosos com menor frequência de uso digital.

  6. *Canal de contestação:* Botão de fácil acesso na tela inicial para reverter ou contestar qualquer bloqueio automático em até 1 clique.

* **LGPD:** Tratamento de dados cadastrais e comportamentais estritamente para a finalidade de prevenção à fraude (Base legal: Proteção ao Crédito e Prevenção a Fraudes - Art. 7º, X e Art. 11 da LGPD). Retenção limitada ao tempo necessário de segurança, com ênfase na proteção de dados de pessoas vulneráveis.

* **Comunicado público (534 caracteres):**
  "O projeto Escudo 60+ desenvolve uma tecnologia de proteção antifraude voltada especificamente para a segurança financeira de pessoas idosas no ambiente digital. Integrando análise comportamental em tempo real e uma rede de apoio familiar validada, nossa solução atua de forma preventiva contra golpes de engenharia social, preservando a autonomia, a privacidade e a tranquilidade de quem construiu uma vida inteira de trabalho. Tecnologia humanizada a serviço da inclusão e da justiça social."

## 5. Acessibilidade e inclusão digital

* **Barreiras e Inclusão:** Idosos com baixa literacia digital ou limitações visuais/motoras frequentemente abandonam aplicativos bancários complexos. O *Escudo 60+* adota uma interface simplificada, botões de toque estendidos, suporte a comandos de voz guiados e alto contraste.

* **Requisitos técnicos:** Atendimento integral às diretrizes da WCAG (Web Content Accessibility Guidelines) no nível AA, garantindo legibilidade de fontes, navegação linear intuitiva e ausência de elementos visuais poluídos que gerem confusão cognitiva.

## 6. Sustentabilidade

* **TI Verde:** Otimização dos algoritmos de Machine Learning para rodar em instâncias de nuvem energeticamente eficientes, reduzindo o consumo desnecessário de processamento (*compute*) e pegada de carbono computacional.
Melhora e deixando de forma mais leve o consumo energético dos servidores através do uso de instâncias elásticas que entram em modo de baixo consumo (idle scaling) durante os horários de menor movimento noturno.
Arquitetura de microsserviços leves que evitam o desperdício de ciclos de CPU em modelos preditivos pesados, priorizando inferências locais eficientes quando suportadas pelo dispositivo do usuário.

* **Modelo financeiro:** Manutenção sustentada por meio de parcerias com as próprias instituições financeiras (que reduzem drasticamente seus prejuízos com estornos de fraudes) e fundos de responsabilidade social corporativa após o primeiro ano de implantação.
Ano 1: Financiamento absorvido pelo próprio orçamento de inovação e prevenção a fraudes das instituições financeiras parceiras, visto que a redução de prejuízos com estornos de golpes supera o custo de manutenção da plataforma.
Anos seguintes (Sustentabilidade a longo prazo): Transição para um modelo cooperativo sustentado por consórcios do setor bancário e fundos de impacto social voltados para a longevidade e cidadania financeira.

## 7. Impacto esperado

* **Indicadores e Metas:** Redução de pelo menos 30% nas perdas financeiras por engenharia social entre os usuários idosos cadastrados no piloto em um período de 6 meses.

* **Validação:** Realização de testes de usabilidade presenciais com grupos focais de idosos e cuidadores antes da escala total da aplicação.

* **Plano de contingência:** Caso a adesão inicial seja baixa devido à resistência tecnológica, o sistema prevê campanhas educativas guiadas por assistentes virtuais em áudio e parceria com centros de convivência da terceira idade.

## 8. Quadro de decisões

| Decisão | Alternativas Consideradas | Justificativa da Escolha | 
| ----- | ----- | ----- | 
| 1\. Arquitetura de Nuvem | Servidores locais vs. Nuvem pública elástica | Escolhida a nuvem pública para garantir escalabilidade imediata no processamento de picos de alertas de segurança. | 
| 2\. Modelo Antifraude | Regras estáticas tradicionais vs. Machine Learning comportamental | Escolhido ML comportamental para identificar desvios sutiles de padrão que regras fixas não detectam. | 
| 3\. Mecanismo de Alerta | Apenas SMS/Push vs. Acionamento de Rede de Apoio | Escolhida a Rede de Apoio familiar, pois o idoso sob coação psicológica costuma ignorar alertas tradicionais. | 
| 4\. Interface do Usuário | App separado vs. Módulo integrado ao banco existente | Escolhido módulo integrado para evitar a necessidade de download de novos aplicativos desconhecidos. | 
| 5\. Armazenamento de Logs | Banco relacional simples vs. Data Lake seguro e criptografado | Escolhido Data Lake com criptografia robusta para suportar auditorias de conformidade com a LGPD. | 

## 9. Capítulos individuais

### Caue (Ciência de Dados)

* **Papel no projeto:** Desenvolvimento e validação dos modelos preditivos de análise comportamental (evidenciado pelos commits de criação do script de machine learning no repositório).

* **Plano de desenvolvimento (SMART):** Aprofundar competências em *Responsible AI* e fairness em modelos estatísticos nos próximos 12 meses, buscando certificação específica na área de dados até o final do próximo semestre.

* **Feedback dos colegas:** O grupo destaca a excelente articulação na escolha das métricas de desvio comportamental, pontuando a necessidade de maior atenção inicial na documentação dos parâmetros do modelo.

### Luan henrique (Cibersegurança)

* **Papel no projeto:** Mapeamento de vetores de ataque de engenharia social, desenho da matriz de riscos e mitigação de malwares de acesso remoto (comprovado pelos commits de segurança e LGPD).

* **Plano de desenvolvimento (SMART):** Obter especialização prática em testes de intrusão móvel e segurança de APIs bancárias em um horizonte de 6 a 9 meses.

* **Feedback dos colegas:** Reconhecimento pela rigidez técnica na construção dos 6 eixos de controle ético, com sugestão de otimizar o tempo de resposta nas entregas parciais.

### Giovana Moura e Thiago Nielsen (Engenharia de Dados)

* **Papel no projeto:** Estruturação dos pipelines de ingestão de dados em tempo real e arquitetura de armazenamento seguro (validado pelos commits de infraestrutura de dados).

* **Plano de desenvolvimento (SMART):** Dominar ferramentas avançadas de streaming de dados (como Apache Kafka) e governança em nuvem nos próximos 12 meses.

* **Feedback dos colegas:** exemplar na organização geral do repositório e limpeza do código, com apontamento para diversificar a participação nas discussões conceituais com as outras áreas.

* **Feedback Conjunto do Grupo:** A dinâmica colaborativa fluiu de forma equilibrada, unindo expertises técnicas complementares em prol de um problema social crítico, com divisão justa e transparente de tarefas atestada pelo histórico do GitHub.

## 10. Referências e Fontes de Pesquisa
* [BANCO CENTRAL DO BRASIL. Relatório de Cidadania Financeira.](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/RIF/relatorio_de_cidadania_financeira_2025.pdf) Brasília, 2025.
* [FEBRABAN TECH. Radar Febraban: Panorama de tentativas de golpes e engenharia social no Brasil.](https://febrabantech.febraban.org.br/conteudoPublicado/79dbebb1-db67-467d-b21b-42afb44807cf) São Paulo, 2025.
* [FEBRABAN NEWS. Os 10 golpes mais comuns aplicados contra idosos e diretrizes de prevenção.](https://portal.febraban.org.br/DetalheNews/16/pt-br) São Paulo, 2024.
* LEI GERAL DE PROTEÇÃO DE DADOS PESSOAIS (LGPD). Lei nº 13.709/2018. Diretrizes aplicadas à segurança e proteção de dados de públicos vulneráveis.
* AGÊNCIA BRASIL. *Engenharia social responde por parcela significativa das fraudes financeiras no Brasil*. Brasília: EBC, 2026.
