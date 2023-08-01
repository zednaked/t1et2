Checklist Tarefa1 - familiarização com o codigo atual e suas tecnologias:


[ ] Tarefa 1: Estudar o funcionamento do protótipo PvP e ver como está implementado o fluxo, as interações entre os sistemas (Client, API, Open Match, Agones, Game Server)

[ ] 1.1 Acessar o protótipo PvP e explorar as suas funcionalidades

[ ] 1.2 Ler a documentação do protótipo PvP e entender a sua arquitetura

[ ] 1.3 Estudar o código-fonte do Client e ver como ele se comunica com a API

[ ] 1.4 Estudar o código-fonte da API e ver como ela se comunica com o Open Match, o Agones e o Game Server

[ ] 1.5 Estudar o código-fonte do Open Match e ver como ele faz o matchmaking dos jogadores

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

[ ] 9.2 Explicar o conceito de REST e como ele é usado para comunicação entre serviços

[ ] 9.3 Listar os serviços da infra que utilizam gRPC e os que utilizam REST e justificar as escolhas

[ ] 9.4 Explicar o conceito de Agones e como ele é usado para gerenciar os servidores de jogo

[ ] 9.5 Explicar o conceito de kubernetes e como ele é usado para orquestrar os serviços da infra

[ ] 9.6 Explicar como é feita a alocação de um Server no Agones e quais são os requisitos e os benefícios

[ ] 9.7 Explicar quais sistemas podem ser rodados fora do cluster kubernetes e como fazer isso


[ ] Tarefa 10: Revisar o relatório, corrigir erros, formatar e preparar a apresentação

Tarefa 2 - em ver

