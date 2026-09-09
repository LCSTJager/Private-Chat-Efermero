# Chat Efêmero

Chat ponto-a-ponto (P2P) entre duas pessoas, com visual inspirado em terminal/CMD. Nada fica salvo — quando a sessão termina, a conversa desaparece.

## Como funciona

- Conexão direta entre os dois participantes via **WebRTC** — as mensagens trafegam de navegador para navegador, sem passar pelo servidor.
- `server.js` roda um relay de sinalização em Node.js/WebSocket, usado só para as duas pontas se encontrarem e abrirem a conexão P2P. Ele não lê nem armazena o conteúdo das mensagens.
- Sem histórico e sem banco de dados: encerrou a sessão, a conversa some.
- Sem instalação — roda direto no navegador.
- Interface com visual de terminal/CMD.
- Botão de pânico: esconde o chat instantaneamente e disfarça a página como `about:blank`.

## Stack

- **Frontend:** HTML/JS puro (`index.html`)
- **Backend:** Node.js + WebSocket (`ws`) — relay de sinalização WebRTC (`server.js`)
- Requer Node.js >= 18

## Rodando localmente

```bash
npm install
npm start
```

Depois abra `index.html` no navegador para iniciar uma sessão.

## Motivação

Projeto pessoal para explorar comunicação P2P (WebRTC) e arquitetura de sinalização sem persistência de dados, priorizando privacidade por design desde a concepção.

## Status

Em desenvolvimento ativo.
