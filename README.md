# MovieFinder

Buscador de filmes com frontend em HTML/CSS/JS e backend em .NET 10.

A API key do TMDB fica protegida no backend via user-secrets — nunca exposta no cliente.

## Tecnologias

- **Backend:** .NET 10 Web API, HttpClient, injeção de dependência, Scalar (docs)
- **Frontend:** HTML, CSS e JavaScript puro
- **API:** [The Movie Database (TMDB)](https://www.themoviedb.org/)

## Como rodar localmente

### Pré-requisitos
- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- Conta gratuita no [TMDB](https://www.themoviedb.org/) para pegar a API key
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) para o frontend

### Backend

```bash
cd backend/MovieFinder.API
dotnet user-secrets init
dotnet user-secrets set "Tmdb:ApiKey" "SUA_KEY_AQUI"
dotnet run
```

A API sobe em `http://localhost:5000`.
Documentação interativa em `http://localhost:5000/scalar/v1`.

### Frontend

Abra o `frontend/index.html` com o Live Server do VS Code.

## Endpoints

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/api/movies/search?q={termo}&page={n}` | Busca filmes por nome |
| GET | `/api/movies/{id}` | Detalhes completos de um filme |
