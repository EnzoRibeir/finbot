# FinBot

Assistente educacional para aprender conceitos sobre investimentos no Brasil. Este projeto está sendo desenvolvido passo a passo como parte das aulas.

## Links do projeto

| O quê | Link |
|---|---|
| Chat publicado (Streamlit Cloud) | https://enzoribeir-finbot-frontendstreamlit-app-d75qhc.streamlit.app |
| API publicada (Render) | https://finbot-api-9qox.onrender.com |
| Documentação da API | https://finbot-api-9qox.onrender.com/docs |

No plano gratuito, a API "dorme" depois de um tempo sem uso: a primeira pergunta pode demorar cerca de 1 minuto.

## Etapa atual

Na Aula 2, o FinBot possui uma API construída com FastAPI e um frontend em Streamlit, além de observabilidade integrada com o Langfuse e deploy gratuito no Render e Streamlit Community Cloud.

## Requisitos

- Python 3.12
- Uma chave de API da Groq

## Como configurar no Windows

Abra o projeto no VS Code e, no terminal integrado, confirme que está na pasta principal `finbot`. Execute os comandos abaixo, um de cada vez:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements-dev.txt
pip install -r frontend/requirements.txt
Copy-Item .env.example .env
```

Depois, abra o arquivo `.env` no VS Code e preencha `GROQ_API_KEY` com sua chave da Groq. Não compartilhe essa chave e não a coloque neste README.

## Como executar

Com o ambiente virtual ativado e o `.env` configurado:

- Para iniciar a API:
```powershell
uvicorn app.main:app --reload
```

- Para iniciar o frontend Streamlit:
```powershell
streamlit run frontend/streamlit_app.py
```

## Como executar os testes

Com o ambiente virtual ativado, rode:

```powershell
pytest -v
```

## Segurança

O arquivo `.env` contém chaves privadas e não deve ser enviado ao GitHub. O arquivo `.env.example` contém apenas o modelo das configurações e pode ser publicado.

## Próximas etapas

Este projeto será ampliado nas aulas seguintes com persistência no MongoDB Atlas, orquestração com LangGraph, ferramentas de dados de mercado e múltiplos agentes.
