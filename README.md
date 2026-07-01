# product-skills

Coleção de skills para Claude Code focadas em **produto, conversão (CRO) e ciência
comportamental** — ferramentas de diagnóstico que rodam direto na sua code base ou
nas suas telas.

Formato compatível com o CLI [`skills`](https://github.com/obra/skills): cada skill
é uma pasta em `skills/<nome>/` com um `SKILL.md`.

## Skills

| Skill | O que faz | Quando usar |
|-------|-----------|-------------|
| [`raio-x-de-produto`](skills/raio-x-de-produto/SKILL.md) | Roda um raio-x numa **code base** ou em **telas** e devolve achados priorizados por onde o produto vaza receita (conversão, ativação, TTV, churn, LTV), com evidência localizável e correção concreta. | Antes de lançar/refatorar uma tela, LP, checkout, pricing, onboarding ou dashboard — quando você quer saber **onde está vazando dinheiro**, não se está "bonito". |
| [`produto-viral`](skills/produto-viral/SKILL.md) | Audita uma landing/produto (**telas** ou **code base**) contra os **32 princípios de produto viral** e devolve um placar ("22/32") com o que passa, o que falha e como corrigir. | Antes de publicar uma landing page ou lançar um produto — quando você quer um checklist opinativo e rápido de **virality + oferta + copy**. |

> **Qual usar?** `raio-x-de-produto` é o diagnóstico **amplo** de CRO + comportamento (vários tipos de tela, achados por impacto). `produto-viral` é um **checklist opinativo** de 32 itens focado em landing/oferta/copy, com placar. Dá para rodar os dois.

### `raio-x-de-produto`
- **Ativação:** só manual — digite `/raio-x-de-produto` no prompt (é `disable-model-invocation: true`,
  então o modelo não dispara sozinho; você chama quando quer).
- **Entrada:** aponte uma code base (rotas/telas/componentes) ou anexe prints de UI.
- **Saída:** relatório em português — veredito, "conserta primeiro" (top 3), achados por
  superfície e lacunas do que não deu para avaliar.
- A régua é uma só: **"design que não move receita é decoração."**

### `produto-viral`
- **Ativação:** só manual — digite `/produto-viral` no prompt (`disable-model-invocation: true`).
- **Entrada:** aponte a landing/produto no código ou anexe prints.
- **Saída:** relatório em português — placar dos 32, "conserta primeiro" (top 3), tabela item a
  item e detalhe das falhas.
- Princípios agressivos (sem plano grátis, sem assinatura, cobre mais) são tratados como
  **trade-off consciente** quando seu modelo de negócio contradiz de propósito — não como falha cega.

## Instalar

Uma skill específica:
```bash
npx skills add matheusnascimento-021/product-skills --skill raio-x-de-produto
```

Todas as skills do repo:
```bash
npx skills add matheusnascimento-021/product-skills
```

> Para instalar por aqui e usar em **qualquer projeto**, o repositório precisa estar
> **público**. Se estiver privado, você o torna público, ou instala a skill manualmente
> copiando a pasta `skills/raio-x-de-produto/` para o seu diretório de skills global.

## Licença
MIT. Os princípios de CRO, UX e economia comportamental catalogados nas skills são
conhecimento consolidado da área.
