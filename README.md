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
1. O projeto DEVERÁ usar o rastreador de relatos da Plataforma.
1. O projeto DEVERÁ ter diretrizes claramente documentadas para o estilo de código.
1. Um "Colaborador" é uma pessoa que, por meio de uma "requisição de merge", deseja fornecer um patch sendo um conjunto de commits que resolvem algum relato claramente identificado.
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
1. Um patch DEVE ser uma resposta mínima e precisa para exatamente um relato identificado e acordado.
1. Um patch DEVE respeitar as diretrizes de estilo de código do projeto se estas forem definidas.
1. Um patch DEVE respeitar as diretrizes de "Evolução de Contratos Públicos" definidas abaixo.
1. Um patch NÃO DEVE incluir código não trivial de outros projetos, a menos que o Contribuinte seja o autor original desse código.
1. Um patch DEVE compilar de forma limpa e passar nos auto-testes do projeto ao menos para a principal plataforma de destino.
1. Uma mensagem de commit de patch DEVE ser composta por uma única linha curta (menos de 50 caracteres) informando o relato sendo resolvido, uma linha em branco seguida da solução proposta, uma linha em brando e a relação de Colaboradores e suas participações no patch.
1. Um "Correto Patch" é aquele que satisfaz os requisitos acima.

### 2.4. Processo de desenvolvimento
1. A mudança no projeto DEVERÁ ser regida pelo padrão de identificar com precisão relaos e aplicar soluções mínimas e precisas a esses relatos.
1. Para solicitar alterações, um usuário DEVERIA registrar um relato no rastreador de problemas da Plataforma do projeto.
1. O usuário ou o Colaborador DEVERIA registar descrevendo o relato que enfrentam ou observam.
1. O usuário ou o Colaborador DEVERIA buscar consenso sobre a precisão de suas observações e o valor de resolver o relato.
1. Os usuários NÃO DEVERIAM registrar solicitações de recursos, idéias, sugestões ou quaisquer soluções para problemas que não estão explicitamente documentados e prováveis.
1. Assim, o histórico de lançamento do projeto DEVERÁ ser uma lista de relatos significativos registrados e resolvidos.
1. Para trabalhar em um relatos, um Colaborador DEVERÁ criar um branch do branch master do projeto e, em seguida, trabalhar em seu branch privado.
1. Para enviar um patch, um Colaborador DEVERÁ criar uma requisição de merge da Plataforma para o projeto.
1. Um Colaborador NÃO DEVERÁ commitar alterações diretamente no branch master do projeto.
1. Para discutir um patch, as pessoas podem comentar a requisição de merge da Platforma, no commit ou em outro lugar.
1. Para aceitar ou rejeitar um patch, um Mantenedor DEVERÁ usar a interface Platforma.
1. Os Mantenedores NÃO DEVERÃO fundir seus próprios patches, exceto em casos excepcionais, como a falta de capacidade de resposta de outros Mantenedores por um período prolongado (mais de 1-2 dias).
1. Os Mantenedores NÃO DEVERÃO fazer julgamentos de valor nos patches corretos.
1. Os Mantenedores DEVERÃO fazer o merge corretamente dos patches de outros Contribuidores rapidamente.
1. Os Mantenedores PODERÃO fazer merge de patches incorretos de outros Colaboradores com os objetivos de (a) terminar discussões infrutíferas, (b) capturar patches tóxicos no registro histórico, (c) se envolver com o Colaborador na melhoria da qualidade de seu patch.
1. O usuário que registrou um relato DEVERIA encerrá-lo depois de verificar se o patch foi bem-sucedido.
1. Qualquer Colaborador que tenha julgamentos de valor em um patch DEVERIA expressá-los através de seus próprios patches.
1. Os Mantenedores DEVERIAM fechar problemas de usuários que são deixados abertos sem ação por um período desconfortável.

### 2.5. Branches e lançamentos
1. O projeto DEVERÁ ter um branch ("master") que sempre contém a versão mais recente em progresso e DEVERIA sempre passar nos testes de build.
1. Os branchs privados DEVERÃO sobreviver apenas ao pequeno período do processo de requisição de merge, devendo ser excluídos ao final do processo. 
1. Para fazer uma versão estável, um Mantenedor DEVERÁ aplicar uma tag no repositório. Os lançamentos estáveis sempre DEVERÃO ser liberados do branch master.

### 2.6. Evolução de Contratos Públicos
1. Todos os Contratos Públicos (APIs ou protocolos) DEVERÃO ser documentados.
1. Todos os Contratos Públicos DEVERIAM ter espaço para extensibilidade e experimentação.
1. Um patch que modifica um Contrato Público estável NÃO DEVERIA quebrar os aplicativos existentes, a menos que exista um consenso primordial sobre o valor de fazer isso.
1. Um patch que apresenta novos recursos DEVERIA fazê-lo usando novos nomes (um novo contrato).
1. Novos contratos DEVERIAM ser marcados como "rascunho" até serem estáveis e usados por usuários reais.
1. Os contratos antigos DEVERIAM se tornar obsoletos de forma sistemática, marcando-os como "obsoletos" e substituindo-os por novos contratos, conforme necessário.
1. Após tempo suficiente, os antigos contratos obsoletos DEVERIAM ser removidos.
1. Os antigos nomes DEVERÃO serão reutilizados por novos contratos.

### 2.7. Administração do Projeto
1. Os fundadores do projeto DEVERÃO atuar como Administradores para gerenciar o conjunto de projetos dos Mantenedores.
1. Os Administradores DEVERÃO garantir sua própria sucessão ao longo do tempo, promovendo os Mantenedores mais efetivos.
1. Um novo Colaborador que faz patchs corretos, que compreende claramente os objetivos do projeto, e o processo DEVERIA ser convidado a se tornar um Mantenedor.
1. Os Administradores DEVERIAM remover os Mantenedores que estão inativos por um longo período de tempo ou que repetidamente não conseguem aplicar esse processo com precisão.
1. Os Administradores DEVERIAM bloquear ou proibir "atores ruins" que causam estresse e dor aos outros no projeto. Isso deveria ser feito após a discussão pública, com a chance de todas as partes falarem. Um ator ruim é alguém que ignora repetidamente as regras e a cultura do projeto, que é desnecessariamente argumentativo ou hostil, ou que é ofensivo e que não consegue auto-corrigir seu comportamento quando solicitado por outros.
