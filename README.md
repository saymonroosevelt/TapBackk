# TapBack

Landing page e quiz de diagnóstico do TapBack — solução em desenvolvimento
para recuperar ligações perdidas e mensagens de WhatsApp sem resposta.

Site publicado: https://tapbackoficial.netlify.app

## Estrutura

| Arquivo     | Função                                                                           |
|-------------|-----------------------------------------------------------------------------------|
| `index.html`| Landing page (hero, benefícios, como funciona, planos, FAQ, privacidade)          |
| `quiz.html` | Quiz de diagnóstico com 5 perguntas que recomenda um plano                        |

## Como funciona

- O quiz é 100% client-side: as respostas não são enviadas a nenhum servidor.
- Ao finalizar, o quiz redireciona para
  `index.html?origem=quiz&plano=X&q1=...&q5=...#planos`.
- A landing page lê os parâmetros, exibe o diagnóstico, destaca o plano
  recomendado e monta as mensagens pré-preenchidas do WhatsApp (wa.me).
- Todo o CSS e o JavaScript estão embutidos nos próprios HTML —
  sem dependências externas e sem processo de build.

## Planos

| Plano        | Preço      | Destaques                                                   |
|--------------|------------|--------------------------------------------------------------|
| Essencial    | R$ 97/mês  | Ligações perdidas, até 50 oportunidades/mês                  |
| Profissional | R$ 197/mês | + WhatsApp sem resposta, até 200 oportunidades/mês           |
| Empresarial  | R$ 397/mês | + até 600 oportunidades/mês, 3 números, suporte prioritário  |

## Publicação

Site estático publicado na Netlify, servido diretamente da raiz do
repositório (`index.html` é a entrada). Não há build.

## Observações

- Meta Pixel e API de Conversões ainda não estão implementados nesta versão.
- Não há Netlify Functions nesta versão.
- As respostas do quiz transitam apenas pela URL, conforme documentado na
  seção de privacidade da própria página.
