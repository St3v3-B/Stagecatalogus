<h1 align="center">Stagecatalogus</h1>

<p align="center">
  <a href="#-quickstart"><img alt="Quickstart" src="https://img.shields.io/badge/Quickstart-1,2,3-2563EB?style=for-the-badge"></a>
  <a href="#-stack"><img alt="Stack" src="https://img.shields.io/badge/PHP-8.1+-2563EB?style=for-the-badge"></a>
  <a href="#lock_security"><img alt="Security" src="https://img.shields.io/badge/Secure_by_default-16a34a?style=for-the-badge"></a>
</p>

<p align="center">
  Stagecatalogus combineert een moderne stagecatalogus met een krachtig adminportaal.<br>
  Publieke studenten krijgen toegang via unieke tokens, terwijl beheerders bedrijven, stage-typen en toegangscodes beheren.
</p>

---

## ✨ Features
- **Publieke catalogus** met filters, dark-mode, favoriete stages, hidden easter eggs (logo taps, Konami-code).
- **Stagekeuze wizard** (`/kiezen`) waar studenten hun top 3 stages indienen (alleen via `@student.graafschapcollege.nl`).
- **Admin dashboard** (`/admin`) met CRUD voor bedrijven, stage-typen, toegangscodes en gebruikers.
- **Slimme caching** voor stagecards, stage-typen en geocode requests.
- **Installer** (`install.php`) die tabellen aanmaakt, demo-data seed en bestandsrechten fixeert.

## 🧱 Stack
| Laag                | Technologie |
|---------------------|-------------|
| Core                | PHP 8.1+ (zonder Composer) |
| Data                | MySQL 8.x (PDO) |
| Front-end utilities | Bootstrap 5, jQuery 3, lite custom JS |
| Styling             | Custom `theme.css` met dark-mode en retro-mode |

## 🚀 Quickstart
1. **Repository clonen**
   ```bash
   git clone https://github.com/<jouw-account>/stagecatalogus.git
   cd stagecatalogus
   ```

2. **Configuratie kopiëren & invullen**
   ```bash
   cp storage/app_config.example.php storage/app_config.php
   ```
   - Vul in `storage/app_config.php` je databasegegevens, `base_url` en optionele geocode-instellingen in.
   - Controleer schrijfbare mappen: `storage/`, `images/`, `videos/`.

3. **Installer draaien**
   - Open `https://<jouw-domein>/install.php` in de browser.
   - Volg de stappen (db, site, admin, optionele seed) → klik *Installeer*.
   - Verwijder of blokkeer `install.php` zodra je klaar bent.

4. **Aan de slag**
   - Log in op `/admin/` met je aangemaakte account.
   - Genereer toegangscodes (maak tokenlinks zoals `https://<base>?token=...`).
   - Deel de link met studenten; zij kunnen meteen filteren, favorieten markeren en keuzes indienen.

> ✅ Tip: Gebruik een lokale `.env` of secretsmanager voor je databasewachtwoord; `storage/app_config.php` staat in `.gitignore`.

## 🔒 Security
- Alle database calls gebruiken prepared statements.
- Session cookies: `HttpOnly`, `SameSite=Lax`, eigen sessietegel in `storage/sessions`.
- Uploads lopen via een mediaproxy (`info/media.php`) om pad-leaks te voorkomen.
- Installer checkt bestandsrechten en verplicht een sterk adminwachtwoord.
- `.gitignore` beschermt `storage/app_config.php`, uploads en overige lokale artefacts.

## 📸 Screens & UI highlights
| Publieke catalogus | Stagekeuze wizard | Admin dashboard |
|--------------------|-------------------|-----------------|
| _Voeg screenshots toe (PNG/JPG)_ | _Screenshots van stappen_ | _Dashboard overzicht_ |

## 🧪 Testen & onderhoud
- Handmatige QA: token-claim flow → filters → detailpagina → stagekeuze inzending.
- Upload een logo/video en check de rendering & caching.
- Controleer `/admin/` CRUD-acties en dat caches vernieuwen.
- (Optioneel) voeg je eigen PHPUnit/Laravel Dusk suite toe als het project groeit.

## 🤝 Bijdragen
1. Fork & clone de repo.
2. Maak een feature branch (`git checkout -b feature/nieuwe-actie`).
3. Commit kleine, duidelijke stappen.
4. Open een Pull Request met beschrijving & test-notes.

## 📄 Licentie
Kies een licentie en voeg `LICENSE` toe (bijv. MIT, GPL, propriëtair).

---

<p align="center">💬 Vragen of ideeën? Open een issue of stuur een berichtje – veel succes met je stagezoektocht!</p>
