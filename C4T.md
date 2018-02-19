# Contrato de Construção de Código Coletivo Tupiniquim 

## Abstrato
O C4T fornece um processo padrão para contribuir, avaliar e discutir melhorias em projetos de software. Ele define requisitos técnicos específicos para projetos como um guia de estilo, testes de unidade git plataformas similares. Ele também estabelece personagens diferentes para projetos, com tarefas claras e distintas. O C4T especifica um processo para documentar e discutir questões, incluindo busca de consenso e descrições claras, uso de "requisição de merge" e revisões sistemáticas.

## Língua
As palavras-chave "DEVERÁ", "NÃO DEVERÁ", "DEVERÃO", "NÃO DEVERÃO", "REQUERIDO" são usados no contexto de obrigatórias. E as palavras-chave "DEVERIA", "NÃO DEVERIA", "DEVERIAM", "NÃO DEVERIAM", "RECOMENDADO" e "OPCIONAL" devem ser interpretadas como não obrigatórias mas altamente recomendadas. Livre traduzida aqui, essas interpretações se baseiam na RFC 2119.

## 1. Objetivos
O C4T destina-se a fornecer um modelo de colaboração ideal reutilizável para projetos de software. Tem esses objetivos específicos:
1. Para maximizar a escala e a diversidade da comunidade em torno de um projeto, reduzindo a fricção para novos Colaboradores e criando um modelo de participação escalonado com fortes feedbacks positivos;
1. Para aliviar as dependências em indivíduos-chave, separando diferentes conjuntos de habilidades para que haja um pool maior de competências em qualquer domínio requerido;
1. Permitir que o projeto se desenvolva de forma mais rápida e precisa, aumentando a diversidade do processo de tomada de decisão;
1. Apoiar o ciclo de vida natural das versões do projeto, desde o experimento até o estado estável, permitindo experiências seguras, falhas rápidas e isolamento de código estável;
1. Para reduzir a complexidade interna dos repositórios de projetos, facilitando assim a participação dos Colaboradores e reduzindo a margem de erro;
1. Forçar a apropriação coletiva do projeto, o que aumenta o incentivo econômico aos Contribuintes e reduz o risco de seqüestro por entidades hostis.

## 2. Design
### 2.1. Preliminares
1. O projeto DEVERÁ usar o sistema de controle de revisão distribuído git.
1. O projeto DEVERÁ ser hospedado em um servidor git, aqui chamado de "Plataforma".
1. Um problema(issue) descreve alguma alteração a ser realizada no projeto como, por exemplo, uma nova funcionalida ou um defeito a ser corrigido.
1. O projeto DEVERÁ usar o rastreador de problemas da Plataforma.
1. O projeto DEVERIA ter diretrizes claramente documentadas para o estilo de código e métricas de qualidade.
1. Um patch é um conjunto alterações que resolvem algum problema claramente identificado.
1. A integração do patch ao projeto ocorre por meio de commits no git, que podem precisar de um merge, para os casos de conflito.
1. Um "Mantenedor" é uma pessoa que faz integra os patchs ao projeto ou auxilia os Colaboradores com essa tarefa. Os Mantenedores não são desenvolvedores; seu trabalho é fazer cumprir o processo de desenvolvimento.
1. Um "Colaborador" é uma pessoa que deseja fornecer um patch.
1. Todos DEVERÃO ter acesso ao branch master.
1. Todos, sem distinção ou discriminação, DEVERÃO ter o mesmo direito de se tornar um Colaborador nos termos deste contrato.

### 2.2. Licenciamento e propriedade
1. Todas as contribuições para o código-fonte do projeto ("patchs") DEVERÃO usar a mesma licença que o projeto.
1. Cada colaborador DEVERÁ ser responsável por se identificar na lista de colaboradores do projeto.

### 2.3. Requisitos do patch
1. Mantenedores e Colaboradores DEVERÃO ter uma conta da Plataforma e DEVERIAM usar seus nomes reais ou um apelido bem conhecido.
1. Um patch DEVERIA ser uma resposta mínima e precisa para exatamente um problema identificado e acordado.
1. Um patch DEVERÁ respeitar as diretrizes de estilo de código do projeto se estas forem definidas.
1. Um patch DEVERÁ respeitar as diretrizes de "Evolução de Contratos Públicos" definidas abaixo.
1. Um patch NÃO DEVERÁ incluir código não trivial de outros projetos, a menos que o Colaborador seja o autor original desse código.
1. UM patch DEVERÁ conter provas de seu funcionamento na formas de testes unitários, de integração e aceitação.
1. Um patch DEVERÁ ser afetar apenas um componente.
1. Um patch DEVERÁ compilar de forma limpa e passar nos auto-testes do projeto ao menos para a principal plataforma de destino.
1. Um patch DEVERÁ ser um incremento a partir do commit mais atual no branch master. Um rebase ou squash DEVERÃO ser aplicados antes do patch ser integrado.
1. Um patch DEVERÁ deve conter uma mensagem de commit composta por:
    - uma unica linha de assunto informando o problema sendo resolvido de forma:
      - curta com até de 50 caracteres,
      - iniciada com a identificação do componente + ":",
      - capitalizada,
      - sem pontuação,
      - conjugada no tempo verbal futuro do presente do modo indicativo,
      - ser capaz de completar a frase "Se aplicado, este patch irá <linha de assunto>",
      - ex. "contribuinte: Validar dv do cnpj";
    - uma linha em branco seguida da solução proposta, com margem de até 72 caractéres;
    - uma linha em branco seguido dos metadados Resolvem, Resolve-parcialmente, Relatado-por, Criado-por.
1. Um "Patch Correto" é aquele que satisfaz os requisitos acima e possuí uma mensagem adequada como no exemplo abaixo.

```
contribuinte: Validar dv do cnpj
   
Atualmente, ao pesquisar uma Pessoa Júridica com um cnpj com dv 
inválido, uma mensagem diferente de "Cnpj Inválido." é exibida.
Exibir essa mensagem facilitará a identificação de erro de digitação.
  
Para resolver isso, a exceção CNPJInvalido foi criada e será lançada 
sempre que a regra de cálculo do DV não for satisfeita. As fachadas
também foram alteradas para traduzir essa exceção na mensagem 
esperada pelo usuário.
    
Resolve: #1234
Relatado-por: Josenildo Produtctowner <jprodutctowner@hacker.com>
Criado-por: Siclano Torvalds <storvalds@hacker.com>
Criado-por: Beltrano Torvalds <btorvalds@hacker.com>
```

### 2.4. Processo de desenvolvimento
1. A mudança no projeto DEVERÁ ser regida pelo padrão de identificar com precisão problemas e aplicar soluções mínimas e precisas a esses problemas.
1. Para solicitar alterações, um usuário DEVERIA registrar um problema no rastreador de problemas da Plataforma do projeto.
1. O usuário ou o Colaborador DEVERIA registar descrevendo o problema que enfrentam ou observam.
1. O usuário ou o Colaborador DEVERIA buscar consenso sobre a precisão de suas observações e o valor de resolver o relato.
1. Os usuários NÃO DEVERIAM registrar solicitações de recursos, idéias, sugestões ou quaisquer soluções para problemas que não estão explicitamente documentados ou são prováveis.
1. Assim, o histórico de lançamento do projeto DEVERÁ ser uma lista de probelmas significativos registrados e resolvidos.
1. Para trabalhar em um problema, um Colaborador DEVERÁ clonar localmente o branch master do projeto e, em seguida, trabalhar nele.
1. Os Colaboradores DEVERÃO fatiar o problema para que sejam resolvidos em pequenos patchs para que sejam integrados ao menos uma vez ao dia.
1. Os Colaboradores DEVERÃO programar em pares na resolução dos problemas.
1. Para integrar um patch ao branch master do repositório remoto, o Colaborador DEVERÁ se assegurar que ele está correto antes de realizar a integração. Em caso de dificuldade, um Mantenedor DEVERÁ auxiliar no processo.
1. A partir do branch master, outros colaboradores PODERÃO revisar, testar ou corrigir o patch. 
1. O projeto é de propriedade coletiva, portanto, todos DEVERÃO ser reposáveis e zelar por sua qualidade.
1. Os Mantenedores DEVERÃO verificar constantemente o repositório e excluir os patchs incorretos rapidamente.
1. Os Mantenedores PODERÃO manter os patchs incorretos de outros Colaboradores com os objetivos de (a) terminar discussões infrutíferas, (b) capturar patchs tóxicos no registro histórico, (c) se envolver com o Colaborador na melhoria da qualidade de seu patch.
1. O usuário que registrou um problema DEVERIA encerrá-lo depois de verificar se o patch foi bem-sucedido.
1. Qualquer Colaborador que tenha julgamentos de valor em um patch DEVERIA expressá-los através de seus próprios patchs.
1. Os Mantenedores DEVERIAM fechar problemas de usuários que são deixados abertos sem ação por um período desconfortável.

### 2.5. Branches e Releases
1. O projeto DEVERÁ ter apenas o branch ("master") que sempre contém a versão mais recente em progresso e DEVERIA sempre passar nos testes de build.
1. Os Colaboradores PODERÃO ter branchs privados locais.
1. Para fazer uma versão estável, um Mantenedor DEVERÁ aplicar uma tag no branch master. Os lançamentos estáveis sempre DEVERÃO ser liberados do branch master.

### 2.6. Evolução de Contratos Públicos
1. Todos os Contratos Públicos (APIs ou protocolos) DEVERÃO ser documentados.
1. Todos os Contratos Públicos DEVERIAM ter espaço para extensibilidade e experimentação.
1. Um patch que modifica um Contrato Público estável NÃO DEVERIA quebrar os aplicativos existentes, a menos que exista um consenso primordial sobre o valor de fazer isso.
1. Um patch que apresenta novos recursos DEVERIA fazê-lo usando novos nomes (um novo contrato).
1. Novos contratos DEVERIAM ser marcados como "rascunho" até serem estáveis e usados por usuários reais.
1. Os contratos antigos DEVERIAM se tornar obsoletos de forma sistemática, marcando-os como "obsoletos" e substituindo-os por novos contratos, conforme necessário.
1. Após tempo suficiente, os antigos contratos obsoletos DEVERIAM ser removidos.
1. Os antigos nomes NÃO DEVERÃO serão reutilizados por novos contratos.

### 2.7. Administração do Projeto
1. Um novo Colaborador que faz patchs corretos, que compreende claramente os objetivos do projeto, e o processo DEVERIA ser convidado a se tornar um Mantenedor.
1. Os Administradores DEVERIAM remover os Mantenedores que estão inativos por um longo período de tempo ou que repetidamente não conseguem aplicar esse processo com precisão.
1. Os Administradores DEVERIAM bloquear ou proibir "atores ruins" que causam estresse e dor aos outros no projeto. Isso deveria ser feito após a discussão pública, com a chance de todas as partes falarem. Um ator ruim é alguém que ignora repetidamente as regras e a cultura do projeto, que é desnecessariamente argumentativo ou hostil, ou que é ofensivo e que não consegue auto-corrigir seu comportamento quando solicitado por outros.
