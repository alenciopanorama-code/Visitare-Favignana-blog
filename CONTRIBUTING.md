# 🤝 Contribuire al Blog

Grazie per voler contribuire a Blog Visitare Favignana!

## Come Contribuire

### 1. **Aggiungere un Nuovo Articolo**

#### Fase 1: Creazione
1. Crea un nuovo file HTML in `/docs/`
2. Nomina il file con lo slug dell'articolo (esempio: `tramonti-favignana.html`)
3. Usa il template base con meta tag SEO:

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Titolo Articolo | Blog Favignana</title>
    <meta name="description" content="Descrizione breve (160 caratteri)">
    <meta name="keywords" content="parola1, parola2, parola3">
    <link rel="canonical" href="https://visitarefavignana.eu/slug-articolo.html">
    
    <meta property="og:type" content="article">
    <meta property="og:title" content="Titolo">
    <meta property="og:description" content="Descrizione">
    <meta property="article:published_time" content="2024-05-19">
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Article",
        "headline": "Titolo",
        "description": "Descrizione",
        "datePublished": "2024-05-19",
        "author": {"@type": "Person", "name": "Blog Favignana"}
    }
    </script>
</head>
<body>
    <h1>Titolo Articolo</h1>
    <!-- Contenuto -->
</body>
</html>
```

#### Fase 2: Aggiornamento
1. **Aggiungi link in `index.html`**:
   ```html
   <a href="slug-articolo.html" class="article-card">
       <div class="article-image">emoji</div>
       <div class="article-content">
           <div class="article-meta">Data • Tempo lettura</div>
           <h2>Titolo</h2>
           <p>Descrizione breve</p>
           <span class="read-more">Leggi l'articolo →</span>
       </div>
   </a>
   ```

2. **Aggiorna `sitemap.xml`**:
   ```xml
   <url>
       <loc>https://visitarefavignana.eu/slug-articolo.html</loc>
       <lastmod>2024-05-19</lastmod>
       <changefreq>monthly</changefreq>
       <priority>0.8</priority>
   </url>
   ```

#### Fase 3: Push su GitHub
```bash
git add .
git commit -m "Aggiungi articolo: Titolo Articolo"
git push origin main
```

### 2. **Modificare Articolo Esistente**

```bash
# Modifica il file
nano docs/slug-articolo.html

# Commit e push
git add docs/slug-articolo.html
git commit -m "Aggiorna articolo: Titolo"
git push origin main
```

### 3. **Aggiornare Home Page**

Modifica `docs/index.html` per cambiare:
- Titolo del blog
- Descrizione
- Colori
- Articoli in evidenza
- CTA buttons

## 🎨 Guidelines per gli Articoli

### Lunghezza
- **Minimo:** 500 parole
- **Ideale:** 1500+ parole
- **Massimo:** Nessun limite, ma considera la user experience

### SEO
- ✅ Titolo: 50-60 caratteri
- ✅ Meta description: 155-160 caratteri
- ✅ H1: Uno solo per pagina
- ✅ H2/H3: Mantieni gerarchia
- ✅ Internal links: Collega articoli correlati
- ✅ Parole chiave: 2-3 volte nel testo

### Qualità
- Scrivi in italiano corretto
- Usa frasi brevi e chiare
- Dividi il testo in paragrafi piccoli
- Aggiungi emoji per rendere accattivante
- Includi call-to-action

## 🔍 Verifiche Prima di Pushare

```bash
# 1. Testa localmente
python -m http.server 8000 --directory docs

# 2. Apri http://localhost:8000 nel browser
# 3. Verifica che:
#    - ✅ Pagina carica correttamente
#    - ✅ Responsive su mobile
#    - ✅ Link interni funzionano
#    - ✅ Meta tag sono presenti

# 4. Valida HTML
# Usa: https://validator.w3.org

# 5. Verifica SEO
# Usa: https://pagespeed.web.dev
```

## 📋 Checklist Commit

Prima di ogni commit:

- [ ] File HTML valido (nessun errore W3C)
- [ ] Meta tag completi (title, description, og:)
- [ ] Schema.org JSON-LD presente
- [ ] Sitemap.xml aggiornato
- [ ] Link aggiunto a index.html
- [ ] Testato localmente
- [ ] Nessun file CSS/JS rotto

## 🚀 Merge Request (PR)

Se vuoi suggerire cambiamenti:

1. **Fork il repository**
2. **Crea un branch:** `git checkout -b feature/nome-feature`
3. **Fai le modifiche**
4. **Push il branch:** `git push origin feature/nome-feature`
5. **Apri una Pull Request** su GitHub
6. **Descrivi le modifiche** nel PR body
7. **Attendi la review**

## ⚠️ Non Fare

- ❌ Non modificare file `.github/workflows/`
- ❌ Non cambiare `robots.txt` senza consulenza SEO
- ❌ Non aggiungere file binari grandi (>50MB)
- ❌ Non cancellare articoli senza motivo
- ❌ Non rompere link interni

## 🆘 Problemi?

Se hai domande:
- Apri un **Issue** su GitHub
- Descrivi il problema dettagliatamente
- Allega screenshot se necessario
- Attendi il feedback

## 📞 Contatti

- **Email:** governaleguido92@gmail.com
- **GitHub:** @alenciopanorama-code

---

**Grazie per il contributo! 🙏**
