# Aula 02 — Engenharia de Prompt

## 1. Identificação
- **Data:** [21/08]
- **Integrante:** [Igor Baffi Felippelli Vieira]

---

## 2. Problema escolhido

### Modernização de funcionalidades de um sistema legado sem perder regras de negócio

O problema escolhido está relacionado ao processo de modernização de um sistema legado utilizado pela Defensoria Pública da União, denominado SISDPU, para sua nova versão, o SISDPU 2.0.

Durante a modernização de sistemas legados, funcionalidades existentes precisam ser analisadas antes de serem reproduzidas ou aprimoradas na nova aplicação. Esse processo exige atenção, pois uma funcionalidade aparentemente simples pode envolver regras de negócio, validações, comportamento da interface, comunicação entre front-end e back-end e persistência das informações no banco de dados.

Como exemplo, foi considerada uma demanda relacionada à tela de **Cadastro de Pessoa Física** do SISDPU 2.0.

Nessa tela existe o campo destinado ao CPF da pessoa cadastrada. Entretanto, podem existir situações em que a pessoa não possui CPF. Para representar corretamente essa condição, é necessário disponibilizar uma opção denominada **"Não tem CPF"**.

O problema é que a implementação não pode se limitar à inclusão visual de um checkbox. O sistema precisa compreender que a ausência do CPF é uma condição declarada pelo usuário, diferentemente de um campo que simplesmente não foi preenchido.

Dessa forma, é necessário analisar os impactos da funcionalidade na interface, nas validações, no back-end, no banco de dados e nos testes do sistema.

---

## 3. Objetivo

Utilizar Inteligência Artificial Generativa como ferramenta de apoio à análise de requisitos para auxiliar na definição da funcionalidade **"Não tem CPF"** no Cadastro de Pessoa Física do SISDPU 2.0.

A IA deverá auxiliar na identificação de:

- requisitos funcionais;
- regras de negócio;
- comportamento esperado da interface;
- impactos no front-end;
- impactos no back-end;
- necessidade de persistência no banco de dados;
- critérios de aceite;
- possíveis casos de teste;
- riscos e pontos que necessitam de validação humana.

A Inteligência Artificial será utilizada como ferramenta de apoio à análise e não como responsável pela decisão final sobre as regras de negócio do sistema.

---

## 4. Prompt inicial

```text
Analise a demanda de adicionar a opção "Não tem CPF" na tela de Cadastro de Pessoa Física do SISDPU 2.0 e diga como ela deve ser implementada.
```

---

## 5. Resultado inicial

A resposta gerada pela IA indicou que deveria ser criado um checkbox denominado **"Não tem CPF"** próximo ao campo CPF.

Segundo a resposta, quando o usuário marcasse a opção, o campo CPF deveria ser desabilitado e sua obrigatoriedade removida. Caso a opção fosse desmarcada, o campo deveria voltar a ficar disponível para preenchimento.

A IA também sugeriu que o valor do checkbox fosse enviado ao back-end e armazenado no banco de dados.

Como possíveis critérios de aceite, foram sugeridos:

- exibição do checkbox na tela;
- bloqueio do campo CPF ao marcar a opção;
- desbloqueio ao desmarcar;
- possibilidade de salvar uma pessoa sem CPF quando a opção estiver marcada;
- persistência da informação no banco de dados.

---

## 6. Análise crítica

### O que funcionou?

O prompt inicial conseguiu transmitir a ideia principal da demanda.

A IA identificou alguns comportamentos importantes, como:

- criação do checkbox;
- bloqueio do campo CPF;
- remoção da obrigatoriedade;
- comunicação com o back-end;
- persistência da informação.

Esses pontos ajudam a iniciar a análise da funcionalidade.

### O que não funcionou?

O prompt forneceu pouco contexto sobre o sistema.

A IA não sabia, por exemplo:

- como funciona a arquitetura do SISDPU 2.0;
- se existe uma funcionalidade equivalente no sistema legado;
- quais regras de negócio já existem;
- como a informação deve ser armazenada;
- se existe uma coluna no banco preparada para essa informação;
- quais padrões visuais devem ser seguidos;
- quais tecnologias estão envolvidas.

Por isso, a resposta ficou genérica.

### O que ficou faltando?

Faltaram principalmente:

- história de usuário;
- requisitos funcionais detalhados;
- regras de negócio;
- critérios de aceite mais completos;
- análise separada entre front-end, back-end e banco de dados;
- comportamento ao marcar e depois desmarcar a opção;
- tratamento de eventual CPF já digitado;
- edição posterior do cadastro;
- casos de teste;
- riscos;
- identificação das informações que precisam ser confirmadas pela equipe responsável pelo sistema.

### O que precisa ser validado?

Algumas informações não devem ser definidas apenas pela Inteligência Artificial.

Precisam ser confirmadas com a equipe responsável pelo SISDPU 2.0, como:

- estrutura real do banco de dados;
- existência de coluna destinada a indicar ausência de CPF;
- regras institucionais relacionadas ao cadastro de pessoas sem CPF;
- comportamento esperado no sistema legado;
- validações atualmente existentes no back-end;
- impactos em funcionalidades que utilizam CPF como critério de consulta ou identificação.

### A IA fez alguma suposição inadequada?

Sim.

A IA presumiu que já existiria uma forma simples de armazenar essa informação no banco de dados.

Entretanto, isso precisa ser verificado antes da implementação.

Ela também presumiu determinado comportamento da interface sem conhecer completamente as regras existentes no sistema.

Isso demonstra que uma resposta aparentemente coerente não deve ser utilizada sem análise e validação.

---

## 7. Prompt refinado

```text
PAPEL:

Atue como um analista de sistemas e engenheiro de software especializado em modernização de sistemas legados, levantamento de requisitos, UX/UI e aplicações web corporativas.

CONTEXTO:

A Defensoria Pública da União está realizando a modernização de um sistema legado denominado SISDPU para uma nova aplicação denominada SISDPU 2.0.

O SISDPU 2.0 possui uma arquitetura moderna, com front-end e back-end separados, e diversas funcionalidades do sistema legado precisam ser analisadas, reproduzidas ou aprimoradas sem provocar perda de regras de negócio.

Uma das funcionalidades em análise está localizada na tela de Cadastro de Pessoa Física.

Atualmente existe o campo CPF, porém há situações em que a pessoa cadastrada pode não possuir esse documento.

A nova interface deverá disponibilizar um checkbox denominado "Não tem CPF".

Quando essa opção for marcada, o sistema deverá compreender que a ausência do CPF é uma condição válida do cadastro, e não simplesmente que o usuário esqueceu de preencher o campo.

A implementação deve ser considerada de forma completa, envolvendo interface, validações, comunicação entre front-end e back-end e persistência da informação.

O sistema legado deverá ser utilizado como referência sempre que existir comportamento equivalente, mas a solução deve respeitar os padrões tecnológicos e visuais adotados no SISDPU 2.0.

OBJETIVO:

Definir uma solução funcional para a implementação da opção "Não tem CPF", garantindo que a funcionalidade seja corretamente tratada em todas as camadas do sistema e evitando inconsistências no cadastro de pessoas.

TAREFA:

Analise o problema nas seguintes etapas:

1. Identifique a necessidade do usuário que motivou a funcionalidade.

2. Defina os requisitos funcionais necessários.

3. Descreva as regras de negócio relacionadas ao campo CPF e ao checkbox "Não tem CPF".

4. Explique o comportamento esperado da interface quando:
   - o checkbox estiver desmarcado;
   - o checkbox for marcado;
   - o usuário marcar e posteriormente desmarcar a opção.

5. Identifique os possíveis impactos no:
   - front-end;
   - back-end;
   - banco de dados;
   - validações do formulário.

6. Verifique quais informações precisam ser persistidas para que o sistema consiga diferenciar:
   - uma pessoa que possui CPF;
   - uma pessoa que declarou não possuir CPF;
   - um cadastro em que o CPF simplesmente não foi informado.

7. Crie uma história de usuário correspondente à funcionalidade.

8. Elabore critérios de aceite objetivos e verificáveis.

9. Crie casos de teste contemplando:
   - cenário de sucesso;
   - campos obrigatórios;
   - marcação e desmarcação do checkbox;
   - tentativa de informar CPF enquanto "Não tem CPF" estiver selecionado;
   - edição posterior do cadastro;
   - persistência e recuperação da informação.

10. Identifique riscos, ambiguidades ou decisões de negócio que não podem ser determinadas somente pela IA e precisam ser confirmadas com a equipe responsável pelo SISDPU 2.0.

RESTRIÇÕES:

- Não invente regras institucionais da Defensoria Pública da União.
- Não suponha nomes de tabelas, colunas, endpoints ou classes caso essas informações não tenham sido fornecidas.
- Quando faltar informação técnica, indique explicitamente que o ponto precisa ser verificado no código ou no banco de dados.
- Não proponha mudanças que afetem outras funcionalidades sem indicar possíveis impactos.
- Não trate a ausência de CPF e a opção "Não tem CPF" como situações equivalentes sem justificar a regra.
- Considere acessibilidade, clareza da interface e consistência visual.
- Preserve as regras de negócio existentes que ainda forem válidas.
- Utilize linguagem técnica, porém clara e objetiva.

FORMATO:

Apresente a análise utilizando a seguinte estrutura:

1. Problema identificado
2. Necessidade do usuário
3. Requisitos funcionais
4. Regras de negócio
5. Comportamento da interface
6. Impactos técnicos
   - Front-end
   - Back-end
   - Banco de dados
7. História de usuário
8. Critérios de aceite
9. Casos de teste
10. Riscos e pontos que precisam de validação humana
11. Recomendação final

Para os casos de teste, utilize uma tabela contendo:

Cenário | Ação do usuário | Resultado esperado

CRITÉRIOS DE QUALIDADE:

A resposta deve:

- ser clara e objetiva;
- distinguir requisito de implementação;
- considerar a integração entre front-end, back-end e banco de dados;
- produzir critérios de aceite verificáveis;
- apresentar casos de teste coerentes;
- identificar possíveis inconsistências;
- evitar inventar informações sobre o sistema;
- destacar explicitamente aquilo que precisa ser validado pela equipe;
- considerar a experiência do usuário;
- ser tecnicamente coerente com um processo de modernização de software.
```

---

## 8. Resultado refinado

### 1. Problema identificado

A funcionalidade precisa permitir que o sistema represente explicitamente a situação em que uma pessoa não possui CPF.

Atualmente, deixar o campo vazio pode representar diferentes situações, como ausência do documento, esquecimento no preenchimento ou cadastro incompleto.

Por isso, é necessário criar uma forma explícita de registrar que a pessoa declarou não possuir CPF.

### 2. Necessidade do usuário

O usuário responsável pelo cadastro precisa conseguir registrar uma pessoa que não possui CPF sem ser impedido por validações de obrigatoriedade do formulário.

Ao mesmo tempo, o sistema precisa diferenciar essa situação de um preenchimento incompleto.

### 3. Requisitos funcionais

**RF01:** O sistema deve disponibilizar o checkbox **"Não tem CPF"** na tela de Cadastro de Pessoa Física.

**RF02:** O sistema deve permitir a marcação e desmarcação da opção.

**RF03:** Quando a opção estiver marcada, o campo CPF deve ficar desabilitado.

**RF04:** Quando a opção estiver marcada, o CPF não deve ser considerado obrigatório.

**RF05:** Quando a opção for desmarcada, o campo CPF deve voltar a ficar disponível.

**RF06:** O estado da opção deve ser enviado corretamente ao back-end.

**RF07:** O sistema deve persistir uma informação que permita identificar que a pessoa declarou não possuir CPF.

**RF08:** Ao consultar ou editar posteriormente o cadastro, o sistema deve recuperar corretamente a informação.

### 4. Regras de negócio

- CPF e "Não tem CPF" representam condições mutuamente exclusivas.
- Quando "Não tem CPF" estiver marcado, não deverá existir um CPF válido associado simultaneamente àquela condição.
- A ausência de CPF sem marcação da opção não deve ser automaticamente interpretada como declaração de que a pessoa não possui CPF.
- O comportamento de obrigatoriedade deve respeitar as demais regras existentes no cadastro.
- Caso exista regra equivalente no sistema legado, ela deve ser considerada antes da definição final.

### 5. Comportamento da interface

#### Checkbox desmarcado

O campo CPF permanece habilitado e sujeito às validações normais do cadastro.

#### Checkbox marcado

O campo CPF deve ser desabilitado e sua obrigatoriedade deve ser removida de acordo com as regras definidas para a funcionalidade.

A interface deve indicar visualmente que o campo não está disponível para edição.

#### Checkbox marcado e posteriormente desmarcado

O campo CPF deve voltar ao estado habilitado.

Caso exista valor anteriormente digitado no campo, a equipe deverá definir se ele deverá ser restaurado ou apagado permanentemente após a marcação do checkbox.

Esse comportamento precisa ser validado como regra de negócio.

### 6. Impactos técnicos

#### Front-end

O front-end deverá:

- adicionar o componente visual;
- controlar o estado do checkbox;
- habilitar ou desabilitar o campo CPF;
- ajustar as validações;
- enviar corretamente a informação para o back-end;
- recuperar a informação ao carregar um cadastro existente.

#### Back-end

O back-end deverá:

- receber a informação;
- validar combinações inconsistentes;
- permitir ausência de CPF quando a condição for válida;
- persistir a informação;
- retornar o estado corretamente durante consultas e edições.

#### Banco de dados

Deve existir uma forma de diferenciar explicitamente:

1. pessoa com CPF;
2. pessoa que declarou não possuir CPF;
3. cadastro no qual o CPF não foi informado.

A estrutura real do banco de dados deve ser analisada antes da implementação.

A IA não deve determinar nomes de colunas ou alterações no esquema sem conhecer a estrutura existente.

### 7. História de usuário

**Como** usuário responsável pelo Cadastro de Pessoa Física,

**quero** informar que determinada pessoa não possui CPF,

**para que** seja possível concluir o cadastro corretamente sem inserir informações inexistentes ou inválidas.

### 8. Critérios de aceite

- O checkbox "Não tem CPF" deve ser exibido na tela de Cadastro de Pessoa Física.
- O campo CPF deve permanecer habilitado quando o checkbox estiver desmarcado.
- Ao marcar "Não tem CPF", o campo CPF deve ser desabilitado.
- O formulário deve permitir salvar o cadastro sem CPF quando a opção estiver marcada e as demais informações obrigatórias estiverem válidas.
- Ao desmarcar a opção, o campo CPF deve voltar a ficar habilitado.
- O sistema não deve permitir inconsistência entre um CPF informado e a declaração de ausência do documento.
- A informação deve ser enviada corretamente ao back-end.
- A condição deve ser persistida.
- Ao editar posteriormente a pessoa, o estado da opção deve ser recuperado corretamente.
- A implementação não deve quebrar cadastros existentes.
- O comportamento deve ser validado tanto no front-end quanto no back-end.

### 9. Casos de teste

| Cenário | Ação do usuário | Resultado esperado |
|---|---|---|
| Cadastro com CPF | Informar um CPF válido e manter "Não tem CPF" desmarcado | Cadastro deve seguir as validações normais |
| Pessoa sem CPF | Marcar "Não tem CPF" | Campo CPF deve ser desabilitado |
| Salvar sem CPF | Marcar "Não tem CPF" e preencher os demais campos obrigatórios | Cadastro deve poder ser concluído |
| Desmarcar opção | Marcar e posteriormente desmarcar "Não tem CPF" | Campo CPF deve voltar a ser habilitado |
| CPF incompatível | Tentar manter CPF preenchido simultaneamente à declaração de ausência | Sistema deve impedir estado inconsistente conforme regra definida |
| Persistência | Salvar pessoa com "Não tem CPF" marcado | Informação deve ser persistida |
| Edição | Abrir novamente cadastro de pessoa sem CPF | Checkbox deve aparecer no estado salvo |
| Validação do back-end | Enviar requisição inconsistente diretamente ao back-end | Back-end deve validar a regra independentemente do front-end |

### 10. Riscos e pontos que precisam de validação humana

Devem ser confirmados pela equipe:

- estrutura real das tabelas do banco;
- necessidade de criação ou alteração de coluna;
- regras institucionais para pessoas sem CPF;
- existência de funcionalidade equivalente no sistema legado;
- impacto em pesquisas e consultas que utilizem CPF;
- comportamento de outros sistemas ou integrações que dependam do documento;
- tratamento de valores anteriormente digitados quando o checkbox for marcado.

### 11. Recomendação final

A funcionalidade deve ser implementada considerando todas as camadas da aplicação.

O checkbox não deve ser tratado apenas como alteração visual.

A implementação precisa representar uma regra de negócio consistente, validada no front-end e no back-end e corretamente persistida no banco de dados.

Antes da implementação definitiva, as decisões identificadas como ambíguas devem ser confirmadas com a equipe responsável pelo sistema.

---

## 9. Técnicas utilizadas

- [x] Role Prompting
- [ ] Few-Shot Prompting
- [x] Contexto
- [x] Restrições
- [x] Formato de saída
- [x] Prompt em etapas
- [x] Refinamento iterativo
- [ ] Outra

---

## 10. Comparação

O prompt refinado produziu um resultado significativamente mais adequado do que o prompt inicial.

| Critério | Prompt inicial | Prompt refinado |
|---|---|---|
| Clareza | Média | Alta |
| Contexto | Baixo | Alto |
| Relevância | Média | Alta |
| Organização | Baixa | Alta |
| Precisão | Média | Alta |
| Utilidade | Média | Alta |

O prompt inicial apresentou apenas uma descrição curta da demanda. Como consequência, a IA precisou realizar diversas suposições para elaborar a resposta.

No prompt refinado foram fornecidos papel, contexto, objetivo, tarefa, restrições, formato de saída e critérios de qualidade.

Isso reduziu ambiguidades e fez com que a resposta considerasse não somente o checkbox na interface, mas também regras de negócio, integração entre camadas, persistência, testes e validação humana.

Portanto, o **Prompt B, refinado**, produziu a resposta mais adequada.

---

## 11. Validação

O resultado da IA não deve ser utilizado automaticamente como especificação definitiva da funcionalidade.

A validação deve ocorrer por meio de diferentes fontes.

Primeiramente, é necessário comparar a resposta com o comportamento do sistema legado, caso exista funcionalidade equivalente.

Também deve ser realizada análise do código do SISDPU 2.0 para identificar as validações já existentes no front-end e no back-end.

A estrutura do banco de dados deve ser consultada para verificar de que forma a informação pode ser armazenada.

Além disso, as regras de negócio devem ser confirmadas com os responsáveis pela definição funcional do sistema.

Após a implementação, devem ser executados testes para verificar se os critérios de aceite foram atendidos.

Dessa forma, a resposta da IA funciona como apoio ao processo de análise, enquanto a decisão final continua dependendo de validação humana e técnica.

---

## 12. Ética e responsabilidade

Existem riscos no uso de Inteligência Artificial Generativa durante o desenvolvimento ou modernização de sistemas.

A IA pode:

- inventar regras de negócio;
- sugerir tabelas ou campos inexistentes;
- propor soluções tecnicamente incompatíveis com a arquitetura real;
- deixar de identificar impactos importantes;
- produzir uma resposta convincente, porém incorreta;
- interpretar incorretamente requisitos institucionais.

Em sistemas utilizados por instituições públicas, esses riscos precisam ser considerados com ainda mais atenção, pois uma implementação incorreta pode afetar usuários e processos de trabalho.

Por esse motivo, a IA deve ser utilizada como ferramenta de apoio ao profissional, e não como substituta da análise humana.

Informações técnicas, regras de negócio e decisões que afetem o funcionamento do sistema devem ser verificadas antes de sua utilização.

---

## 13. Take Away

A atividade demonstrou que Engenharia de Prompt não consiste apenas em fazer uma pergunta maior para uma Inteligência Artificial.

Um prompt bem estruturado precisa fornecer contexto, definir claramente o objetivo, estabelecer restrições e informar o formato esperado da resposta.

Também foi possível perceber que pequenas alterações na forma de descrever um problema podem gerar grandes diferenças na qualidade dos resultados.

No caso analisado, o primeiro prompt gerou uma solução superficial para a funcionalidade. Após o refinamento, a IA passou a considerar requisitos, regras de negócio, interface, back-end, banco de dados, testes e riscos.

O principal aprendizado foi que a IA pode contribuir significativamente para atividades de Engenharia de Software, principalmente no levantamento e organização de requisitos, desde que suas respostas sejam analisadas criticamente e validadas por pessoas que conhecem o sistema.

A Engenharia de Prompt, portanto, melhora a comunicação entre o usuário e a IA, mas não elimina a necessidade de conhecimento técnico, pensamento crítico e responsabilidade humana.

---

## 14. Link

Tendencias/aula-02
/

engenharia-de-prompt.md
