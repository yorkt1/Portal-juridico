✅ CHECKLIST DE VALIDAÇÃO E COMPILAÇÃO
=====================================

## 1. VALIDAÇÃO TÉCNICA (HTML, CSS, Schema)

### 1.1 Validar HTML
- [ ] Usar [W3C Markup Validator](https://validator.w3.org/)
  - Opção: Direct Input (colar HTML) ou URL
  - Verificar se há erros críticos (não avisos)
  - Corrigir tags mal fechadas, atributos inválidos

- [ ] Validar cada página:
  - [ ] index.html
  - [ ] artigos.html
  - [ ] contato.html
  - [ ] sobre.html
  - [ ] privacidade.html

### 1.2 Validar Schema Markup (JSON-LD)
- [ ] Usar [Google Rich Results Test](https://search.google.com/test/rich-results)
  - Colar HTML de index.html (seção `<head>`)
  - Verificar:
    - ✅ Article schema detectado?
    - ✅ FAQPage schema detectado?
    - ✅ Organization schema detectado?
    - ⚠️ Há avisos (warnings)?
  - **Se houver erro:** corrigir JSON-LD e re-testar

- [ ] Testar ArticleSchema e FAQPage no [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool/)

### 1.3 Validar Links
- [ ] Verificar se links internos estão funcionando:
  - [ ] `<a href="#postsContainer">Artigos</a>` redireciona corretamente
  - [ ] `<a href="contato.html">Contato</a>` funciona
  - [ ] `rel="canonical"` aponta para URLs corretas

- [ ] Verificar links externos:
  - [ ] Instagram link acessível
  - [ ] LinkedIn link do desenvolvedor acessível

### 1.4 Verificar Sitemap e Robots
- [ ] Acessar `https://fatimafelipe.com.br/robots.txt`
  - Deve mostrar conteúdo de texto (User-agent, Disallow, Sitemap)
  
- [ ] Acessar `https://fatimafelipe.com.br/sitemap.xml`
  - Deve mostrar XML com URLs listadas
  - Verificar se não há erros 404

---

## 2. VALIDAÇÃO SEO ON-PAGE

### 2.1 Meta Tags
- [ ] **index.html**
  - [ ] Title: "Fátima Felippe — Portal Jurídico: Artigos e orientação em Direito" ✓
  - [ ] Meta description: contém palavras-chave "artigos", "direito" ✓
  - [ ] Meta robots: "index, follow" ✓
  - [ ] rel="canonical" presente ✓

- [ ] **artigos.html**
  - [ ] Title diferente e descritivo ✓
  - [ ] Meta description ✓
  - [ ] Canonical ✓

- [ ] **contato.html, sobre.html, privacidade.html**
  - [ ] Mesma verificação acima

### 2.2 Estrutura de Headings
- [ ] Cada página tem apenas UM `<h1>` (não 2 ou mais)
- [ ] Hierarquia respeitada: H1 → H2 → H3 (não pula H1 para H3)
- [ ] H1 contém palavra-chave principal

**Exemplo correto:**
```
<h1>Curatela: Instrumento de Proteção</h1>
  <h2>O que é Curatela</h2>
    <h3>Definição Legal</h3>
  <h2>Procedimento</h2>
    <h3>Passo 1: Laudo Médico</h3>
```

### 2.3 URLs Amigáveis
- [ ] URLs sem parâmetros desnecessários
- [ ] URLs use hífens (não underscore ou espaço)
- [ ] Exemplo: `https://fatimafelipe.com.br/guarda-compartilhada.html` ✓

### 2.4 Imagens com Alt
- [ ] Todas as `<img>` têm atributo `alt` descritivo
  - [ ] Não use "imagem1", "foto", etc.
  - [ ] Exemplo: `alt="Mulher representando o Direito"` ✓

---

## 3. VALIDAÇÃO PERFORMANCE (Core Web Vitals)

### 3.1 Usar PageSpeed Insights
- [ ] Acessar [PageSpeed Insights](https://pagespeed.web.dev/)
- [ ] Digite: `https://fatimafelipe.com.br`
- [ ] Esperar resultado e verificar:

| Métrica | Objetivo | Seu Score |
|---------|----------|-----------|
| LCP (Largest Contentful Paint) | < 2.5s | ___ |
| FID / INP (Interaction) | < 100ms / 200ms | ___ |
| CLS (Cumulative Layout Shift) | < 0.1 | ___ |

**Se vermelho (<50):**
- [ ] Comprimir imagens (usar Squoosh, TinyPNG)
- [ ] Remover CSS/JS não utilizado
- [ ] Ativar cache HTTP (verificar com hospedagem)
- [ ] Usar CDN para imagens (já usa Cloudinary ✓)

### 3.2 Verificar Mobile Friendliness
- [ ] Site é responsivo em celular?
- [ ] Usar [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
- [ ] Resultado: ✅ "Mobile Friendly" (esperado)

---

## 4. VALIDAÇÃO FUNCIONAL (Testes Locais)

### 4.1 Testar em navegadores
- [ ] Chrome (desktop + mobile)
- [ ] Firefox
- [ ] Safari (se Mac/iOS)
- [ ] Edge

**Verificar:**
- [ ] Menu hamburger funciona (mobile)
- [ ] Overlay fecha ao clicar fora
- [ ] Links internos (âncoras) funcionam
- [ ] Formulário de contato (se houver) funciona
- [ ] Imagens carregam sem erro
- [ ] Fonte é legível em todos tamanhos

### 4.2 Testar em Resoluções
- [ ] Desktop (1920x1080)
- [ ] Tablet (768x1024)
- [ ] Mobile (375x667)

Usar DevTools do Chrome: F12 → Toggle device toolbar (Ctrl+Shift+M)

### 4.3 Testar Dark Mode (opcional)
- Se o site usar prefers-color-scheme, testar ambos modos

---

## 5. PUBLICAÇÃO / DEPLOYMENT

### 5.1 Antes de fazer upload:
- [ ] Todos testes acima passaram ✓?
- [ ] Nenhum arquivo temporário ou teste incluído
- [ ] Diretório `/Nova pasta/` precisa ser removido? (Verificar se contém algo importante)

### 5.2 Upload para servidor
```bash
# Opção 1: Via FTP/SFTP (cPanel)
- Conectar ao servidor via FileZilla ou WinSCP
- Fazer upload de todos os arquivos (.html, .css, .js, sitemap.xml, robots.txt)

# Opção 2: Via Git (se hospedado em GitHub Pages / Netlify)
git add .
git commit -m "SEO: atualizar meta tags, schema markup, sitemap e robots.txt"
git push origin main
```

### 5.3 Após publicação, verificar:
- [ ] Site acessível via `https://fatimafelipe.com.br` (não mostra erro 404/500)
- [ ] HTTPS está ativo (certificado SSL válido)
- [ ] Certificado é válido (não expirado)

---

## 6. REGISTRAR NO GOOGLE SEARCH CONSOLE

### 6.1 Verificação do domínio
- [ ] Acessar [Google Search Console](https://search.google.com/search-console)
- [ ] Clique "Propriedade" e selecione "Adicionar propriedade"
- [ ] Escolha "Propriedade do domínio"
- [ ] Digite: `fatimafelipe.com.br`
- [ ] Clique "Continuar"
- [ ] Cópia o registro TXT fornecido
- [ ] Acesse seu painel de DNS (GoDaddy, NameCheap, etc.)
- [ ] Adicione o registro TXT
- [ ] Aguarde propagação (5min-48h)
- [ ] Retorne ao GSC e clique "Verificar"

### 6.2 Enviar Sitemap
- [ ] No GSC, vá para "Sitemaps"
- [ ] Cole: `https://fatimafelipe.com.br/sitemap.xml`
- [ ] Clique "Enviar"
- [ ] Aguarde processamento (Status: Sucesso)

### 6.3 Solicitar Indexação
- [ ] No GSC, use a barra de pesquisa no topo
- [ ] Cole: `https://fatimafelipe.com.br/`
- [ ] Clique "Inspecionar"
- [ ] Se não indexada: clique "Solicitar indexação"
- [ ] Repita para: `/artigos.html`, `/sobre.html`, `/contato.html`, `/privacidade.html`

### 6.4 Aguardar Resultados
- [ ] Dentro de 1-7 dias, URLs devem aparecer em "Cobertura"
- [ ] Monitorar "Performance" para primeiras impressões/cliques

---

## 7. CHECKLIST FINAL PRÉ-LANÇAMENTO

| Item | Status | Data | Obs |
|------|--------|------|-----|
| HTML válido (W3C) | ☐ | __ | |
| Schema markup correto (Rich Results) | ☐ | __ | |
| Sitemap.xml criado e acessível | ☐ | __ | |
| Robots.txt criado e correto | ☐ | __ | |
| Meta tags atualizadas (título, descrição) | ☐ | __ | |
| Canonical links presentes | ☐ | __ | |
| Links internos estruturados | ☐ | __ | |
| Imagens com alt descritivo | ☐ | __ | |
| PageSpeed Insights >= 50 (desktop) | ☐ | __ | |
| Mobile Friendly ✓ | ☐ | __ | |
| Testes em navegadores múltiplos ✓ | ☐ | __ | |
| Upload para servidor completado | ☐ | __ | |
| HTTPS ativo e válido | ☐ | __ | |
| Google Search Console verificado | ☐ | __ | |
| Sitemap enviado no GSC | ☐ | __ | |
| Primeiras URLs solicitadas para indexação | ☐ | __ | |

---

## 8. PRÓXIMAS AÇÕES (PÓS-PUBLICAÇÃO)

### Dia 1-3:
- [ ] Monitorar erros no GSC (Cobertura)
- [ ] Verificar se URLs estão sendo rastreadas

### Semana 1:
- [ ] Monitorar Performance (impressões, CTR)
- [ ] Corrigir qualquer erro detectado

### Semana 2-4:
- [ ] Publicar 1º novo artigo (conforme calendário editorial)
- [ ] Implementar schema FAQPage se necessário
- [ ] Adicionar links internos

### Mês 2+:
- [ ] Revisar analytics e GSC mensalmente
- [ ] Atualizar artigos com informações novas
- [ ] Continuar publicando conforme calendário

---

**Dúvidas? Veja o arquivo `PALAVRAS_CHAVE_E_ESTRATEGIA_SEO.md` para referência completa.**

Última atualização: 27 de dezembro de 2025
