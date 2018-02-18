# Contrato de Construção de Código Coletivo Tupiniquim 

## Abstrato
O C4T fornece um processo padrão para contribuir, avaliar e discutir melhorias em projetos de software. Ele define requisitos técnicos específicos para projetos como um guia de estilo, testes de unidade git plataformas similares. Ele também estabelece personagens diferentes para projetos, com tarefas claras e distintas. C4T especifica um processo para documentar e discutir questões, incluindo busca de consenso e descrições claras, uso de "requisição de merge" e revisões sistemáticas.

## Língua
As palavras-chave "DEVE", "NÃO DEVE", "DEVERÁ", "NÃO DEVERIA", "REQUERIDO", "DEVERIAM", "NÃO DEVERIAM", "RECOMENDADO" e "OPCIONAL" neste documento são para ser interpretado como descrito na RFC 2119.

## 1. Objetivos
O C4T destina-se a fornecer um modelo de colaboração ideal reutilizável para projetos de software de código aberto. Tem esses objetivos específicos:
1. Para maximizar a escala e a diversidade da comunidade em torno de um projeto, reduzindo a fricção para novos Colaboradores e criando um modelo de participação escalonado com fortes feedbacks positivos;
1. Para aliviar as dependências em indivíduos-chave, separando diferentes conjuntos de habilidades para que haja um pool maior de competências em qualquer domínio requerido;
1. Permitir que o projeto se desenvolva de forma mais rápida e precisa, aumentando a diversidade do processo de tomada de decisão;
1. Apoiar o ciclo de vida natural das versões do projeto, desde o experimento até o estável, permitindo experiências seguras, falhas rápidas e isolamento de código estável;
1. Para reduzir a complexidade interna dos repositórios de projetos, facilitando assim a participaço dos Colaboradores e reduzindo a margem de erro;
1. Forçar a apropriação coletiva do projeto, o que aumenta o incentivo econômico aos Contribuintes e reduz o risco de seqüestro por entidades hostis.

## 2. Design
### 2.1. Preliminares
1. O projeto DEVERÁ usar o sistema de controle de revisão distribuído git.
1. O projeto DEVERÁ ser hospedado em gitlab corporativo ou equivalente, aqui chamado "Plataforma".
1. O projeto DEVERÁ usar o rastreador de problemas da Plataforma.
1. O projeto DEVERÁ ter diretrizes claramente documentadas para o estilo de código.
1. Um "Colaborador" é uma pessoa que, por meio de uma "requisição de merge", deseja fornecer um patch sendo um conjunto de commits que resolvem algum problema claramente identificado.
1. Um "Mantenedor" é uma pessoa que combina os patches com o projeto. Os Mantenedores não são desenvolvedores; seu trabalho é fazer cumprir o processo.
1. Os Mantenedores DEVERÃO ter acesso ao branch master, aqui chamado de "Repositório".
1. Contribuidores NÃO DEVERÃO ter acesso ao repositório, a menos que também sejam Mantenedores.
1. Todos, sem distinção ou discriminação, DEVEM ter o mesmo direito de se tornar um Contribuidor nos termos deste contrato.

### 2.2. Licenciamento e propriedade
1. O projeto DEVERÁ usar uma licença compartilhada, como o MPLv2, ou uma variante GPLv3 (GPL, LGPL, AGPL).
1. Todas as contribuições para o código-fonte do projeto ("patches") DEVERÃO usar a mesma licença que o projeto.
1. Todos os patches são propriedade de seus autores. NÃO TERÁ qualquer processo de atribuição de direitos autorais.
1. Cada colaborador será responsável por se identificar na lista de colaboradores do projeto.

### 2.3. Requisitos do patch
1. Mantenedores e Colaboradores DEVEM ter uma conta da Plataforma e DEVEM usar seus nomes reais ou um apelido bem conhecido.
1. Um patch DEVE ser uma resposta mínima e precisa para exatamente um problema identificado e acordado.
1. Um patch DEVE respeitar as diretrizes de estilo de código do projeto se estas forem definidas.
1. Um patch DEVE respeitar as diretrizes de "Evolução de Contratos Públicos" definidas abaixo.
1. Um patch NÃO DEVE incluir código não trivial de outros projetos, a menos que o Contribuinte seja o autor original desse código.
1. Um patch DEVE compilar de forma limpa e passar nos auto-testes do projeto ao menos para a principal plataforma de destino.
1. Uma mensagem de commit de patch DEVE ser composta por uma única linha curta (menos de 50 caracteres) informando o problema sendo resolvido, uma linha em branco seguida da solução proposta, uma linha em brando e a relação de Colaboradores e suas participações no patch.
1. Um "Correto Patch" é aquele que satisfaz os requisitos acima.

### 2.4. Processo de desenvolvimento
1. A mudança no projeto será regida pelo padrão de identificar com precisão problemas e aplicar soluções mínimas e precisas a esses problemas.
1. Para solicitar alterações, um usuário DEVE registrar um problema no rastreador de problemas de plataforma do projeto.
1. O usuário ou colaborador DEVE escrever o problema descrevendo o problema que enfrentam ou observam.
1. O usuário ou colaborador DEVE buscar consenso sobre a precisão de suas observações e o valor de resolver o problema.
1. Os usuários NÃO devem registrar solicitações de recursos, idéias, sugestões ou quaisquer soluções para problemas que não estão explicitamente documentados e prováveis.
1. Assim, o histórico de lançamento do projeto será uma lista de problemas significativos registrados e resolvidos.
1. Para trabalhar em um problema, um colaborador DEVE FORQUER o repositório do projeto e, em seguida, trabalhar em seu repositório bifurcado.
1. Para enviar um patch, um colaborador DEVERÁ criar um pedido de puxar Plataforma para o projeto.
1. Um colaborador NÃO deve confirmar alterações diretamente no projeto.
1. Se a Plataforma implementar solicitações de pull como problemas, um Contributor MAY envia diretamente uma solicitação de puxar sem registrar uma questão separada.
1. Para discutir um patch, as pessoas podem comentar o pedido de tração Platform, no commit ou em outro lugar.
1. Para aceitar ou rejeitar um patch, um Maintainer DEVE usar a interface Platform.
1. Os fabricantes não devem fundir seus próprios patches, exceto em casos excepcionais, como a falta de capacidade de resposta de outros Maintainers por um período prolongado (mais de 1-2 dias).
1. Os responsáveis não devem fazer julgamentos de valor nos patches corretos.
1. Maintainers deve combinar corretamente os patches de outros contribuidores rapidamente.
1. Os responsáveis podem combinar patches incorretos de outros Colaboradores com os objetivos de (a) terminar discussões infrutíferas, (b) capturar manchas tóxicas no registro histórico, (c) se envolver com o Colaborador na melhoria da qualidade de seu patch.
1. O usuário que criou um problema DEVE encerrar o problema depois de verificar o patch foi bem-sucedido.
1. Qualquer colaborador que tenha julgamentos de valor em um patch DEVE expressá-los através de seus próprios patches.
1. Os operadores devem fechar problemas de usuários que são deixados abertos sem ação por um período desconfortável.

### 2.5. Sucursais e lançamentos
1. O projeto DEVE ter uma filial ("mestre") que sempre contém a versão mais recente em progresso e DEVE sempre construir.
1. O projeto NÃO deve usar sucursais tópicos por qualquer motivo. As garfos pessoais podem usar filiais tópicos.
1. Para fazer uma versão estável, um Maintainer deve marcar o repositório. Os lançamentos estáveis ​​sempre serão liberados do mestre do repositório.

### 2.6. Evolução de Contratos Públicos
1. Todos os Contratos Públicos (APIs ou protocolos) DEVEM ser documentados.
1. Todos os contratos públicos DEVEM ter espaço para extensibilidade e experimentação.
1. Um patch que modifica um Contrato público estável NÃO deve quebrar os aplicativos existentes, a menos que exista um consenso primordial sobre o valor de fazer isso.
1. Um patch que apresenta novos recursos DEVE fazê-lo usando novos nomes (um novo contrato).
1. Novos contratos DEVEM ser marcados como "rascunho" até serem estáveis ​​e usados ​​por usuários reais.
1. Os contratos antigos DEVEM ser obsoletos de forma sistemática, marcando-os como "obsoletos" e substituindo-os por novos contratos, conforme necessário.
1. Quando o tempo foi suficiente, os antigos contratos obsoletos DEVEM ser removidos.
1. Os antigos nomes NÃO serão reutilizados por novos contratos.

### 2.7. Administração do Projeto
1. Os fundadores do projeto devem atuar como Administradores para gerenciar o conjunto de projetos do Maintainers.
1. Os Administradores DEVEM garantir sua própria sucessão ao longo do tempo, promovendo os Manutenção mais efetivos.
1. Um novo Colaborador que faz correções corretas, que compreende claramente os objetivos do projeto, e o processo DEVE ser convidado a se tornar um Maintainer.
1. Os administradores DEVEM remover os usuários que estão inativos por um longo período de tempo ou que repetidamente não conseguem aplicar esse processo com precisão.
1. Os administradores DEVEM bloquear ou proibir "atores ruins" que causam estresse e dor aos outros no projeto. Isso deve ser feito após a discussão pública, com a chance de todas as partes falarem. Um ator ruim é alguém que ignora repetidamente as regras e a cultura do projeto, que é desnecessariamente argumentativo ou hostil, ou que é ofensivo e que não consegue auto-corrigir seu comportamento quando solicitado por outros.
