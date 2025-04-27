# Campeonato-Brasileiro-de-2024

API REST simples em Node.js/Express para gerenciar a tabela da Série A 2024.  
Criada acompanhando minicurso Hashtag Programação (Aulas 1–6).

## Tecnologias  
Node.js, Express, Joi  

## Instalação  
1. git clone https://github.com/JorgeALDev/Campeonato-Brasileiro-de-2024
2. cd Campeonato-Brasileiro-de-2024  
3. npm install  
4. npm start  

## Endpoints  
GET    /          → lista todos os clubes  
GET    /:sigla    → dados de um clube (200/404)  
POST   /          → cria clube (201/400)  
PUT    /:sigla    → atualiza clube (200/400/404)  
DELETE /:sigla    → remove clube (200/404)  

## Modelo de Dados  
{ nome, sigla (3 chars), pontos, vitorias, empates, derrotas, golsMarcados, golsSofridos, saldoGols }  

## Validação  
Usa Joi:  
- nome ≥ 4 chars  
- sigla = 3 chars  
- campos num ≥ 0  

## License  
MIT  

## References  
- Hashtag Programação – Minicurso NodeJS Backend (Aulas 1–6) 
