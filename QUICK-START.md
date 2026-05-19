# ⚡ Quick Start - 5 Minuti

Tutto quello che devi fare per lanciare il blog in produzione.

---

## 📋 Checklist Finale

### ✅ Fase 1: Repository GitHub (5 min)

1. **Vai a GitHub:** https://github.com/alenciopanorama-code
2. **Se repo non esiste:**
   - Clicca **New Repository**
   - Nome: `Visitare-Favignana-blog`
   - Public: ✅
   - Clicca **Create**
3. **Se repo esiste:** Vai direttamente al passaggio 2

### ✅ Fase 2: Caricare i File (2 min)

```bash
# Opzione A: Via terminale (Consigliato)
git clone https://github.com/alenciopanorama-code/Visitare-Favignana-blog.git
cd Visitare-Favignana-blog

# Copia i file dalla cartella Blog visitare Favignana in:
# - docs/
# - .github/workflows/
# - Root del repo

git add .
git commit -m "Initial commit: Blog Visitare Favignana"
git push -u origin main

# Opzione B: Via GitHub Web Interface
# 1. Vai su https://github.com/alenciopanorama-code/Visitare-Favignana-blog
# 2. Clicca "Add file" → "Upload files"
# 3. Trascina i file da /docs
# 4. Commit changes
```

### ✅ Fase 3: GitHub Pages Setup (2 min)

1. **Vai a:** https://github.com/alenciopanorama-code/Visitare-Favignana-blog/settings/pages
2. **Source:** `Deploy from a branch`
3. **Branch:** `main` / `/docs`
4. **Custom domain:** `visitarefavignana.eu`
5. Clicca **Save**

### ✅ Fase 4: DNS Configuration (1 min)

Contatta il registrar di `visitarefavignana.eu` e configura:

**Per visitarefavignana.eu:**
```
Host: @
Type: A
Values:
  185.199.108.153
  185.199.109.153
  185.199.110.153
  185.199.111.153
```

**Per www.visitarefavignana.eu:**
```
Host: www
Type: CNAME
Value: alenciopanorama-code.github.io
```

**Attendi 24-48 ore per la propagazione DNS.**

### ✅ Fase 5: Verifica Deploy (2 min)

1. **Vai a:** https://github.com/alenciopanorama-code/Visitare-Favignana-blog/actions
2. Verifica che il workflow `Deploy Blog to GitHub Pages` sia **verde** ✅
3. **Aspetta 5 minuti** (DNS non ancora propagato)
4. Apri nel browser: `https://visitarefavignana.eu`
5. Dovresti vedere la home page

---

## 🎯 Dopo il Deploy

### Indicizzare su Google (5 min)

1. **Google Search Console:** https://search.google.com/search-console
2. **Aggiungi proprietà:** `https://visitarefavignana.eu`
3. **Verifica proprietà** (scegli il metodo DNS)
4. **Aggiungi sitemap:** `/sitemap.xml`

### Condividere il Blog

- Email ai tuoi contatti
- Instagram: @alenciopanorama
- Sito Alencio Bistrot

---

## 📝 Prossimi Passi

**Per aggiungere nuovi articoli:**

```bash
# 1. Modifica/crea file HTML in /docs
# 2. Aggiorna index.html con il link
# 3. Aggiorna sitemap.xml

git add .
git commit -m "Aggiungi articolo: [Titolo]"
git push origin main

# ✅ Deploy automatico!
```

---

## 🆘 Se Qualcosa Non Funziona

### Sito non carica
- Verifica GitHub Pages Settings (branch + folder)
- Attendi la propagazione DNS (fino a 48 ore)
- Svuota cache browser (Ctrl+Shift+Del)

### Deploy fallisce
- Vai a **Actions** → Clicca il workflow fallito
- Leggi l'errore nel log
- Verifica che `/docs` contenga i file HTML

### Dominio non funziona
- Verifica DNS dal registrar
- Controlla che il file `CNAME` esista
- Testa con: `nslookup visitarefavignana.eu`

---

## 📞 Contatti

- **Email:** governaleguido92@gmail.com
- **GitHub:** @alenciopanorama-code
- **Repository:** https://github.com/alenciopanorama-code/Visitare-Favignana-blog

---

**Fatto! Il blog è pronto! 🚀**
