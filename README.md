# Processo Seletivo LAPES 2026

O LAPES — Laboratório de Pesquisa em Engenharia de Software — está com as seleções abertas para 2026. O processo é composto por um desafio técnico e uma entrevista com o responsável pela área de interesse.

Há duas trilhas disponíveis. Você pode seguir pela que mais se alinha ao seu perfil ou encarar ambas, inclusive mesclando os desafios em um único projeto, se fizer sentido.

---

## Como entregar

1. Faça um fork deste repositório.
2. O repositório deve permanecer público do início ao fim do processo seletivo.
3. No README do seu fork, inclua:
   - nome(s) do(s) candidato(s) e trilha(s) escolhida(s);
   - contato: e-mail institucional e/ou telefone com WhatsApp;
   - instruções de setup e decisões técnicas, conforme o PDF de cada desafio.

O PDF de cada trilha está na pasta correspondente:

```
processo-seletivo-2026/
├── dados/    ← Trilha de Dados / IA
└── dev/      ← Trilha de Desenvolvimento
```

**Em dupla:** apenas um dos candidatos faz o fork; o segundo contribui no mesmo repositório. Ambos os nomes devem constar no README final.

---

## Trilha de Dados — Sistema Agêntico de IA

Construa um sistema multiagente capaz de responder perguntas sobre um corpus de documentos a sua escolha, combinando recuperação vetorial (RAG) com busca na web como fallback.

**Prazo:** 17 de julho de 2026, até 23:59 (BRT).
**Formato:** individual ou dupla.
**Desafio completo:** [`dados/desafio.pdf`](dados/desafio.pdf)

Dúvidas: Giovanni Braga — [e-mail institucional](mailto:giovanni23070008@aluno.cesupa.br)

---

## Trilha de Desenvolvimento — Mini E-commerce

Desenvolver uma plataforma de e-commerce simplificada. Um desafio fullstack(frontend, backend e devops), abordando conceitos como cache, rate limiting, testes automatizadoes e entre outros.

**Prazo:** 17 de julho de 2026, até 23:59 (BRT).
**Formato:** individual ou dupla.
**Desafio completo:** [`dev/desafio.pdf`](dev/desafio.pdf)

Dúvidas: Gabriel Mattos — [e-mail institucional](mailto:gabriel22070059@aluno.cesupa.br)

---

## Apresentações

As apresentações serão realizadas nas primeiras semanas de agosto. Data e horário serão definidos com cada candidato pelo responsável da respectiva trilha. Detalhes sobre formato e duração serão divulgados em breve.

---

## Avaliação

Em ambas as trilhas, a nota final é composta por **50% do desafio técnico** e **50% da entrevista** com o responsável pela área. Todos os candidatos que entregarem o desafio são convidados para a entrevista automaticamente. Mais detalhes sobre o formato da entrevista serão divulgados em breve.

Candidatos não selecionados após a entrevista recebem feedback ao final do processo.

---

## Sobre o uso de IA

O uso de ferramentas de IA generativa é permitido — faz parte do dia a dia do desenvolvimento moderno. O desafio avalia o seu conhecimento, não o da máquina. Você deve ser capaz de explicar seu código, justificar cada decisão técnica e defender sua arquitetura na apresentação. Copiar sem compreender será evidente na review.

---

## FAQ

**Existe algum pré-requisito (curso, período, vínculo institucional)?**
Não.

**Posso me inscrever nas duas trilhas?**
Sim. Você pode entregar as duas trilhas separadamente ou mesclá-las em um único projeto, se houver fluidez entre os escopos.

**Deploy público é obrigatório?**
Não. Basta o repositório rodando localmente conforme o README. Deploy automatizado é diferencial (pontuação extra), conforme detalhado no PDF do desafio.

**Atraso resulta em penalização ou desclassificação?**
Penalização. O prazo encerra em 17/07/2026 às 23:59. Commits feitos depois do prazo são aceitos, mas implicam desconto na nota do desafio.

**Como faço para tirar dúvidas durante o desafio ou reportar inconsistências?**
Por contato direto com os responsáveis abaixo. Dúvidas específicas de uma trilha vão para o responsável da área; dúvidas gerais sobre o processo podem ser endereçadas a qualquer um.

- Caio Johnston — [e-mail institucional](mailto:caio21070002@aluno.cesupa.br)
- Gabriel Mattos — [e-mail institucional](mailto:gabriel22070059@aluno.cesupa.br)
- Giovanni Braga — [e-mail institucional](mailto:giovanni23070008@aluno.cesupa.br)
- Isaac Elgrably

Gabriel e Giovanni são da turma CC7NA e podem ser procurados pessoalmente no CESUPA, nos horários da turma (tarde e noite).

Contato organizacional: contato.lapes@gmail.com

---

A todos, desejamos um bom projeto, e boa sorte.

Atenciosamente,

Caio Johnston, Gabriel Mattos, Giovanni Braga, e Isaac Elgrably.

---

1. Por que este corpus e o que ele representa?
Profissionais e entusiastas de café especial frequentemente precisam consultar vocabulário sensorial padronizado, protocolos técnicos de *cupping/brewing* e contextos de origem geográfica. No entanto, essas informações costumam estar espalhadas entre documentos institucionais densos (SCA, WCR) e registros legais complexos (INPI/Embrapa). 

O desenvolvimento de um sistema **RAG (Retrieval-Augmented Generation)** resolve exatamente a dificuldade de localizar rapidamente esses dados sem a necessidade de vasculhar e ler manualmente dezenas de PDFs técnicos extensos. Este corpus representa a base de conhecimento consolidada e confiável desse ecossistema.

---

2. Por que RAG + Busca Web resolvem melhor do que cada um sozinho?
Os padrões da SCA/WCR e os registros do INPI são extremamente estáveis, normativos e consolidados; logo, o RAG é a arquitetura ideal e confiável para recuperá-los com precisão, evitando alucinações. 

Contudo, existem **lacunas genuínas e documentadas** neste corpus local — por exemplo, mesmo após buscas dedicadas, não foram encontradas fontes institucionais abertas e robustas detalhando o perfil sensorial de origens específicas como Etiópia ou Indonésia. A **busca web** entra no sistema para suprir exatamente essa lacuna real (e não fabricada artificialmente para o desafio), trazendo dinamismo ao pipeline.

---

3. Onde o sistema vai falhar? (Limitações do Pipeline)
É fundamental documentar os cenários onde o pipeline encontrará restrições:
* **Origens internacionais específicas:** Perguntas detalhadas sobre os perfis sensoriais da Etiópia ou Indonésia (devido à lacuna documental mapeada acima).
* **Harmonizações comerciais/específicas:** Combinações muito nichadas de alimentos e cafés que não estejam formalmente cobertas pela literatura científica disponível no corpus.
* **Dados voláteis de mercado:** Informações de preços, cotações atuais do café ou dados comerciais sazonais que não fazem parte de nenhum documento normativo indexado.

---

4. Por que este corpus exercita todas as partes obrigatórias do desafio?
O corpus foi desenhado estrategicamente para cobrir de forma sólida os pilares exigidos pelo edital:
* **Robustez no RAG:** Garantida pela presença de dados profundos sobre *cupping*, padrões técnicos, léxico sensorial, origens brasileiras e harmonização com embasamento científico real.
* **Fallback genuíno para a entrevista:** A limitação sobre as lacunas da Etiópia/Indonésia foi descoberta de forma orgânica durante a fase de curadoria e pesquisa. Isso cria um cenário de teste real, defensável e técnico para demonstrar aos avaliadores o comportamento do sistema quando precisa alternar dinamicamente entre o banco local e a API de busca web.