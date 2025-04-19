# Campeonato-Brasileiro-de-2024

API REST simples para consulta e gerenciamento da tabela do Brasileirão Série A 2024 + referência ao Minicurso de NodeJS – Backend com JavaScript (Hashtag Programação).

---

## Sobre o curso

Fiz esta API acompanhando o curso gratuito da Hashtag Programação, que ensina a criar um backend completo em JavaScript com Node.js, desde conceitos teóricos até uma Web API funcional.

### Aulas:  
1. Aula 1 – Crie um Backend com JavaScript  
2. Aula 2 – Construindo uma Web API – Requisições HTTP  
3. Aula 3 – Construindo uma WebAPI – Códigos de Status HTTP  
4. Aula 4 – Construindo uma WebAPI – Requisição do tipo PUT  
5. Aula 5 – Construindo uma WebAPI – Métodos POST e DELETE  
6. Aula 6 – Construindo uma WebAPI – Tratamento de Erros :contentReference[oaicite:2]{index=2}

---

## API Brasileirão Série A 2024

### Visão Geral  
Aplicação construída com Node.js e Express, oferecendo endpoints REST para listar, buscar, adicionar, atualizar e remover clubes da tabela :contentReference[oaicite:3]{index=3}. Utiliza ES Modules habilitados via `"type": "module"` no `package.json` :contentReference[oaicite:4]{index=4} e `"type": "module"` define o formato de módulos no Node.js :contentReference[oaicite:5]{index=5}.

### Roteiros da API

| Método | Endpoint  | Descrição                                  | Resposta                       |
| ------ | --------- | ------------------------------------------ | ------------------------------ |
| GET    | `/`       | Retorna lista completa de times            | 200 OK                         |
| GET    | `/:sigla` | Retorna dados de um time pela sigla        | 200 OK / 404 Not Found         |
| POST   | `/`       | Adiciona um novo time                      | 201 Created / 400 Bad Request  |
| PUT    | `/:sigla` | Atualiza dados de um time existente        | 200 OK / 400 Bad Request / 404 |
| DELETE | `/:sigla` | Remove um time da tabela                   | 200 OK / 404 Not Found         |

### Código de Exemplo  
O servidor é iniciado em `app.js` seguindo o exemplo básico de “Hello World” da documentação oficial do Express :contentReference[oaicite:6]{index=6}, e usa middleware mínimo para roteamento e tratamento de requisições :contentReference[oaicite:7]{index=7}.

### Modelo de Dados  
O arquivo `tabela.js` exporta um array `tabela2024` com objetos contendo:  
- `nome` (string)  
- `sigla` (string de 3 caracteres)  
- `pontos`, `vitorias`, `empates`, `derrotas`, `golsMarcados`, `golsSofridos`, `saldoGols` (números)  

### Validação  
As rotas `POST` e `PUT` usam Joi para validar payloads:  
- `modeloTime`: exige `nome` (mínimo 4 caracteres) e `sigla` (3 caracteres); define defaults zero nos campos numéricos :contentReference[oaicite:8]{index=8}.  
- `modeloAtualizacaoTime`: permite atualização parcial (mínimo 1 campo) com valores numéricos ≥ 0 :contentReference[oaicite:9]{index=9}.

### Instalação e Execução

1. Clone o repositório  
