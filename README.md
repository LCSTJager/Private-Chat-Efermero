# Chat Efêmero

Chat P2P entre duas pessoas, direto do navegador. Sem instalação, sem conta, sem histórico — fechou a aba, a conversa deixou de existir.

## Como funciona

A conversa acontece por um canal direto via **WebRTC** (`RTCDataChannel`), sem que o conteúdo passe por nenhum servidor. Um pequeno relay de sinalização serve só para apresentar as duas pontas no início — repassa a oferta, a resposta e os candidatos de conexão, e nunca vê o texto das mensagens. Assim que o canal direto abre, o relay já não é necessário.

Para atravessar NATs mais restritivos (rede de operadora, corporativa, etc.), a conexão conta com STUN público e um TURN de retransmissão como plano B.

## Estrutura

```
chat-efemero/
├── client/
│   └── index.html      # cliente único — HTML, CSS e JS, interface estilo terminal
└── server/
    ├── server.js        # relay de sinalização (Node.js + ws)
    └── package.json
```

## Como rodar

1. Entre em: https://lcstjager.github.io/Private-Chat-Efermero/, aguarde o serviço iniciar e envie o código gerado para a outra pessoa

## Funcionalidades

- Geração automática de sala com link único e compartilhável;
- Sessão 100% efêmera — nenhuma mensagem toca disco, banco de dados ou servidor;
- Botão de pânico: oculta o chat inteiro e deixa a tela como uma página em branco (retorno com clique ou `Esc`);
- Interface com identidade visual de terminal, incluindo sequência de boot.

## Stack

WebRTC · Node.js · WebSocket (`ws`) · Render · STUN/TURN (Google / Metered.ca)
