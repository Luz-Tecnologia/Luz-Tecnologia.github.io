# luz.tec.br

Site institucional da Luz Tecnologia. É uma página única feita só com HTML, CSS e JavaScript, sem framework e sem etapa de build, publicada no GitHub Pages.

A identidade visual segue o **Manual da marca v1.0**, que fica no repositório [identidade-visual](https://github.com/Luz-Tecnologia/identidade-visual).

## Estrutura

```
index.html              página única: início, serviços, para quem, como trabalhamos,
                        projetos, sobre, perguntas frequentes e contato
404.html                página de erro (o GitHub Pages usa sozinho)
assets/css/styles.css   cores da marca em :root, layout e componentes
assets/js/main.js       menu no celular, item ativo do menu, ano no rodapé, animação de entrada
assets/img/             logos copiados do identidade-visual + og-image.png (prévia em redes sociais)
site.webmanifest        nome e ícones para celular
CNAME                   domínio do GitHub Pages (luz.tec.br)
robots.txt, sitemap.xml indexação em buscadores
```

## Rodar localmente

```bash
python3 -m http.server 8080
```

Depois abra http://localhost:8080.

## Antes de publicar: textos a revisar

| Onde | O que fazer |
| --- | --- |
| `index.html`, seção **Perguntas frequentes** (`#perguntas`) | Confira se as respostas (suporte, órgãos públicos, orçamento) refletem como a empresa trabalha. |
| `index.html`, seções **Para quem** e **Sobre** | Revise o tom e as promessas, como "atenção à LGPD" e "decisões documentadas". |

Para achar os trechos provisórios:

```bash
grep -n "data-provisorio\|PROVISÓRIO\|REVISAR" index.html
```

## Regras da marca aplicadas

- Cores: Azul-noite `#0E1A2B`, Âmbar `#F5A623`, Névoa `#F3F5F8`, Ardósia `#5B6677`.
- O Âmbar aparece só sobre Azul-noite e só como destaque (quarto de sol no início e no contato, números dos passos). Nunca sobre branco.
- Fonte Manrope em tudo. JetBrains Mono para números (telefone, CNPJ, numeração).
- Assinatura completa com pelo menos 170 px de largura. No celular o cabeçalho usa a versão reduzida.
- O quarto de sol fica num canto inferior, cortado pelas bordas, e nunca passa por baixo de texto.

Se os logos mudarem no `identidade-visual`, copie de novo para `assets/img/`:

```bash
cp ../identidade-visual/luz-{assinatura,reduzida,simbolo}.svg assets/img/
```

## Publicar no GitHub Pages

1. Envie para a branch `main`.
2. No GitHub, abra **Settings → Pages** e escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Em **Custom domain** deve aparecer `luz.tec.br`, que vem do arquivo `CNAME`.
4. Depois que o DNS propagar, marque **Enforce HTTPS**.

### DNS de luz.tec.br (no Registro.br ou no provedor de DNS)

| Tipo | Nome | Valor |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153` |
| AAAA | `@` | `2606:50c0:8001::153` |
| AAAA | `@` | `2606:50c0:8002::153` |
| AAAA | `@` | `2606:50c0:8003::153` |
| CNAME | `www` | `luz-tecnologia.github.io` |

Confira os valores atuais na documentação do GitHub Pages ("Managing a custom domain").

## Assinatura de e-mail

O ícone da assinatura de e-mail (`identidade-visual/assinatura-email.html`) pode apontar para a imagem publicada aqui:

```
https://luz.tec.br/assets/img/luz-simbolo-192.png
```
