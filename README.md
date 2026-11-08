[consultoria_de_ti_dossi_10.md](https://github.com/user-attachments/files/34553448/consultoria_de_ti_dossi_10.md)
# Escudo 60+: Solução Antifraude Comportamental para Proteção de Idosos

**Entrega 2 - Consultoria de TI**

**Turma:** 2N2026.2 | **Professor:** Cid Andrade

**Dossiê Escolhido:** 10 - Antifraude e golpes contra idosos

## 1. Abertura

* **Título do Projeto:** Escudo 60+: Camada de Proteção Comportamental e Assistida contra Engenharia Social

* **Dossiê Escolhido:** 10 - Antifraude e golpes contra idosos

* **Recorte Escolhido:** Foco estrito na prevenção de fraudes por engenharia social (falsas centrais de atendimento e transferências atípicas via Pix) direcionadas a idosos na faixa etária acima de 65 anos utilizando aplicativos bancários móveis.

* **Integrantes:**

  * Cauê Norberto| GitHub: \[cauenorberto\] | Área: Ciência de Dados | RGM: \[48009661\]

  * Luan Henrique | GitHub: \[\] | Área: Cibersegurança | RGM: \[47914564\]

  * Thiago Nielsen | GitHub: \[ThiagoNielsen2008\] | Área: Engenharia de Dados | RGM: \[47917041\]

  * Giovana Moura | GitHub: \[giomoura09032008\] | Área: Engenharia de Dados | RGM: \[47932112\]

## 2. Análise do Problema

* **Quem é afetado, onde e quanto:** Segundo dados recentes da Unifesp e levantamentos de órgãos de proteção ao consumidor, as fraudes digitais contra pessoas idosas dispararam expressivamente no Brasil, com vítimas com idade média superior a 67 anos. Estatísticas da Febraban indicam que as tentativas de golpes atingem fortemente a população sênior, comprometendo aposentadorias e reservas de uma vida inteira.

* **Causas (com destaque tecnológico):** O principal vetor não é a quebra de criptografia dos bancos, mas sim a **engenharia social** (que responde por cerca de 40% das fraudes financeiras no país). Os criminosos manipulam psicologicamente o idoso — utilizando falsas centrais de atendimento, urgência inventada ou engenharia social por telefone/WhatsApp —, induzindo-o a realizar transações voluntárias ou a entregar senhas e códigos de segurança.

* **O que já existe e por que não basta:** Atualmente, os bancos utilizam alertas genéricos por SMS ou notificações push padrão. No entanto, o público idoso muitas vezes não compreende o aviso, ignora o texto técnico ou é coagido pelo golpista a ignorar o alerta, tornando ineficientes as barreiras puramente textuais e passivas.

## 3. Proposta tecnológica

* **Jornada do usuário:** O *Escudo 60+* atua como um modo assistido no aplicativo do banco. Ao detectar uma transação atípica para uma chave Pix desconhecida ou sob coação simulada, o sistema ativa uma interface simplificada de alto contraste e aciona automaticamente uma **"Rede de Apoio de Confiança"** (um familiar ou cuidador pré-cadastrado) para validar a operação em conjunto com o idoso, sem jargões complexos.

* **Arquitetura da Solução:**

  * *Camada de Ingestão (Engenharia de Dados):* Pipelines em tempo real que capturam metadados de transações e padrões de navegação no app.

  * *Camada de Inteligência (Ciência de Dados):* Modelos de *behavioral analytics* que avaliam o desvio de comportamento do idoso (horário incomum, valor atípico, velocidade de digitação alterada por nervosismo).

  * *Camada de Proteção (Cibersegurança):* Bloqueio preventivo de espelhamento de tela (*screen mirroring*) e detecção de aplicativos maliciosos de acesso remoto instalados no dispositivo móvel.

* **Papel das áreas:** Engenharia e Ciência de Dados estruturam o fluxo preditivo; Cibersegurança blinda o dispositivo contra malwares; Gestão e Cloud garantem a escalabilidade segura da infraestrutura em nuvem e a conformidade regulatória.

* **O que a tecnologia não resolve:** A tecnologia mitiga a execução do golpe digital, mas não substitui totalmente a educação financeira e o suporte familiar contínuo contra pressões psicológicas presenciais ou telefônicas externas.

## 4. Análise ética

* **Matriz de riscos:**

  1. *Falsos Positivos:* Bloqueio indevido de transações legítimas do idoso. *(Impacto: Alto | Controle: Canal humanizado imediato).*

  2. *Exclusão de Autonomia:* O idoso sentir-se infantilizado pelo monitoramento. *(Impacto: Médio | Controle: Transparência clara e consentimento do familiar de confiança).*

  3. *Vazamento de Dados Comportamentais Sensíveis:* Exposição de rotinas financeiras. *(Impacto: Alto | Controle: Criptografia ponta a ponta e anonimização).*

  4. *Indisponibilidade do Sistema de Apoio:* Falha ao contatar o familiar no momento do alerta. *(Impacto: Médio | Controle: Fluxo de contingência com retenção temporária da transferência).*

  5. *Uso Indevido por Terceiros de Má Fé:* Um familiar mal-intencionado controlar as finanças do idoso. *(Impacto: Alto | Controle: Termo de consentimento revogável e auditoria de acessos).*

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

* **Modelo financeiro:** Manutenção sustentada por meio de parcerias com as próprias instituições financeiras (que reduzem drasticamente seus prejuízos com estornos de fraudes) e fundos de responsabilidade social corporativa após o primeiro ano de implantação.

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

* **Feedback dos colegas:** Doutrina exemplar na organização geral do repositório e limpeza do código, com apontamento para diversificar a participação nas discussões conceituais com as outras áreas.

* **Feedback Conjunto do Grupo:** A dinâmica colaborativa fluiu de forma equilibrada, unindo expertises técnicas complementares em prol de um problema social crítico, com divisão justa e transparente de tarefas atestada pelo histórico do GitHub.

## 10. Referências

* FEBRABAN. *Pesquisa Radar Febraban: Panorama de fraudes e percepção de segurança digital*. São Paulo, 2025. Disponível em fontes institucionais do setor bancário.

* UNIFESP. *Fraudes digitais contra pessoas idosas crescem em levantamento recente de registros policiais*. São Paulo: Assessoria de Imprensa DCI Unifesp, 2026.

* AGÊNCIA BRASIL. *Engenharia social responde por parcela significativa das fraudes financeiras no Brasil*. Brasília: EBC, 2026.
