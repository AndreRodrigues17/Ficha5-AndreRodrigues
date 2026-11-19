# Ficha 5 · Cartas novas

App React (client/) com um server Express (server/). O formulário acrescenta cartas, o server guarda-as em server/cartas.json.

## API

Todas as rotas estão em http://localhost:3000.

### GET /api/cartas
Não recebe nada. Responde 200 com a lista de cartas em JSON.

### POST /api/cartas
Recebe um JSON no body com name, type e attack, por exemplo {"name": "Teste", "type": "Criatura", "attack": 3}. O header Content-Type tem de ser application/json.
- 201: a carta foi guardada, e o server devolve-a.
- 400: falta o name ou o type. A carta não é guardada e a resposta é {"error": "Falta o nome ou o tipo"}.

### GET /api/cartas/aleatoria
Não recebe nada. Responde 200 com uma carta escolhida ao acaso.

## Perguntas

### Pergunta 3

O primeiro é o OPTIONS (preflight), mandado pelo browser para perguntar se o server aceita o POST, porque a app e o server estão em origens diferentes. Antes do cors o server não respondia a isso, por isso o POST nunca chegava a ser enviado e o console.log não aparecia.

### Pergunta 4

Só com setCards, a carta estava no React e o F5 apagava-a. No POST sem ficheiro estava no array do server e o reinício apagava-a. Com o cartas.json fica no disco e nada a apaga.