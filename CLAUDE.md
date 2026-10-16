# CLAUDE.md

Diretrizes para trabalhar neste repositório.

## Visão geral

TapBack — landing page + quiz de diagnóstico (pt-BR) de um serviço em
desenvolvimento que recupera ligações perdidas e mensagens de WhatsApp
sem resposta. Site 100% estático, publicado na Netlify.

## Comandos

- Não há build, dependências nem testes; o site é servido da raiz.
- Para testar localmente: `python3 -m http.server` na raiz do projeto
  (ou abrir os HTML diretamente no navegador).

## Arquitetura

- `index.html` — landing page. Todo o CSS fica no `<style>` do `<head>`;
  todo o JS fica no `<script>` antes de `</body>`.
  - Lê os parâmetros da URL (`origem=quiz`, `plano`, `q1..q5`) para exibir
    o diagnóstico e destacar o plano recomendado.
  - Monta links `wa.me` pré-preenchidos com o plano escolhido e as
    respostas do quiz (constante `PHONE`).
- `quiz.html` — quiz de 5 perguntas com 3 telas (intro / perguntas /
  resultado), 100% client-side.
  - `choosePlan()` define o plano recomendado (essencial ou profissional)
    a partir das respostas.
  - Redireciona para a landing page com os parâmetros da consulta.

## Convenções

- Todo o conteúdo visível é em português (pt-BR).
- Sem frameworks: CSS puro embutido; paleta escura com fundo
  `#071426`/`#081625` e verde `#39dd96`/`#41e3a2`.
- Preços e recursos dos planos aparecem em DOIS arquivos (`index.html` e
  `quiz.html`) — mantenha os dois sincronizados ao alterar.
- O serviço é apresentado como "em desenvolvimento": o copy não deve
  afirmar disponibilidade do produto.

## Estado atual

- Meta Pixel e API de Conversões: não implementados.
- Netlify Functions: nenhuma.
