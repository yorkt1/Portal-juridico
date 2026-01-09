🚀 QUICK START — PUBLICAÇÃO E GOOGLE SEARCH CONSOLE
====================================================

**Tempo total: ~75 minutos**

---

## 1️⃣ PRÉ-PUBLICAÇÃO (10 min)

### Verificar em casa (antes de subir)

Abra seu navegador e teste:

```
1. Abrir index.html localmente:
   Arquivo → Abrir arquivo → c:/Users/guilh/Documents/adv-nf/index.html
   
2. Verificar:
   ☐ Página carrega sem erro
   ☐ Menu funciona (clique em "Artigos", "Contato", etc.)
   ☐ Links estão vermelhos (não visitados) ou azuis (visitados)
   ☐ Imagens aparecem (devem carregar de Cloudinary)
   ☐ Responsivo? (F12 → Ctrl+Shift+M → testar em 375px, 768px, 1920px)
```

---

## 2️⃣ PUBLICAÇÃO NO SERVIDOR (15 min)

### Opção A: FTP (FileZilla)

```bash
1. Download FileZilla: https://filezilla-project.org/
2. Abrir → Edit → Settings
3. Adicionar novo site:
   - Host: seu.provedor.com
   - Usuário: seu_cpanel_user
   - Senha: sua_senha
4. Arrastar arquivos de c:\...\adv-nf para servidor:
   - index.html
   - artigos.html
   - contato.html
   - sobre.html
   - privacidade.html
   - sitemap.xml
   - robots.txt
   - (opcional: pasta de imagens/CSS)
5. Verificar em: https://fatimafelipe.com.br
```

### Opção B: cPanel File Manager (mais fácil)

```bash
1. Acessar cPanel do seu provedor
2. Clicar em "File Manager"
3. Navegar para raiz do domínio (public_html)
4. Upload dos 7 arquivos acima
5. Verificar permissões: 644 (arquivos), 755 (pastas)
```

### Opção C: Git (Netlify/GitHub Pages)

```bash
git add .
git commit -m "SEO: meta tags, schema markup, sitemap, robots.txt"
git push origin main
# Aguardar deploy automático (~1-2 min)
```

**✅ Após upload, testar:**
```
https://fatimafelipe.com.br/
https://fatimafelipe.com.br/robots.txt (deve mostrar texto)
https://fatimafelipe.com.br/sitemap.xml (deve mostrar XML)
HTTPS deve estar ativo (🔒 cadeado)
```

---

## 3️⃣ GOOGLE SEARCH CONSOLE (45 min)

### 3A. Verificar Domínio (30 min)

```
1. Ir para: https://search.google.com/search-console
2. Clicar "Começar agora" (ou "+" se já tem propriedades)
3. Escolher "Propriedade do domínio"
4. Digitar: fatimafelipe.com.br
5. Clique "Continuar"
6. Cópia o registro TXT mostrado (exemplo):
   google-site-verification=abc123xyz456...
```

**Agora ir ao seu registrador de domínio (GoDaddy, NameCheap, etc.):**

```
1. Login em GoDaddy/NameCheap/etc.
2. Ir para "Gerenciar Domínios"
3. Clicar em fatimafelipe.com.br
4. Encontrar "DNS" ou "Registros DNS"
5. Procurar por "TXT" ou "Novo Registro"
6. Adicionar novo registro TXT:
   Tipo: TXT
   Nome/Host: @ (ou deixar vazio)
   Valor: google-site-verification=abc123xyz456...
   TTL: 3600 (padrão)
7. Salvar
8. Voltar ao Google Search Console
9. Clicar "Verificar"
10. ⏳ Aguardar 5min-48h (geralmente 5-10min)
11. ✅ Quando aparecer "Propriedade verificada", continuar
```

**Se após 48h não verificar:**
- [ ] Verificar se TXT foi adicionado (aguardar propagação)
- [ ] Ou usar método alternativo: upload arquivo HTML na raiz (GSC mostra opção)

### 3B. Enviar Sitemap (5 min)

```
1. No GSC (após verificado), menu esquerdo
2. Clique "Sitemaps"
3. Campo de texto: colar https://fatimafelipe.com.br/sitemap.xml
4. Clique "Enviar"
5. Status aparecerá como "Pendente" ou "Sucesso"
6. ⏳ Aguardar 1-3 dias para processar

Resultado esperado:
- 5 URLs lidas
- 0 erros
- Status: Sucesso
```

### 3C. Solicitar Indexação (10 min)

```
1. GSC, barra de pesquisa (topo)
2. Colar: https://fatimafelipe.com.br/
3. Clique no URL que aparece
4. Painel mostra:
   ☐ URL é acessível?
   ☐ URL pode ser indexada?
   ☐ Problemas encontrados?
5. Se OK: clique "Solicitar indexação"
6. Google fila para rastreamento

Repetir para:
- https://fatimafelipe.com.br/artigos.html
- https://fatimafelipe.com.br/sobre.html
- https://fatimafelipe.com.br/contato.html
- https://fatimafelipe.com.br/privacidade.html

⏳ Dentro de 1-7 dias, devem aparecer em "Cobertura" como "Válidas"
```

---

## 4️⃣ VALIDAR SCHEMA (5 min — OPCIONAL, mas recomendado)

```
1. Ir para: https://search.google.com/test/rich-results
2. Clicar "Testar código"
3. Copiar HTML de <head> a </head> do seu index.html
4. Colar na caixa de texto
5. Clique "Testar"
6. Esperado: ✅ 5 valid items encontrados:
   - WebSite
   - Organization
   - Article (Curatela)
   - Article (Tutela)
   - FAQPage

Se aparecer ⚠️ aviso: não é crítico, mas anote para corrigir depois.
```

---

## 5️⃣ MONITORAR (Após 1 semana)

### Voltando ao GSC:

```
Menu "Performance":
☐ Quantas impressões apareceram?
☐ Quantos cliques recebeu?
☐ Qual a posição média? (desejável: <10)
☐ Qual o CTR? (desejável: >2%)

Menu "Cobertura":
☐ Quantas URLs estão indexadas? (desejável: 5)
☐ Há erros de indexação? (sim → corrigir)

Se tudo OK:
✅ Primeira semana bem-sucedida!
Próximo: Publicar 1º novo artigo (vide calendário em PALAVRAS_CHAVE_E_ESTRATEGIA_SEO.md)
```

---

## 📞 SUPORTE RÁPIDO

| Dúvida | Resposta | Arquivo |
|--------|----------|---------|
| Como escolher próximas palavras-chave? | Consultar tabela de 50+ palavras-chave | PALAVRAS_CHAVE_E_ESTRATEGIA_SEO.md |
| Há erro ao verificar no GSC? | Testar método alternativo (upload HTML) | CHECKLIST_VALIDACAO.md |
| Preciso publicar novo artigo? | Use calendário de 12 semanas | PALAVRAS_CHAVE_E_ESTRATEGIA_SEO.md |
| Qual é o próximo passo? | Monitorar Performance no GSC por 1 mês | RELATORIO_FINAL_VALIDACAO.md |

---

## ✅ CHECKLIST FINAL

```
☐ Arquivos (.html, .xml, .txt) prontos
☐ Testado localmente (sem erros)
☐ Upload para servidor (https://fatimafelipe.com.br acessível)
☐ HTTPS ativo (cadeado 🔒 visível)
☐ Domínio verificado no GSC
☐ Sitemap enviado ao GSC
☐ URLs solicitadas para indexação
☐ Schema validado (Rich Results Test)
☐ Primeira semana monitorada (Performance GSC)
☐ Próximo artigo agendado para publicação
```

---

**Tempo total: ~75 minutos**  
**Resultado: Site otimizado, visível no Google em 1-7 dias**

Dúvidas? Consulte os guias:
- 📄 PALAVRAS_CHAVE_E_ESTRATEGIA_SEO.md (guia completo)
- ✅ CHECKLIST_VALIDACAO.md (validação detalhada)
- 📊 RELATORIO_FINAL_VALIDACAO.md (sumário técnico)
