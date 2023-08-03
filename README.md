Checklist Tarefa1 - familiarização com o codigo atual e suas tecnologias:


[ ] Tarefa 1: Estudar o funcionamento do protótipo PvP e ver como está implementado o fluxo, as interações entre os sistemas (Client, API, Open Match, Agones, Game Server)

[ ] 1.1 Acessar o protótipo PvP e explorar as suas funcionalidades

    acessado, explorado

[ ] 1.2 Ler a documentação do protótipo PvP e entender a sua arquitetura
    
    Lido e entendido

[ ] 1.3 Estudar o código-fonte do Client e ver como ele se comunica com a API

    Estudado, Visto

[ ] 1.4 Estudar o código-fonte da API e ver como ela se comunica com o Open Match, o Agones e o Game Server
    Em andamento

[ ] 1.5 Estudar o código-fonte do Open Match e ver como ele faz o matchmaking dos jogadores

    Em andamento

    O Open Match é um framework de matchmaking de código aberto que lida com o gerenciamento de infraestrutura para desenvolvedores de jogos, tudo isso enquanto lhes dá controle sobre sua lógica de correspondência. Quando um jogador deseja entrar em um jogo, um ticket é criado e armazenado no banco de dados do Open Match. Um conceito que chamamos de Diretor chamará o serviço backend para solicitar partidas do Open Match. O Open Match chamará uma função de correspondência, que você fornece, para transformar os tickets em partidas.



[ ] 1.6 Estudar o código-fonte do Agones e ver como ele aloca os servidores de jogo
    em andamento

   

[ ] 1.7 Estudar o código-fonte do Game Server e ver como ele gerencia a lógica de jogo

    o codigo do server cria o objeto player dentro da waiting room, quando nessa sala, fica procurando um jogador disponivel para match, quando encontra ele cria uma play_room e coloca o objeto player e o objeto other_player como child.

    Uma vez dentro de uma play_room (Classe PlayRoom) que gerencia os turnos, contagem de tempo, execução do turno de processamento (processing_turn), filas, distancia do evo mais proximo, etc.. (scr_playroom.gd)



[ ] Tarefa 2: Responder a pergunta: Como funciona o fluxo de telas do Client para o PvP?

    Ao efetuar a validação do login o botão Arena fica disponível e ao pressioná-lo muda pra cena scn_lobby_arena.tsc

    onde vai permanecer até encontrar um oponente, então o servidor vai pedir pro cliente trocar pra cena de arena (load_scene_arena)

    na cena de arena ele irá para duas cenas, vitoria (server emite player_win_battle), derrota (server emite player_lose_battle)

    na cena de vitoria (scn_win_arena) sinaliza a vitoria

    na cena de derrota (scn_lose_arena) sinaliza a derrota


[ ] Tarefa 3: Responder a pergunta: O que acontece após o player conseguir um ticket de matching?



[ ] Tarefa 4: Responder a pergunta: Quais endpoints na API são responsáveis pela gestão do ticket de matching?



[ ] Tarefa 5: Responder a pergunta: Como é feito o match entre dois jogadores, detalhadamente?




[ ] Tarefa 6: Responder a pergunta: Como um jogador sabe as informações do outro?


    


[ ] Tarefa 7: Responder a pergunta: Como é feito o cálculo para definir a distância entre os evos?

    A classe EVO tem um metodo para isso chamado distance que retorna:
        func distance(evo : EVO) -> int:
            var evo_position : int = EvoPosition.get(choosed_position)
            var target_position : int = EvoPosition.get(evo.choosed_position)
            return (target_position * evo_position) - evo_position

    Essa função é utilizada pelo metodo _get_closest_target_alive dento da classe PlayRoom em _get_closest_target_alive .




[ ] Tarefa 8: Responder a pergunta: Como é definido a fila de ataque dos evos?
    A classe PlayRoom tem um metodo para criar essa fila de ataque (_build_attack_queue).
     ele usa os criterios, max_dexterity, min_resistance, max_lethality, max_precision para montar uma array e embaralhar.
     depois ele cria instancias desses evos dentro da $AttackQueue por fim armazena dentro desse Evo atacante sua posição (??????)




[ ] Tarefa 9: Responder as perguntas: Quais serviços da infra utilizam gRPC? Quais serviços da infra utilizam REST? Como é feita a alocação de um Server no Agones? É possível rodar quais sistemas fora do cluster kubernetes? Como?

[ ] 9.1 Explicar o conceito de gRPC e como ele é usado para comunicação entre serviços


    gRPC é um serviço de alto desempenho para atender chamadas RPC (Remote Call Procedures). Ele é uma estrutura de RPC de linguagem independente. O gRPC pode oferecer suporte a load balance, health-check, tracing e autenticação. Ele permite que os clientes especifiquem um tempo máximo para que um RPC seja concluído. Se o prazo especificado for excedido, o servidor pode cancelar a operação independentemente do cliente. O gRPC tem código aberto e pode ser executado em qualquer ambiente.

    O gRPC é uma estrutura moderna de código aberto e alto desempenho criada pelo Google. O gRPC segue amplamente a semântica HTTP sobre HTTP/2 e, assim permite que você use o streaming full-duplex, possibilitando a comunicação entre diferentes sistemas via conexão de rede. A proposta do gRPC é que o cliente interaja com o servidor por meio de chamadas de funções simples, ou seja, de interfaces de códigos geradas automaticamente pela própria aplicação do gRPC. Isso significa que você precisa apenas implementar sua lógica de programação, o que facilita muito a adoção desse recurso.


[ ] 9.2 Explicar o conceito de REST e como ele é usado para comunicação entre serviços


    A Representational State Transfer (REST), em português Transferência de Estado Representacional, é uma abstração da arquitetura da World Wide Web, mais precisamente, é um estilo arquitetural que consiste de um conjunto coordenado de restrições arquiteturais aplicadas a componentes, conectores e elementos de dados dentro de um sistema de hipermídia distribuído.

    No mundo da programação, o conceito de REST (Representational State Transfer) se aplica à construção de Aplicações Web, como softwares e sites, consistindo em um protocolo sobre a Arquitetura da Informação.

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

