# Flask DevOps Project

## 📌 Projekt: Automatizirani Deployment Flask Aplikacije

Ovaj projekt prikazuje kako postaviti jednostavnu Flask web aplikaciju, kontejnerizirati je pomoću Dockera, automatizirati deployment koristeći CI/CD pipeline i pokrenuti aplikaciju pomoću `docker-compose`.

---

## 📁 Struktura Projekta
```
flask-ci-cd/
│── app.py                 # Glavna Flask aplikacija
│── requirements.txt        # Python dependency lista
│── Dockerfile              # Definiranje Docker image-a
│── docker-compose.yml      # Docker Compose konfiguracija
│── .github/workflows/      # CI/CD pipeline za automatizirani deploy
│── README.md               # Ovaj dokument
```

---

## 🚀 1. Pokretanje aplikacije lokalno
Ako želiš testirati aplikaciju bez Dockera, pokreni sljedeće naredbe:
```bash
# Instaliraj dependency-je
pip install -r requirements.txt

# Pokreni aplikaciju
python app.py
```
Aplikacija će biti dostupna na: [http://localhost:5000](http://localhost:5000)

---

## 🐳 2. Dockerizacija aplikacije

### **2.1 Izrada Docker image-a**
```bash
docker build -t my-flask-app .
```

### **2.2 Pokretanje Docker container-a**
```bash
docker run -p 5000:5000 my-flask-app
```
Aplikacija će biti dostupna na: [http://localhost:5000](http://localhost:5000)

---

## 🔄 3. Korištenje Docker Compose-a

Umjesto da pokrećeš Docker ručno, možeš koristiti `docker-compose` za upravljanje servisima:
```bash
docker-compose up -d
```
Aplikacija će biti dostupna na: [http://localhost:5000](http://localhost:5000)

Za zaustavljanje servisa:
```bash
docker-compose down
```

---

## 🛠️ 4. CI/CD Pipeline (GitHub Actions)
Automatizacija je postavljena pomoću GitHub Actions. Workflow se nalazi u `.github/workflows/deploy.yml`.

### **4.1 Što radi CI/CD pipeline?**
✅ Svaki `git push` u `main` granu pokreće:
1. **Build Docker image-a**
2. **Provjeru koda** (linting, testovi)
3. **Deployment na server** (opcija za cloud hosting)

---

## 🌍 5. Deployment na server (opcija)
Ako želiš deployati aplikaciju na cloud, možeš koristiti VPS ili cloud provider (AWS, GCP, Azure).

Primjer deploya na server s Docker Compose-om:
```bash
git pull origin main
docker-compose up -d --build
```

---

## 📜 6. Zaključak
✅ Dockerizacija aplikacije 🚀  
✅ Automatizirani CI/CD pipeline 🤖  
✅ Deployment s Docker Compose-om 🛠️  



---

👨‍💻 **Autor:** Stefan Belić  
📌 **Repozitorij:** [GitHub](https://github.com/StefanBelic1/flask-ci-cd)

