O que foi feito:

- Atualizados `title`, `meta description`, `robots` e `rel=canonical` em páginas principais.
- Inserido JSON-LD básico (WebSite / Organization / Person / CollectionPage) para melhorar presença no Google.
- Criados `sitemap.xml` e `robots.txt` com referência ao sitemap.

Próximos passos recomendados:

1) Enviar `https://fatimafelipe.com.br/sitemap.xml` no Google Search Console (verificar propriedade do domínio via DNS TXT para cobertura completa).
2) No GSC: Inspeção de URL das páginas principais e solicitar indexação após publicação.
3) Configurar Google Analytics 4 (se ainda não estiver) e ativar anonimização de IP (considerando LGPD).
4) Otimizar conteúdo por palavra-chave: criar uma planilha com pares (URL ↔ palavra-chave alvo ↔ intenção ↔ prioridade).
5) Implementar schema `FAQPage` em posts com perguntas/respostas e `Article` em cada artigo individual.
6) Melhorar Core Web Vitals: usar compressão, remover CSS/JS não usados, ativar cache/CDN.

Comandos úteis (localmente) para validar sitemap e markup:

- Validar sitemap (curl):

```bash
curl -I https://fatimafelipe.com.br/sitemap.xml
```

- Testar JSON-LD localmente: cole o JSON-LD no Rich Results Test (https://search.google.com/test/rich-results) ou use a extensão 'Structured Data Testing Tool'.

Se quiser, eu:
- Subo marcação FAQ/Article para os 10 artigos mais importantes;
- Gero uma planilha com 50 palavras-chave de cauda longa e intenção;
- Preparo email/texto com instruções passo-a-passo para verificar no Google Search Console.
