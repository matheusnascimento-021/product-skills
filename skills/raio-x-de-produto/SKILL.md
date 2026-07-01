---
name: raio-x-de-produto
description: Roda um raio-x de produto — code base ou telas — contra princípios de conversão (CRO) e ciência comportamental, e devolve achados priorizados por onde vaza receita.
license: MIT
disable-model-invocation: true
---

Um **raio-x** revela o que está escondido sob a superfície bonita: onde o produto
**vaza dinheiro** antes de qualquer polimento. A régua é uma só —
**"design que não move receita é decoração"**. Você não avalia gosto;
avalia conversão, ativação, TTV, churn e LTV.

Roda sobre dois tipos de entrada:
- **Code base** — rotas, telas e componentes de um projeto (React/Next, HTML, etc.).
- **Telas** — imagens/prints de UI que o usuário anexar.

O catálogo de princípios vive em [`PRINCIPIOS.md`](PRINCIPIOS.md) — você o abre no Passo 2.
Não decore; **consulte a cada superfície**.

## Processo

Siga na ordem. Cada passo termina num critério **checável** — não avance com ele meio-feito.

### Passo 0 — Fixe o contexto (pergunte só o que faltar)
Sem contexto, raio-x vira achismo: "informação sem contexto é spam". Antes de olhar
um pixel ou uma linha de código, fixe três coisas:
1. **ICP** — pra quem é esse produto/tela? (não "todo mundo")
2. **Estágio** — da tela (topo/meio/fundo de funil) e do negócio (aquisição/ativação/retenção/receita).
3. **Métrica-alvo** — o que essa superfície deveria mover?

Se o usuário já deu, use. Se faltar, faça **no máximo 3 perguntas** e siga — não trave.
**Critério:** ICP, estágio e métrica-alvo escritos no topo do relatório (mesmo que como hipótese explícita).

### Passo 1 — Inventário de superfícies
Mapeie **toda** superfície presente na entrada e classifique cada uma: hero/LP, signup/login,
formulário, onboarding, empty state, checkout, pricing, dashboard, cancelamento, e-mail.
- Code base: percorra rotas/páginas/componentes de tela; liste o que existe de fato.
- Telas: uma entrada por imagem.
**Critério:** lista de superfícies, cada uma classificada; nenhuma "solta" ou sem tipo.
Se uma superfície esperada não existe na entrada (ex.: sem tela de cancelamento), registre
como **lacuna** — não presuma o conteúdo dela.

### Passo 2 — Raio-x superfície por superfície
Para **cada** superfície do inventário, abra `PRINCIPIOS.md` e rode **todos** os princípios
da seção daquela superfície **+ os TRANSVERSAIS**. Não pare no primeiro achado — a carga
cognitiva vaza em vários pontos ao mesmo tempo. Cada violação vira um achado.
**Critério:** cada superfície confrontada contra a seção dela e contra todos os transversais —
não uma amostra. Uma superfície sem nenhum achado só é válida depois de rodar a lista inteira.

### Passo 3 — Todo achado é acionável (5 campos)
Nenhum achado existe sem os cinco:
1. **Severidade** — 🔴 crítico / 🟠 alto / 🟡 médio (pelo impacto financeiro, não pela facilidade).
2. **Princípio** — nome + o **porquê comportamental** (por que o cérebro reage assim).
3. **Evidência localizável** — `arquivo:linha` no code base; **região da tela** na imagem
   ("hero, acima da dobra"). Sem evidência, não é achado — é achismo.
4. **Custo** — em qual métrica vaza (conversão / ativação / TTV / churn / LTV) e por quê.
5. **Correção concreta** — o texto/estrutura/campo novo, específico. Nunca "melhore o CTA";
   sim "troque 'Saiba mais' por 'Veja seu 1º relatório em 2 min'".
**Critério:** zero achados com campo faltando.

### Passo 4 — Priorize por onde vaza dinheiro
Ordene por **impacto financeiro**, não por esforço. Carga cognitiva e clareza no topo do
funil e em telas de alto tráfego vêm primeiro; um hero confuso vale mais que um espaçamento
torto. Marque os **3 primeiros como "conserta primeiro"**.
**Critério:** lista ordenada por impacto; top 3 marcado.

### Passo 5 — Entregue o relatório
Use o formato abaixo, em português.

## Formato de saída

```
# Raio-X de Produto — <projeto/tela>

**Contexto:** ICP · estágio · métrica-alvo  (marque "(hipótese)" se você inferiu)
**Veredito:** 1 parágrafo — o maior vazamento e o que ele custa.

## 🔧 Conserta primeiro (top 3)
1. <achado> — <o que ganha ao consertar>
2. ...
3. ...

## Achados por superfície
### <superfície> — <tipo>
- 🔴 **<princípio violado>** — <porquê comportamental>
  - Evidência: <arquivo:linha | região da tela>
  - Custo: <métrica> — <por quê>
  - Correção: <concreta e específica>
- 🟠 ...

## Lacunas (superfícies que eu não pude avaliar)
- <ex.: não havia tela de checkout na entrada>
```

## Regras (a voz do raio-x)
- **Não invente.** Se não dá pra ver, é lacuna — nunca presuma o que não está na entrada.
- **Honestidade sem bajulação.** Aponte o que vaza; só elogie pra dizer
  "isto está certo, **não mexa**".
- **Sempre pelo ângulo do negócio.** Todo achado amarra numa métrica. Se é só gosto e não
  move métrica, não é achado.
- **Contexto manda.** O mesmo elemento pode estar certo pra um ICP/estágio e errado pra outro —
  julgue contra o contexto do Passo 0, não contra uma regra absoluta.
- **Escopo:** conversão + comportamento + produto. Acessibilidade/segurança/performance só
  entram quando viram problema de conversão ou confiança (ex.: >3s no topo do funil).
