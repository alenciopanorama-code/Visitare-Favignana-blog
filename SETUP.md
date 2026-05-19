# 🔧 Setup Iniziale - Guida Passo-Passo

## ⚠️ IMPORTANTE: First-Time Setup

Segui questi passaggi **una sola volta** per configurare il repository GitHub con il deploy continuo.

---

## Passaggio 1: Preparare il Tuo Computer

### 1a. Installare Git (se non lo hai già)

**Windows:**
```bash
# Scarica da: https://git-scm.com/download/win
# Oppure con Chocolatey:
choco install git
```

**Mac:**
```bash
# Con Homebrew:
brew install git

# Oppure scarica da: https://git-scm.com/download/mac
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install git
```

### 1b. Configurare Git con i Tuoi Dati

```bash
git config --global user.name "Il Tuo Nome"
git config --global user.email "governaleguido92@gmail.com"
```

---

## Passaggio 2: Clonare il Repository

Se il repository esiste già su GitHub:

```bash
# Clona il repository
git clone https://github.com/alenciopanorama-code/Visitare-Favignana-blog.git

# Entra nella cartella
cd Visitare-Favignana-blog

# Verifica i file
ls -la
```

Se il repository **non esiste ancora**, vai su:
- https://github.com/new
- **Repository name:** `Visitare-Favignana-blog`
- **Description:** Blog ufficiale per scoprire Favignana e Alencio Bistrot
- **Public:** ✅ (per GitHub Pages)
- Clicca **Create Repository**

---

## Passaggio 3: Aggiungere i File del Blog

Copia i file che abbiamo creato nella cartella clonata:

```bash
# Dal tuo computer locale, copia:
# - docs/index.html
# - docs/alencio-panorama-favignana-soggiorno.html
# - docs/sitemap.xml
# - docs/robots.txt
# - docs/.htaccess
# - docs/README.md
# - docs/GUIDA-GOOGLE-INDEXING.md
# - CNAME
# - .gitignore
# - .github/workflows/deploy.yml
# - package.json
# - config.json
# - CONTRIBUTING.md
# - README.md
# - SETUP.md (questo file)
```

---

## Passaggio 4: Configurare l'Autenticazione GitHub

### Opzione A: Token GitHub (Consigliato)

1. Vai a: https://github.com/settings/tokens/new
2. Clicca **Generate new token** → **Generate new token (classic)**
3. Compila:
   - **Token name:** `blog-deploy-token`
   - **Expiration:** `No expiration`
   - **Scopes:** Seleziona `repo` (completo)
4. Clicca **Generate token** e **copia il token**

5. In terminale, durante il primo push:
   ```bash
   git push origin main
   ```
   - **Username:** Il tuo username GitHub
   - **Password:** Incolla il token che hai copiato

### Opzione B: SSH Key (Avanzato)

Se usi SSH, configura le chiavi SSH:
```bash
ssh-keygen -t ed25519 -C "governaleguido92@gmail.com"
cat ~/.ssh/id_ed25519.pub  # Copia l'output
```

Poi aggiungi la chiave pubblica su: https://github.com/settings/ssh/new

---

## Passaggio 5: Fare il Primo Push

```bash
# Nella cartella del repository
cd Visitare-Favignana-blog

# Aggiungi tutti i file
git add .

# Crea il primo commit
git commit -m "Initial commit: Blog Visitare Favignana setup"

# Pusha su GitHub
git push -u origin main
```

**Se il branch non è `main`, usa:**
```bash
git push -u origin master
```

---

## Passaggio 6: Configurare GitHub Pages

1. Vai a: https://github.com/alenciopanorama-code/Visitare-Favignana-blog
2. Clicca **Settings** → **Pages** (nel menu sinistro)
3. Configura:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` / `/docs`
4. Clicca **Save**
5. Vai a **Custom domain** e inserisci: `visitarefavignana.eu`
6. Clicca **Save**

---

## Passaggio 7: Configurare il DNS del Dominio

**Importante:** Il dominio `visitarefavignana.eu` deve puntare a GitHub Pages.

Contatta il registrar del dominio (GoDaddy, Namecheap, etc.) e configura:

### Record DNS:

**Opzione A: CNAME (Consigliato)**
```
Host: www
Type: CNAME
Value: alenciopanorama-code.github.io
```

**Opzione B: A Record (per www)**
```
Host: www
Type: CNAME
Value: alenciopanorama-code.github.io
```

**Per l'apex domain (senza www):**
```
Host: @
Type: A
Values: 
  185.199.108.153
  185.199.109.153
  185.199.110.153
  185.199.111.153
```

**Per www + apex:**
```
Host: @
Type: ALIAS/ANAME (se supportato)
Value: alenciopanorama-code.github.io
```

---

## Passaggio 8: Attendere la Propagazione DNS

Dopo aver configurato i DNS, aspetta **24-48 ore** per la propagazione globale.

Puoi controllare lo stato:
```bash
# Controlla il DNS
nslookup visitarefavignana.eu

# Oppure usa un servizio online:
# https://mxtoolbox.com/
```

---

## Passaggio 9: Verificare il Deploy

### 1. Controlla GitHub Actions
1. Vai a: https://github.com/alenciopanorama-code/Visitare-Favignana-blog/actions
2. Dovresti vedere un workflow `Deploy Blog to GitHub Pages` in **success** (verde)

### 2. Verifica il Sito Live
```bash
# Una volta che il DNS si è propagato:
curl -I https://visitarefavignana.eu

# Oppure apri nel browser:
https://visitarefavignana.eu
```

### 3. Controlla GitHub Pages
1. Vai a: https://github.com/alenciopanorama-code/Visitare-Favignana-blog/settings/pages
2. Verifica:
   - ✅ Dominio personalizzato: `visitarefavignana.eu`
   - ✅ Source: `Deploy from a branch` / `main` / `/docs`

---

## Passaggio 10: Test di Funzionamento

Dopo il deploy:

```bash
# 1. Home page
https://visitarefavignana.eu/

# 2. Articolo
https://visitarefavignana.eu/alencio-panorama-favignana-soggiorno.html

# 3. Sitemap
https://visitarefavignana.eu/sitemap.xml

# 4. Robots
https://visitarefavignana.eu/robots.txt
```

Tutti dovrebbero caricare correttamente.

---

## Passaggio 11: Indicizzare su Google

Dopo che il sito è live su `visitarefavignana.eu`:

1. Vai a: https://search.google.com/search-console
2. Aggiungi proprietà: `https://visitarefavignana.eu`
3. Verifica proprietà (via DNS o file)
4. Submita il `sitemap.xml`:
   ```
   https://visitarefavignana.eu/sitemap.xml
   ```

---

## 🚀 Tutto Fatto!

Il blog è ora:
- ✅ Online su https://visitarefavignana.eu
- ✅ Deployer automaticamente a ogni push
- ✅ Indicizzato da Google
- ✅ Ottimizzato per SEO

---

## 🔄 Prossimi Push (Aggiungi Articoli)

Una volta completato il setup iniziale, per aggiungere nuovi articoli:

```bash
# 1. Modifica file in /docs/

# 2. Commit e push
git add .
git commit -m "Aggiungi articolo: Titolo"
git push origin main

# 3. Il deploy avviene **automaticamente**!
```

---

## 🆘 Troubleshooting

### "fatal: could not read Username for 'https://github.com'"
Usa il token GitHub al posto della password, oppure configura SSH.

### "GitHub Pages site is not published"
1. Verifica che il branch sia `main` (non `master`)
2. Verifica che la cartella sia `/docs`
3. Attendi 5 minuti e ricarica

### "Dominio non funziona"
1. Verifica il file `CNAME` contiene: `visitarefavignana.eu`
2. Verifica i record DNS dal registrar
3. Attendi la propagazione DNS (24-48 ore)
4. Testa con: `nslookup visitarefavignana.eu`

### "Workflow fallisce"
1. Vai a **Actions** nel repository
2. Clicca sul workflow fallito
3. Leggi l'errore nel log
4. Risolvi il problema e repusha

---

**Domande? Apri un Issue su GitHub!**
