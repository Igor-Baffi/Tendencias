# Atividade - Refinamento de Prompts

## Identificação

* **Nome:** Igor Baffi Felippelli Vieira
* **Turma:** Ciência da Computação
* **Data:** 03/09
* **Ferramenta de IA utilizada:** ChatGPT

---

## Problema escolhido

### Contexto

A Defensoria Pública da União está realizando a modernização do sistema legado SISDPU para uma nova aplicação denominada SISDPU 2.0.

Durante esse processo, funcionalidades existentes precisam ser analisadas antes de serem reproduzidas ou aprimoradas, pois uma alteração aparentemente simples pode envolver regras de negócio, comportamento da interface, validações, comunicação entre front-end e back-end e persistência de informações no banco de dados.

Uma das funcionalidades analisadas está localizada na tela de Cadastro de Pessoa Física. Nessa tela existe o campo CPF, porém podem ocorrer situações em que a pessoa cadastrada não possua esse documento.

### Problema

É necessário permitir que o usuário informe explicitamente que uma pessoa não possui CPF por meio de um checkbox denominado **"Não tem CPF"**.

Entretanto, a implementação não pode ser apenas visual. O sistema deve conseguir diferenciar uma pessoa que declarou não possuir CPF de um cadastro em que o campo simplesmente não foi preenchido.

A funcionalidade também pode provocar impactos no front-end, back-end, banco de dados, validações do formulário e demais funcionalidades que utilizem o CPF como informação de identificação ou consulta.

### Objetivo

Utilizar Inteligência Artificial Generativa como ferramenta de apoio à análise da funcionalidade **"Não tem CPF"**, verificando como diferentes níveis de detalhamento e refinamento do prompt influenciam a qualidade, precisão, organização e utilidade da resposta produzida.

---

## Prompt 1

### Prompt

```text
Analise a demanda de adicionar a opção "Não tem CPF" na tela de Cadastro de Pessoa Física do SISDPU 2.0 e diga como ela deve ser implementada.
```

### Resultado

A funcionalidade pode ser implementada por meio da criação de um checkbox denominado **"Não tem CPF"** próximo ao campo CPF.

Quando o usuário marcar essa opção, o campo CPF deverá ser desabilitado e deixar de ser obrigatório. Caso a opção seja desmarcada, o campo deverá voltar a ficar habilitado para preenchimento.

O estado do checkbox deverá ser enviado ao back-end e armazenado no banco de dados para que a informação seja recuperada posteriormente.

Também devem ser realizados testes para verificar se o usuário consegue cadastrar uma pessoa sem CPF quando a opção estiver marcada.

### Análise

O Prompt 1 conseguiu apresentar a ideia principal da demanda e permitiu que a IA identificasse alguns comportamentos básicos da funcionalidade.

Entre os pontos positivos, a resposta identificou:

* criação do checkbox;
* desabilitação do campo CPF;
* remoção da obrigatoriedade;
* envio da informação ao back-end;
* necessidade de persistência;
* necessidade de testes.

Entretanto, a resposta ficou excessivamente genérica.

O prompt não apresentou informações suficientes sobre:

* arquitetura do SISDPU 2.0;
* comportamento do sistema legado;
* regras de negócio existentes;
* público que utilizará a análise;
* tecnologias envolvidas;
* estrutura do banco de dados;
* comportamento durante a edição de um cadastro existente;
* tratamento de um CPF já digitado;
* impactos em outras funcionalidades.

Além disso, a IA presumiu que existiria uma maneira simples de armazenar essa informação no banco de dados, mesmo sem conhecer sua estrutura.

Portanto, o Prompt 1 conseguiu transmitir a demanda, mas deixou muitas decisões abertas para interpretação da IA.

---

## Prompt 2

### Alterações realizadas

* **Papel:** foi definido que a IA deveria atuar como analista de sistemas especializado em modernização de sistemas legados.
* **Contexto:** foram fornecidas informações sobre a modernização do SISDPU para o SISDPU 2.0.
* **Objetivo:** foi definido que a resposta deveria analisar a funcionalidade de forma completa e não apenas visual.
* **Público:** foi informado que a análise seria utilizada como apoio pela equipe responsável pelo SISDPU 2.0.
* **Formato:** foi definida uma estrutura contendo problema, regras de negócio, interface, impactos técnicos, critérios de aceite e testes.
* **Restrições:** a IA foi orientada a não inventar tabelas, colunas, endpoints ou regras institucionais.
* **Critérios:** a resposta deveria ser clara, tecnicamente coerente e útil para apoiar a equipe de desenvolvimento.

### Prompt

```text
Atue como um analista de sistemas especializado em modernização de sistemas legados.

CONTEXTO:

A Defensoria Pública da União está modernizando o sistema legado SISDPU para uma nova aplicação denominada SISDPU 2.0.

Uma das demandas está relacionada à tela de Cadastro de Pessoa Física.

Atualmente existe um campo para preenchimento do CPF. Entretanto, existem situações em que uma pessoa pode não possuir CPF. Por isso, deseja-se adicionar à interface um checkbox denominado "Não tem CPF".

OBJETIVO:

Analisar como essa funcionalidade deve ser implementada de maneira consistente no SISDPU 2.0, considerando não apenas a alteração visual, mas também as regras de negócio e seus impactos técnicos.

PÚBLICO:

A resposta será utilizada como apoio pela equipe responsável pela análise e desenvolvimento do SISDPU 2.0.

TAREFA:

Analise:

1. o comportamento esperado do campo CPF quando a opção "Não tem CPF" for marcada ou desmarcada;
2. as principais regras de negócio envolvidas;
3. os impactos no front-end;
4. os impactos no back-end;
5. os possíveis impactos no banco de dados;
6. os critérios de aceite da funcionalidade;
7. possíveis casos de teste.

FORMATO:

Organize a resposta utilizando os seguintes tópicos:

1. Problema
2. Regras de negócio
3. Comportamento da interface
4. Impactos no front-end
5. Impactos no back-end
6. Impactos no banco de dados
7. Critérios de aceite
8. Casos de teste

RESTRIÇÕES:

- Não invente nomes de tabelas, colunas, classes ou endpoints.
- Não presuma regras institucionais que não tenham sido informadas.
- Quando alguma informação depender da arquitetura real do SISDPU 2.0, indique que ela precisa ser verificada pela equipe.
- Considere que as regras de negócio existentes no sistema legado devem ser preservadas quando ainda forem válidas.

CRITÉRIO DE QUALIDADE:

A resposta deve ser clara, tecnicamente coerente e suficientemente objetiva para servir como apoio à análise da funcionalidade pela equipe de desenvolvimento.
```

### Resultado

#### 1. Problema

A funcionalidade precisa permitir que o sistema registre explicitamente que determinada pessoa não possui CPF.

Deixar o campo CPF vazio não é suficiente, pois isso também pode representar um erro de preenchimento ou um cadastro incompleto.

#### 2. Regras de negócio

* O checkbox "Não tem CPF" e o preenchimento de um CPF representam condições incompatíveis.
* Quando a opção estiver marcada, o CPF não deverá ser obrigatório.
* Quando a opção estiver desmarcada, devem ser aplicadas as validações normais do campo CPF.
* A ausência de CPF não deve ser automaticamente interpretada como declaração de que a pessoa não possui o documento.
* Regras existentes no SISDPU legado devem ser verificadas antes da definição final.

#### 3. Comportamento da interface

Quando o checkbox estiver desmarcado, o campo CPF deverá permanecer disponível.

Ao marcar "Não tem CPF", o campo deverá ser desabilitado e deixar de ser obrigatório.

Caso a opção seja desmarcada novamente, o campo CPF deverá voltar a ficar habilitado.

#### 4. Impactos no front-end

O front-end deverá:

* adicionar o checkbox;
* controlar seu estado;
* habilitar e desabilitar o campo CPF;
* ajustar as validações do formulário;
* enviar a informação para o back-end;
* recuperar o estado durante a edição do cadastro.

#### 5. Impactos no back-end

O back-end deverá:

* receber a informação correspondente;
* permitir a ausência de CPF quando a condição for válida;
* impedir combinações inconsistentes;
* persistir a informação;
* recuperar corretamente o estado do cadastro.

#### 6. Impactos no banco de dados

Deve existir alguma forma de diferenciar uma pessoa que declarou não possuir CPF de uma pessoa cujo CPF simplesmente não foi informado.

A estrutura real do banco deverá ser analisada antes de qualquer alteração.

Não é possível determinar, somente com as informações fornecidas, se será necessária a criação de uma nova coluna ou se alguma estrutura existente poderá ser utilizada.

#### 7. Critérios de aceite

* O checkbox deve ser exibido na tela.
* Ao marcar a opção, o campo CPF deve ser desabilitado.
* O CPF deve deixar de ser obrigatório enquanto a opção estiver marcada.
* O cadastro deve poder ser salvo sem CPF quando a opção estiver selecionada.
* Ao desmarcar, o campo deve voltar a ficar disponível.
* A informação deve ser persistida e recuperada durante a edição.

#### 8. Casos de teste

| Cenário          | Ação do usuário                          | Resultado esperado                   |
| ---------------- | ---------------------------------------- | ------------------------------------ |
| Cadastro com CPF | Informar CPF válido                      | Cadastro segue validações normais    |
| Pessoa sem CPF   | Marcar "Não tem CPF"                     | Campo CPF é desabilitado             |
| Salvar sem CPF   | Marcar opção e preencher demais campos   | Cadastro pode ser concluído          |
| Desmarcar opção  | Marcar e depois desmarcar                | Campo CPF volta a ser habilitado     |
| Edição           | Abrir pessoa anteriormente salva sem CPF | Checkbox apresenta estado persistido |

---

## Comparação

| Critério                | Prompt 1 | Prompt 2 |
| ----------------------- | -------: | -------: |
| Clareza                 |        3 |        4 |
| Precisão                |        2 |        4 |
| Relevância              |        3 |        4 |
| Organização             |        2 |        5 |
| Adequação ao público    |        2 |        4 |
| Atendimento ao objetivo |        3 |        4 |
| Utilidade prática       |        2 |        4 |

O Prompt 2 apresentou uma melhora significativa em relação ao Prompt 1.

A inclusão de contexto, papel, público, tarefas específicas, restrições e formato fez com que a IA analisasse a funcionalidade em diferentes camadas do sistema.

A resposta deixou de tratar o problema apenas como uma alteração de interface e passou a considerar front-end, back-end, banco de dados, regras de negócio e testes.

Mesmo assim, alguns comportamentos continuaram indefinidos.

---

## Prompt 3

### O que ainda precisava melhorar?

Embora o Prompt 2 tenha produzido uma resposta mais adequada, alguns pontos ainda poderiam ser melhorados.

Não havia instruções suficientemente detalhadas sobre:

* CPF previamente digitado antes da marcação do checkbox;
* comportamento ao marcar e posteriormente desmarcar a opção;
* edição de cadastros existentes;
* diferenças entre requisito confirmado e proposta técnica;
* impactos em outras funcionalidades que utilizem CPF;
* validações realizadas diretamente pelo back-end;
* informações que dependem obrigatoriamente de validação humana;
* possibilidade de a IA apresentar uma hipótese como se fosse uma regra confirmada.

Também foi percebido que uma resposta tecnicamente coerente ainda poderia conter suposições.

### Hipótese

Acredito que a resposta ficará melhor porque o Prompt 3 fornecerá informações mais específicas sobre os cenários que precisam ser analisados e obrigará a IA a diferenciar informações confirmadas, propostas técnicas e pontos que precisam de validação.

Essa alteração deverá reduzir suposições e tornar a resposta mais útil para um cenário profissional de modernização de software.

### Prompt

```text
Atue como um analista de sistemas e engenheiro de software especializado em modernização de sistemas legados, levantamento de requisitos, UX/UI e aplicações web corporativas.

CONTEXTO:

A Defensoria Pública da União está realizando a modernização do sistema legado SISDPU para uma nova aplicação denominada SISDPU 2.0.

O processo de modernização exige que funcionalidades existentes sejam analisadas antes de serem reproduzidas ou aprimoradas, evitando perda de regras de negócio.

Uma das funcionalidades em análise encontra-se na tela de Cadastro de Pessoa Física.

Atualmente existe um campo CPF, porém podem existir situações em que a pessoa cadastrada não possua esse documento. Para representar essa situação de maneira explícita, pretende-se disponibilizar um checkbox denominado "Não tem CPF".

A ausência de CPF declarada pelo usuário deve ser diferenciada de uma situação em que o campo simplesmente não foi preenchido.

A solução deve considerar interface, validações, comunicação entre front-end e back-end, persistência das informações e edição posterior do cadastro.

Sempre que existir comportamento equivalente no SISDPU legado, ele deverá ser utilizado como referência, desde que a regra continue válida para o SISDPU 2.0.

OBJETIVO:

Definir uma proposta funcional para a opção "Não tem CPF", identificando requisitos, regras de negócio, impactos técnicos, critérios de aceite, casos de teste e pontos que necessitam de validação humana.

PÚBLICO:

A análise será utilizada como apoio por analistas e desenvolvedores envolvidos na modernização do SISDPU 2.0.

TAREFA:

Realize a análise nas seguintes etapas:

1. Identifique o problema que a funcionalidade busca resolver.

2. Explique a necessidade do usuário.

3. Defina os requisitos funcionais necessários.

4. Identifique as regras de negócio relacionadas ao CPF e ao checkbox "Não tem CPF".

5. Descreva o comportamento esperado da interface quando:
   - o checkbox estiver desmarcado;
   - o checkbox for marcado;
   - o checkbox for marcado após um CPF já ter sido digitado;
   - o usuário marcar e posteriormente desmarcar a opção;
   - um cadastro existente for aberto para edição.

6. Analise separadamente os impactos no:
   - front-end;
   - back-end;
   - banco de dados;
   - validações do formulário.

7. Explique como o sistema poderia diferenciar conceitualmente:
   - pessoa com CPF;
   - pessoa que declarou não possuir CPF;
   - cadastro no qual o CPF simplesmente não foi informado.

8. Crie uma história de usuário para a funcionalidade.

9. Elabore critérios de aceite objetivos e verificáveis.

10. Elabore casos de teste contemplando pelo menos:
   - cadastro normal com CPF;
   - cadastro de pessoa sem CPF;
   - marcação do checkbox;
   - desmarcação do checkbox;
   - CPF já digitado antes da marcação;
   - tentativa de enviar CPF e "Não tem CPF" simultaneamente;
   - edição posterior do cadastro;
   - persistência e recuperação da informação;
   - validação realizada diretamente pelo back-end.

11. Identifique possíveis impactos em outras funcionalidades que utilizem o CPF como consulta ou identificação.

12. Identifique ambiguidades e decisões que não podem ser definidas somente pela IA.

RESTRIÇÕES:

- Não invente regras institucionais da Defensoria Pública da União.
- Não invente nomes de tabelas, colunas, endpoints, classes, componentes ou APIs.
- Não suponha que já exista estrutura no banco de dados para armazenar a nova informação.
- Quando faltar informação técnica, indique explicitamente que ela precisa ser verificada no código, no banco de dados ou com a equipe responsável.
- Não considere automaticamente a ausência de CPF e a declaração "Não tem CPF" como situações equivalentes.
- Não proponha alterações em outras funcionalidades sem indicar seus possíveis impactos.
- Preserve regras de negócio existentes que ainda forem válidas.
- Considere acessibilidade, clareza e consistência da interface.
- Não apresente uma hipótese da IA como se fosse uma regra confirmada do SISDPU 2.0.

FORMATO:

Organize a resposta em:

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
10. Impactos em outras funcionalidades
11. Riscos e ambiguidades
12. Pontos que precisam de validação humana
13. Recomendação final

Para os casos de teste, utilize:

| Cenário | Ação do usuário | Resultado esperado |

CLASSIFICAÇÃO DAS INFORMAÇÕES:

Sempre que uma conclusão depender de informações que não foram fornecidas, classifique-a como:

- CONFIRMADO PELA DEMANDA — quando decorrer diretamente das informações fornecidas;
- PROPOSTA TÉCNICA — quando for uma possível solução sugerida pela IA;
- NECESSITA VALIDAÇÃO — quando depender do código, banco de dados, sistema legado ou decisão da equipe.

CRITÉRIOS DE QUALIDADE:

A resposta deve:

- ser clara e objetiva;
- distinguir requisito de implementação;
- evitar suposições sobre o sistema;
- considerar a integração entre front-end, back-end e banco de dados;
- produzir critérios de aceite verificáveis;
- apresentar casos de teste coerentes;
- identificar possíveis inconsistências;
- separar fatos, propostas e pontos que precisam de validação;
- considerar a experiência do usuário;
- ser tecnicamente coerente com um processo de modernização de software.

Ao final, apresente uma seção chamada "Informações que precisam ser verificadas antes da implementação", contendo somente os pontos que não podem ser determinados com segurança a partir das informações fornecidas.
```

### Resultado

#### 1. Problema identificado

**CONFIRMADO PELA DEMANDA**

O sistema precisa representar explicitamente a condição em que uma pessoa cadastrada não possui CPF.

Apenas deixar o campo CPF vazio não é suficiente para representar essa condição, porque o valor vazio também pode ser resultado de esquecimento, erro de preenchimento ou cadastro incompleto.

---

#### 2. Necessidade do usuário

**CONFIRMADO PELA DEMANDA**

O usuário responsável pelo cadastro precisa conseguir informar que determinada pessoa não possui CPF e concluir o cadastro sem fornecer uma informação inexistente.

Ao mesmo tempo, o sistema precisa preservar a diferenciação entre ausência declarada de CPF e campo não preenchido.

---

#### 3. Requisitos funcionais

**RF01:** O sistema deve disponibilizar o checkbox **"Não tem CPF"** na tela de Cadastro de Pessoa Física.

**RF02:** O usuário deve conseguir marcar e desmarcar a opção.

**RF03:** Quando a opção estiver marcada, o campo CPF deverá ficar indisponível para preenchimento.

**RF04:** Quando a opção estiver marcada, a ausência do CPF deverá ser aceita pelo sistema.

**RF05:** Quando a opção for desmarcada, o campo CPF deverá voltar a ficar disponível.

**RF06:** O estado da opção deverá ser enviado ao back-end.

**RF07:** O sistema deverá possuir uma forma de persistir a condição declarada.

**RF08:** Ao editar um cadastro existente, o sistema deverá recuperar corretamente a condição previamente armazenada.

**RF09:** O back-end deverá impedir estados inconsistentes entre CPF informado e declaração de ausência do documento.

---

#### 4. Regras de negócio

**CONFIRMADO PELA DEMANDA**

A existência de um CPF e a declaração "Não tem CPF" representam estados diferentes.

**PROPOSTA TÉCNICA**

CPF preenchido e "Não tem CPF" marcado devem ser tratados como condições mutuamente exclusivas.

**NECESSITA VALIDAÇÃO**

É necessário verificar com a equipe responsável se a obrigatoriedade do CPF possui exceções adicionais além da funcionalidade analisada.

**NECESSITA VALIDAÇÃO**

Também deverá ser analisado o SISDPU legado para verificar se existe comportamento equivalente e quais regras deverão ser preservadas.

---

#### 5. Comportamento da interface

##### Checkbox desmarcado

**PROPOSTA TÉCNICA**

O campo CPF permanece habilitado e sujeito às validações normais existentes no sistema.

##### Checkbox marcado

**PROPOSTA TÉCNICA**

O campo CPF deverá ser desabilitado e apresentar visualmente seu estado de indisponibilidade.

A obrigatoriedade deverá ser removida enquanto a declaração permanecer selecionada.

##### CPF já preenchido antes da marcação

**NECESSITA VALIDAÇÃO**

A equipe precisa decidir se um CPF anteriormente digitado deverá ser imediatamente apagado ao marcar "Não tem CPF" ou apenas removido no momento da submissão.

A IA não possui informações suficientes para estabelecer essa regra.

##### Marcar e posteriormente desmarcar

**NECESSITA VALIDAÇÃO**

É necessário definir se um CPF anteriormente digitado deverá ser restaurado após a desmarcação ou se o campo deverá permanecer vazio.

##### Edição de cadastro existente

**PROPOSTA TÉCNICA**

Ao abrir um cadastro de pessoa que declarou não possuir CPF, o checkbox deverá aparecer marcado e o campo CPF deverá respeitar o estado correspondente.

---

#### 6. Impactos técnicos

##### Front-end

**PROPOSTA TÉCNICA**

O front-end deverá:

* adicionar o componente correspondente ao checkbox;
* controlar seu estado;
* controlar o estado do campo CPF;
* atualizar as validações do formulário;
* impedir combinações inconsistentes na interface;
* enviar corretamente a condição ao back-end;
* recuperar o estado ao editar um cadastro;
* manter consistência visual e acessibilidade.

##### Back-end

**PROPOSTA TÉCNICA**

O back-end deverá:

* receber a informação correspondente à condição;
* validar a combinação entre CPF e declaração de ausência;
* permitir cadastro sem CPF quando a regra estiver satisfeita;
* persistir a condição;
* recuperar a informação nas operações de consulta;
* validar a regra independentemente do comportamento do front-end.

##### Banco de dados

**NECESSITA VALIDAÇÃO**

A estrutura atual do banco deverá ser analisada.

Deve existir uma forma lógica de diferenciar:

1. pessoa com CPF;
2. pessoa que declarou não possuir CPF;
3. situação em que o CPF simplesmente não foi informado.

Não é possível determinar se será necessária uma nova coluna, alteração de uma estrutura existente ou outra estratégia sem analisar o modelo de dados atual.

---

#### 7. História de usuário

**Como** usuário responsável pelo Cadastro de Pessoa Física,

**quero** informar explicitamente que determinada pessoa não possui CPF,

**para que** seja possível concluir corretamente o cadastro sem inserir uma informação inexistente ou inválida.

---

#### 8. Critérios de aceite

* O checkbox "Não tem CPF" deve estar disponível na tela de Cadastro de Pessoa Física.
* Com o checkbox desmarcado, o campo CPF deve permanecer disponível.
* Ao marcar o checkbox, o campo CPF deve ficar indisponível.
* O sistema deve permitir salvar uma pessoa sem CPF quando a condição estiver corretamente declarada.
* Ao desmarcar a opção, o campo CPF deve voltar a ficar disponível.
* O sistema não deve aceitar simultaneamente um CPF válido e uma declaração de ausência de CPF.
* O estado da opção deve ser enviado ao back-end.
* A condição deve ser persistida.
* O estado salvo deve ser recuperado durante uma edição posterior.
* A validação também deve existir no back-end.
* A implementação não deve provocar regressões em cadastros existentes.

---

#### 9. Casos de teste

| Cenário                  | Ação do usuário                                            | Resultado esperado                                   |
| ------------------------ | ---------------------------------------------------------- | ---------------------------------------------------- |
| Cadastro normal          | Informar CPF válido e manter "Não tem CPF" desmarcado      | Cadastro deve seguir as validações existentes        |
| Pessoa sem CPF           | Marcar "Não tem CPF"                                       | Campo CPF deve ficar indisponível                    |
| Salvar pessoa sem CPF    | Marcar a opção e preencher os demais campos obrigatórios   | Cadastro deve poder ser concluído                    |
| Desmarcar opção          | Marcar e posteriormente desmarcar                          | Campo CPF deve voltar a ficar disponível             |
| CPF previamente digitado | Digitar CPF e posteriormente marcar "Não tem CPF"          | Comportamento deve seguir regra definida pela equipe |
| Estado inconsistente     | Tentar enviar CPF e declaração de ausência simultaneamente | Back-end deve rejeitar a inconsistência              |
| Persistência             | Salvar pessoa com "Não tem CPF" marcado                    | Condição deve ser armazenada                         |
| Recuperação              | Abrir novamente cadastro salvo sem CPF                     | Checkbox deve apresentar o estado salvo              |
| Edição                   | Alterar cadastro existente                                 | Estado da funcionalidade deve permanecer consistente |
| Validação direta         | Enviar requisição inconsistente sem passar pela interface  | Back-end deve aplicar a regra de negócio             |

---

#### 10. Impactos em outras funcionalidades

**NECESSITA VALIDAÇÃO**

É necessário verificar funcionalidades que utilizam CPF como:

* critério de pesquisa;
* identificação de pessoas;
* validação de duplicidade;
* integração com outros serviços;
* geração de documentos;
* relatórios;
* filtros;
* consultas externas.

Uma alteração no significado da ausência de CPF poderá afetar funcionalidades que atualmente consideram um valor vazio como única representação dessa situação.

---

#### 11. Riscos e ambiguidades

Entre os principais riscos estão:

* interpretar campo vazio como declaração de ausência de CPF;
* permitir CPF e "Não tem CPF" simultaneamente;
* armazenar a condição incorretamente;
* perder a informação durante edição;
* provocar incompatibilidade com cadastros anteriores;
* alterar consultas baseadas em CPF;
* criar comportamento diferente entre front-end e back-end;
* implementar uma regra diferente daquela utilizada no sistema legado.

---

#### 12. Pontos que precisam de validação humana

Devem ser verificados:

* comportamento existente no SISDPU legado;
* estrutura atual do banco de dados;
* existência de campo capaz de representar a condição;
* validações já existentes no back-end;
* regras institucionais relacionadas ao CPF;
* comportamento de CPF previamente preenchido;
* impactos em buscas e integrações;
* comportamento esperado durante edição.

---

#### 13. Recomendação final

A funcionalidade não deve ser tratada somente como inclusão de um checkbox na interface.

A opção "Não tem CPF" representa uma condição de negócio e, portanto, precisa ser tratada de maneira consistente no front-end, back-end e banco de dados.

Antes da implementação definitiva, os pontos classificados como **NECESSITA VALIDAÇÃO** deverão ser confirmados pela equipe responsável pelo SISDPU 2.0.

### Informações que precisam ser verificadas antes da implementação

* estrutura real do banco de dados;
* existência de funcionalidade equivalente no SISDPU legado;
* regra institucional relacionada ao cadastro sem CPF;
* comportamento de um CPF digitado antes da marcação;
* comportamento ao desmarcar a opção;
* validações existentes no back-end;
* impacto em pesquisas e identificação de pessoas;
* impacto em integrações externas que utilizem CPF.

---

## Comparação final

| Critério                | Prompt 1 | Prompt 2 | Prompt 3 |
| ----------------------- | -------: | -------: | -------: |
| Clareza                 |        3 |        4 |        5 |
| Precisão                |        2 |        4 |        5 |
| Relevância              |        3 |        4 |        5 |
| Organização             |        2 |        5 |        5 |
| Adequação ao público    |        2 |        4 |        5 |
| Atendimento ao objetivo |        3 |        4 |        5 |
| Utilidade               |        2 |        4 |        5 |
| **Total**               |   **17** |   **29** |   **35** |

A principal evolução ocorreu entre o Prompt 1 e o Prompt 2, devido à inclusão de contexto, papel, público, formato e restrições.

Entretanto, o Prompt 3 apresentou a resposta mais adequada para a situação analisada, pois acrescentou cenários específicos e passou a exigir a separação entre informações confirmadas, propostas técnicas e decisões que precisam de validação.

A modificação de maior impacto foi a definição explícita das restrições e da classificação das informações.

Isso diminuiu a possibilidade de uma sugestão da IA ser interpretada como uma regra real do SISDPU 2.0.

O resultado demonstra que um prompt maior não é necessariamente melhor. O Prompt 3 apresentou melhor resultado porque as instruções adicionadas tinham objetivos específicos e estavam relacionadas às limitações identificadas nas respostas anteriores.

---

## Validação

A qualidade da resposta foi analisada comparando as sugestões da IA com as informações conhecidas sobre a demanda.

Também foi considerado que o resultado da IA não deve ser utilizado automaticamente como especificação definitiva da funcionalidade.

Para validar tecnicamente a resposta, deverão ser realizadas as seguintes verificações:

* comparar o comportamento sugerido com o SISDPU legado;
* analisar o código atual do SISDPU 2.0;
* verificar as validações existentes no front-end;
* verificar as validações existentes no back-end;
* analisar a estrutura real do banco de dados;
* confirmar as regras de negócio com a equipe responsável;
* verificar impactos em funcionalidades que utilizam CPF;
* executar testes após a implementação.

Também deve ser verificado se a IA apresentou alguma informação como fato sem que existissem dados suficientes para comprová-la.

Dessa forma, a Inteligência Artificial funciona como ferramenta de apoio à análise, enquanto a decisão final permanece dependente de validação humana e técnica.

---

## Reflexão

### 1. Qual foi a principal diferença entre os prompts?

A principal diferença foi o nível de orientação fornecido à Inteligência Artificial.

O Prompt 1 apresentava apenas o problema e solicitava uma solução. Já os Prompts 2 e 3 apresentavam contexto, objetivo, público, estrutura, restrições e critérios de qualidade.

Com isso, a IA precisou realizar menos suposições e conseguiu produzir respostas mais direcionadas ao problema.

### 2. Quais elementos tiveram maior impacto?

Os elementos que tiveram maior impacto foram contexto, restrições, divisão da tarefa em etapas e critérios de qualidade.

O contexto permitiu compreender que se tratava da modernização de um sistema legado utilizado em uma instituição pública.

As restrições reduziram a possibilidade de a IA inventar informações sobre banco de dados, endpoints e regras de negócio.

A divisão em etapas aumentou a organização da análise e os critérios de qualidade ajudaram a orientar o resultado esperado.

### 3. Um prompt maior é necessariamente melhor?

Não.

Um prompt maior somente será melhor quando as novas informações contribuírem para diminuir ambiguidades ou orientar a resposta.

Adicionar palavras, adjetivos ou instruções desnecessárias pode aumentar o tamanho sem melhorar o resultado.

O refinamento deve adicionar informações que tenham finalidade clara.

### 4. O que ocorre quando o objetivo não é claro?

Quando o objetivo não está claramente definido, a IA precisa interpretar o que o usuário pretende obter.

Essa interpretação pode levar a respostas genéricas, informações desnecessárias ou soluções diferentes daquilo que realmente era necessário.

Quanto maior a ambiguidade do objetivo, maior a possibilidade de o resultado não atender à necessidade do usuário.

### 5. Quais informações são indispensáveis?

Considero indispensáveis:

* contexto;
* objetivo;
* tarefa;
* público;
* restrições;
* formato esperado;
* critérios de qualidade.

Dependendo da situação, exemplos também podem ajudar a IA a compreender melhor o padrão de resposta esperado.

### 6. Como essa habilidade pode ser utilizada profissionalmente?

O refinamento de prompts pode ser utilizado por profissionais de Ciência da Computação em diferentes atividades, como levantamento de requisitos, análise de código, criação de casos de teste, documentação, comparação de tecnologias e investigação de problemas.

Em processos de modernização de sistemas legados, essa habilidade permite fornecer à IA informações mais precisas sobre arquitetura, regras, limitações e objetivos, produzindo resultados mais úteis para auxiliar o trabalho da equipe.

Entretanto, a decisão técnica não deve ser delegada integralmente à IA.

### 7. Quais riscos existem ao confiar automaticamente na IA?

Uma IA pode produzir uma resposta organizada e convincente mesmo quando contém informações incorretas.

Entre os riscos estão:

* criação de regras de negócio inexistentes;
* sugestão de tabelas ou campos que não existem;
* utilização de tecnologias incompatíveis;
* interpretação incorreta do requisito;
* omissão de impactos importantes;
* generalizações;
* informações desatualizadas;
* propostas tecnicamente inadequadas.

Por isso, as respostas precisam ser analisadas e validadas.

### 8. Houve alguma situação em que o Prompt 3 ficou pior que o Prompt 2? Se sim, explique.

O Prompt 3 não apresentou piora significativa na qualidade da resposta, porém ficou consideravelmente mais extenso e complexo.

Para uma análise rápida ou uma demanda simples, o Prompt 2 poderia ser mais eficiente.

Isso demonstra que o nível de refinamento também deve ser proporcional à complexidade do problema.

### 9. Existe um ponto em que adicionar mais instruções começa a prejudicar a resposta?

Sim.

Quando muitas instruções são adicionadas sem necessidade, o prompt pode ficar redundante, complexo ou até apresentar regras conflitantes.

Por isso, o objetivo do refinamento não deve ser aumentar o tamanho do prompt, mas identificar quais informações realmente contribuem para a resposta.

### 10. O que você faria para verificar se a resposta tecnicamente está correta?

Eu compararia a resposta com o comportamento real do SISDPU legado e analisaria o código do SISDPU 2.0.

Também verificaria a estrutura do banco de dados, as validações do back-end e as regras de negócio definidas pela equipe.

Após uma eventual implementação, executaria testes baseados nos critérios de aceite para verificar se a funcionalidade apresenta o comportamento esperado.

---

## Take Away

> **Um bom prompt não é simplesmente um prompt longo. Ele precisa fornecer contexto relevante, apresentar um objetivo claro, estabelecer limites e orientar a IA para produzir uma resposta adequada ao problema, sem eliminar a necessidade de análise e validação humana.**

---

## Cinco recomendações

1. **Defina claramente o objetivo:** informe à IA exatamente o que você pretende obter com a resposta.

2. **Forneça contexto relevante:** apresente somente as informações que ajudam a compreender corretamente o problema.

3. **Estabeleça restrições:** informe aquilo que a IA não deve presumir, inventar ou fazer durante a resposta.

4. **Analise e refine de forma iterativa:** utilize a primeira resposta para identificar problemas e melhorar progressivamente o prompt.

5. **Valide o resultado:** nunca considere uma resposta bem escrita como automaticamente correta; confira informações, regras, dados e decisões técnicas antes de utilizá-la.
