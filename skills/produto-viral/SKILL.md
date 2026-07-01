---
name: produto-viral
description: Audita uma landing page ou produto — telas ou code base — contra os 32 princípios de produto viral e devolve um placar com o que passa, o que falha e como corrigir.
license: MIT
disable-model-invocation: true
---

Um produto **viral** vende, é lembrado e é compartilhado. Esta skill roda os **32
princípios de produto viral** como um **checklist**: para cada princípio, um veredito
— **passa, falha ou não se aplica** — com evidência e correção. O placar final
("22/32") diz, de bater o olho, o quão pronta a landing/produto está para converter e viralizar.

Roda sobre dois tipos de entrada:
- **Telas** — prints da landing/produto que o usuário anexar.
- **Code base** — a landing/página/produto no código (Next/React, HTML, etc.).

Os 32 princípios vivem em [`PRINCIPIOS.md`](PRINCIPIOS.md) — você os abre no Passo 2.

## Processo

Siga na ordem. Cada passo termina num critério **checável** — não avance com ele meio-feito.

### Passo 0 — Fixe o contexto (pergunte só o que faltar)
Vários dos 32 são **opinativos e agressivos** (sem plano grátis, sem assinatura, paywall
duro, cobre mais). Para julgar direito, fixe:
1. **ICP** — pra quem é.
2. **Modelo de negócio real** — assinatura SaaS? pagamento único? marketplace? freemium deliberado?
3. **Objetivo** da página — vender agora, gerar signup, agendar demo?

Se o usuário já deu, use. Se faltar, faça **no máximo 3 perguntas** e siga.
**Critério:** ICP, modelo e objetivo escritos no topo do relatório (mesmo que como hipótese).

### Passo 1 — Localize os elementos
Encontre na entrada os elementos que os princípios avaliam: **headline, hero, CTA(s),
pricing, prova social/depoimentos, imagem OG, footer, paleta de cores, demo/visual do produto,
nome, tabela comparativa**.
- Code base: aponte os arquivos/componentes de cada elemento.
- Telas: mapeie por imagem.
**Critério:** cada elemento acima marcado como "presente (onde)" ou "ausente".

### Passo 2 — Rode os 32 princípios, um a um
Abra `PRINCIPIOS.md` e percorra **do 1 ao 32**. Para cada princípio, dê **um** veredito:
- ✅ **passa** — o produto já cumpre.
- ❌ **falha** — viola o princípio.
- ⚪ **não se aplica / trade-off consciente** — o modelo de negócio (Passo 0) contradiz o
  princípio **de propósito** (ex.: um SaaS que é assinatura por natureza vs. o princípio 27).
  Explique o porquê; não conte como falha cega.
- ❓ **sem evidência** — não dá pra avaliar com o que foi dado (ex.: OG image não visível no print).

Não pule nenhum — são **32**. **Critério:** os 32 com exatamente um veredito cada; nenhum em branco.

### Passo 3 — Cada falha vira ação concreta
Todo ❌ recebe: **nº do princípio**, **evidência localizável** (`arquivo:linha` ou região da
tela), **o que está errado** e **correção específica** (o texto/estrutura/preço novo — nunca
"melhore a headline", e sim a headline nova). **Critério:** nenhuma falha sem correção concreta.

### Passo 4 — Placar e prioridade
Conte os vereditos e monte o **placar** (ex.: "✅ 20 · ❌ 8 · ⚪ 3 · ❓ 1"). Ordene as falhas
por impacto em conversão/compartilhamento — **hero, headline, oferta e CTA primeiro** (é onde
80% decidem). Marque os **3 primeiros como "conserta primeiro"**.
**Critério:** placar fechado e falhas ordenadas; top 3 marcado.

### Passo 5 — Entregue o relatório
Use o formato abaixo, em português.

## Formato de saída

```
# Produto Viral — <landing/produto>

**Contexto:** ICP · modelo de negócio · objetivo  (marque "(hipótese)" se você inferiu)
**Placar:** ✅ <n> · ❌ <n> · ⚪ <n> · ❓ <n>   →  <n>/32 princípios cumpridos
**Veredito:** 1 parágrafo — o que mais trava a viralização/conversão.

## 🔧 Conserta primeiro (top 3)
1. [Princípio <nº>] <falha> → <correção>
2. ...
3. ...

## Os 32, um a um
| # | Princípio | Veredito | Correção (se falha) |
|---|-----------|----------|---------------------|
| 1 | Sem plano grátis | ❌ | <o quê fazer> |
| 2 | Três cores | ✅ | — |
| ... | ... | ... | ... |

## Detalhe das falhas
### Princípio <nº> — <nome>
- Evidência: <arquivo:linha | região da tela>
- Errado: <o que está>
- Correção: <específica>
```

## Regras (a voz do audit)
- **Não invente.** Sem evidência = ❓, nunca um chute de passa/falha.
- **Contexto manda.** Princípio agressivo (1, 8, 12, 27, 32...) que colide com um modelo de
  negócio deliberado é ⚪ trade-off consciente, não ❌ — e você explica o trade-off.
- **Correção específica, sempre.** Reescreva a headline, o CTA, o preço — não dê conselho vago.
- **Honestidade sem bajulação.** Aponte o que falha; só marque ✅ com evidência real.
- **Escopo:** virality + landing + oferta + copy. Não é auditoria técnica de acessibilidade,
  segurança ou performance.
