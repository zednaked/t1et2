Checklist Tarefa1 - familiarização com o codigo atual e suas tecnologias:


[ ] Tarefa 1: Estudar o funcionamento do protótipo PvP e ver como está implementado o fluxo, as interações entre os sistemas (Client, API, Open Match, Agones, Game Server)

[ ] 1.1 Acessar o protótipo PvP e explorar as suas funcionalidades

[ ] 1.2 Ler a documentação do protótipo PvP e entender a sua arquitetura

[ ] 1.3 Estudar o código-fonte do Client e ver como ele se comunica com a API

[ ] 1.4 Estudar o código-fonte da API e ver como ela se comunica com o Open Match, o Agones e o Game Server

[ ] 1.5 Estudar o código-fonte do Open Match e ver como ele faz o matchmaking dos jogadores


    O Open Match é um framework de matchmaking de código aberto que lida com o gerenciamento de infraestrutura para desenvolvedores de jogos, tudo isso enquanto lhes dá controle sobre sua lógica de correspondência. Quando um jogador deseja entrar em um jogo, um ticket é criado e armazenado no banco de dados do Open Match. Um conceito que chamamos de Diretor chamará o serviço backend para solicitar partidas do Open Match. O Open Match chamará uma função de correspondência, que você fornece, para transformar os tickets em partidas.



[ ] 1.6 Estudar o código-fonte do Agones e ver como ele aloca os servidores de jogo


   

[ ] 1.7 Estudar o código-fonte do Game Server e ver como ele gerencia a lógica de jogo



[ ] Tarefa 2: Responder a pergunta: Como funciona o fluxo de telas do Client para o PvP?

[ ] 2.1 Descrever as telas do Client e suas funções

[ ] 2.2 Descrever as transições entre as telas e os eventos que as acionam

[ ] 2.3 Descrever os dados que são enviados e recebidos pelo Client em cada tela


[ ] Tarefa 3: Responder a pergunta: O que acontece após o player conseguir um ticket de matching?

[ ] 3.1 Explicar o conceito de ticket de matching e como ele é gerado pelo Open Match

[ ] 3.2 Explicar como o ticket de matching é armazenado na API e como ele é atualizado pelo Open Match

[ ] 3.3 Explicar como o Client consulta o status do ticket de matching e como ele recebe a notificação de match encontrado


[ ] Tarefa 4: Responder a pergunta: Quais endpoints na API são responsáveis pela gestão do ticket de matching?

[ ] 4.1 Listar os endpoints da API relacionados ao ticket de matching e suas rotas

[ ] 4.2 Descrever os parâmetros, os métodos e os retornos de cada endpoint

[ ] 4.3 Descrever a lógica interna de cada endpoint e como eles interagem com o Open Match


[ ] Tarefa 5: Responder a pergunta: Como é feito o match entre dois jogadores, detalhadamente?

[ ] 5.1 Explicar o conceito de match function e como ela é definida pelo Open Match

[ ] 5.2 Explicar o conceito de match profile e como ele é configurado pelo Open Match

[ ] 5.3 Explicar o conceito de match evaluator e como ele é implementado pelo Open Match

[ ] 5.4 Explicar o fluxo de dados entre o Open Match, a API e o Client durante o processo de matchmaking

[ ] Tarefa 6: Responder a pergunta: Como um jogador sabe as informações do outro?

[ ] 6.1 Explicar o conceito de player profile e como ele é criado e armazenado na API

[ ] 6.2 Explicar como o player profile é enviado ao Open Match e como ele é usado no matchmaking

[ ] 6.3 Explicar como o player profile é enviado ao Client e como ele é exibido na tela


[ ] Tarefa 7: Responder a pergunta: Como é feito o cálculo para definir a distância entre os evos?

[ ] 7.1 Explicar o conceito de evo e como ele é representado no Game Server

[ ] 7.2 Explicar o conceito de distância entre os evos e como ela afeta a jogabilidade

[ ] 7.3 Explicar a fórmula matemática usada para calcular a distância entre os evos


[ ] Tarefa 8: Responder a pergunta: Como é definido a fila de ataque dos evos?

[ ] 8.1 Explicar o conceito de fila de ataque e como ela é representada no Game Server

[ ] 8.2 Explicar o conceito de prioridade de ataque e como ela é determinada pelo Game Server

[ ] 8.3 Explicar o algoritmo usado para ordenar os evos na fila de ataque


[ ] Tarefa 9: Responder as perguntas: Quais serviços da infra utilizam gRPC? Quais serviços da infra utilizam REST? Como é feita a alocação de um Server no Agones? É possível rodar quais sistemas fora do cluster kubernetes? Como?

[ ] 9.1 Explicar o conceito de gRPC e como ele é usado para comunicação entre serviços


    gRPC é um serviço de alto desempenho para atender chamadas RPC (Remote Call Procedures). Ele é uma estrutura de RPC de linguagem independente. O gRPC pode oferecer suporte a load balance, health-check, tracing e autenticação. Ele permite que os clientes especifiquem um tempo máximo para que um RPC seja concluído. Se o prazo especificado for excedido, o servidor pode cancelar a operação independentemente do cliente. O gRPC tem código aberto e pode ser executado em qualquer ambiente1.

    O gRPC é uma estrutura moderna de código aberto e alto desempenho criada pelo Google. O gRPC segue amplamente a semântica HTTP sobre HTTP/2 e, assim permite que você use o streaming full-duplex, possibilitando a comunicação entre diferentes sistemas via conexão de rede2. A proposta do gRPC é que o cliente interaja com o servidor por meio de chamadas de funções simples, ou seja, de interfaces de códigos geradas automaticamente pela própria aplicação do gRPC. Isso significa que você precisa apenas implementar sua lógica de programação, o que facilita muito a adoção desse recurso2.


[ ] 9.2 Explicar o conceito de REST e como ele é usado para comunicação entre serviços


    A Representational State Transfer (REST), em português Transferência de Estado Representacional, é uma abstração da arquitetura da World Wide Web, mais precisamente, é um estilo arquitetural que consiste de um conjunto coordenado de restrições arquiteturais aplicadas a componentes, conectores e elementos de dados dentro de um sistema de hipermídia distribuído1.

    No mundo da programação, o conceito de REST (Representational State Transfer) se aplica à construção de Aplicações Web, como softwares e sites, consistindo em um protocolo sobre a Arquitetura da Informação2.

[ ] 9.3 Listar os serviços da infra que utilizam gRPC e os que utilizam REST e justificar as escolhas

[ ] 9.4 Explicar o conceito de Agones e como ele é usado para gerenciar os servidores de jogo


     O Agones é uma plataforma de código aberto criada com base no Kubernetes que conteineriza cargas de trabalho do servidor de jogos e "impulsiona uma adoção mais ampla e mais fácil de paradigmas nativos da nuvem que aumenta a velocidade do desenvolvimento de jogos". A plataforma foi construída com base na tecnologia de computação na nuvem Kubernetes, que são contentores criados para abrir sessões de jogo rapidamente para as partidas.


[ ] 9.5 Explicar o conceito de kubernetes e como ele é usado para orquestrar os serviços da infra

    Kubernetes é um sistema de código aberto para automatizar a implantação, o dimensionamento e o gerenciamento de aplicativos em contêineres. Ele foi projetado para lidar com aplicativos distribuídos em contêineres em escala. Ele funciona agrupando os contêineres que compõem um aplicativo em unidades lógicas para facilitar o gerenciamento e a descoberta.


[ ] 9.6 Explicar como é feita a alocação de um Server no Agones e quais são os requisitos e os benefícios

    O Agones é uma plataforma de código aberto criada com base no Kubernetes que conteineriza cargas de trabalho do servidor de jogos e "impulsiona uma adoção mais ampla e mais fácil de paradigmas nativos da nuvem que aumenta a velocidade do desenvolvimento de jogos". A plataforma foi construída com base na tecnologia de computação na nuvem Kubernetes, que são contentores criados para abrir sessões de jogo rapidamente para as partidas.

    A alocação de servidores no Agones é feita por meio do Kubernetes. O Kubernetes é um sistema de código aberto para automatizar a implantação, o dimensionamento e o gerenciamento de aplicativos em contêineres. Ele foi projetado para lidar com aplicativos distribuídos em contêineres em escala. Ele funciona agrupando os contêineres que compõem um aplicativo em unidades lógicas para facilitar o gerenciamento e a descoberta.

    Os requisitos para usar o Agones incluem ter uma conta do Google Cloud Platform (GCP) e ter conhecimento básico do Kubernetes. Os benefícios incluem escalabilidade, alta disponibilidade e facilidade de uso.


[ ] 9.7 Explicar quais sistemas podem ser rodados fora do cluster kubernetes e como fazer isso


[ ] Tarefa 10: Revisar o relatório, corrigir erros, formatar e preparar a apresentação

Tarefa 2 - em ver

