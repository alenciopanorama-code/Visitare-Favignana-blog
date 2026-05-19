# 🌅 Blog Visitare Favignana

Blog ufficiale per scoprire le Isole Egadi, Favignana e l'Alencio Panorama Residence con Alencio Bistrot.

**Sito Live:** [https://visitarefavignana.eu](https://visitarefavignana.eu)

## 📁 Struttura del Progetto

```
Visitare-Favignana-blog/
├── docs/                          # File HTML (GitHub Pages)
│   ├── index.html                # Home page
│   ├── alencio-panorama-favignana-soggiorno.html
│   ├── sitemap.xml               # Sitemap per Google
│   ├── robots.txt                # Configurazione bot
│   ├── .htaccess                 # Ottimizzazioni server
│   └── README.md                 # Documentazione blog
├── .github/workflows/
│   └── deploy.yml                # GitHub Actions deploy
├── CNAME                         # Dominio personalizzato
├── .gitignore
└── README.md                     # Questo file

```

## 🚀 Deploy Continuo (CI/CD)

Il blog usa **GitHub Actions** per deploy automatico:

1. **Push su branch `main`** → Trigger automatico
2. **Build & Deploy** → I file in `/docs` vengono pubblicati
3. **Live su GitHub Pages** → Raggiungibile da https://visitarefavignana.eu

### Come Funziona

- File nel branch `main`
- Cartella `/docs` viene servita come sito statico
- Dominio personalizzato via `CNAME`
- Deploy automatico a ogni push

## 📝 Come Aggiungere Articoli

1. **Crea nuovo file HTML** in `/docs/` (esempio: `tramonti-favignana.html`)
2. **Usa il template SEO:**
   ```html
   <meta name="description" content="...">
   <meta property="og:title" content="...">
   <script type="application/ld+json">
     {"@context": "https://schema.org", "@type": "Article", ...}
   </script>
   ```
3. **Aggiungi link in `index.html`** (nella griglia articoli)
4. **Aggiorna `sitemap.xml`** con il nuovo URL
5. **Push su GitHub** → Deploy automatico

## 🔧 Configurazione GitHub Pages

Se il deploy non funziona:

1. Vai su **Impostazioni del Repository** → **Pages**
2. Seleziona **Branch:** `main` / **Cartella:** `/docs`
3. Verifica che **Custom Domain** sia impostato a `visitarefavignana.eu`
4. Il DNS del dominio deve puntare ai nameserver di GitHub

## 📊 SEO & Performance

Il blog include:

- ✅ Meta tag completi
- ✅ Open Graph & Twitter Card
- ✅ Schema.org JSON-LD
- ✅ Sitemap.xml
- ✅ Robots.txt
- ✅ .htaccess (cache, compression, HTTPS)
- ✅ Responsive design
- ✅ Breadcrumb Schema

## 🔍 Monitorare il Deploy

### Su GitHub
1. Vai su **Actions** nel repository
2. Vedi lo stato del workflow `Deploy Blog to GitHub Pages`
3. Click su un run per vedere i dettagli

### Verificare il Sito Live
```bash
curl -I https://visitarefavignana.eu
```

## 📱 Sviluppo Locale

Per testare localmente:

1. **Clone il repository:**
   ```bash
   git clone https://github.com/alenciopanorama-code/Visitare-Favignana-blog.git
   cd Visitare-Favignana-blog
   ```

2. **Apri un server locale:**
   ```bash
   # Con Python 3
   python -m http.server 8000 --directory docs
   
   # Con Node.js (se hai npx)
   npx http-server docs
   ```

3. **Visita:** http://localhost:8000

## 🐛 Troubleshooting

### Deploy fallisce
- Controlla che `/docs` contenga i file HTML
- Verifica il workflow in **Actions** → vedi il log di errore

### Dominio non funziona
- CNAME file deve contenere solo `visitarefavignana.eu`
- DNS deve essere configurato (contatta il registrar del dominio)
- Aspetta 24-48 ore per la propagazione DNS

### GitHub Pages non si aggiorna
- Svuota cache del browser (Ctrl+Shift+Del)
- Attendi qualche minuto dopo il push
- Verifica il workflow in **Actions**

## 📞 Contatti

- **Website:** https://visitarefavignana.eu
- **Email:** governaleguido92@gmail.com
- **Instagram:** @alenciopanorama

## 📄 Licenza

Contenuto © 2024 Blog Visitare Favignana. Tutti i diritti riservati.

---

**Fatto con ❤️ da Guido Governale**
