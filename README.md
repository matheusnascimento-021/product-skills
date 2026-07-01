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

### `raio-x-de-produto`
- **Ativação:** só manual — digite `/raio-x-de-produto` no prompt (é `disable-model-invocation: true`,
  então o modelo não dispara sozinho; você chama quando quer).
- **Entrada:** aponte uma code base (rotas/telas/componentes) ou anexe prints de UI.
- **Saída:** relatório em português — veredito, "conserta primeiro" (top 3), achados por
  superfície e lacunas do que não deu para avaliar.
- A régua é uma só: **"design que não move receita é decoração."**

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
