# Nginx HTTP/2 Demonstration

Ovaj projekt prikazuje prednosti **HTTP/2** protokola u usporedbi s **HTTP/1.x** korištenjem Nginx web poslužitelja. U sklopu vježbe implementirani su HTTPS/SSL i HTTP/2 protokol, a razlike u brzini učitavanja prikazane su pomoću jednostavne web stranice s više resursa (CSS, JavaScript i slike).

## Struktura projekta
- **Konfiguracija Nginx-a**:
  - Konfiguracijska datoteka: `conf/nginx.conf`
- **Web stranica**:
  - Smještena na putanji: `/html/lab4`
  - Sadrži:
    - `index.html` - Glavna stranica
    - `css/` - Stilovi
    - `js/` - JavaScript datoteke
    - `images/` - Slike (10+ datoteka za demonstraciju učitavanja resursa)
- **Log datoteke**:
  - `http2.har` - Log učitavanja stranice s uključenim HTTP/2 protokolom.
  - `no_http2.har` - Log učitavanja stranice bez HTTP/2 (samo HTTP/1.x).
- **Screenshotovi**:
  - `http2.jpg` - Prikaz konzole preglednika s HTTP/2.
  - `no_http2.jpg` - Prikaz konzole preglednika s HTTP/1.x.

## Koraci implementacije
1. **Instalacija Nginx-a**:
   - Preuzet i instaliran Nginx za Windows.
2. **Generiranje SSL certifikata**:
   - Korištenjem OpenSSL generiran je privatni ključ (`private.key`) i samopotpisani certifikat (`certificate.crt`).
3. **Konfiguracija HTTPS i HTTP/2**:
   - U datoteci `nginx.conf` omogućeni su HTTPS i HTTP/2.
4. **Testiranje brzine učitavanja**:
   - Zabilježeni su logovi i vrijeme učitavanja stranice s HTTP/2 i HTTP/1.x.

## Demonstracija
Web stranica dostupna je na sljedećim putanjama na lokalnom poslužitelju:
- **HTTP**: [http://localhost/lab4](http://localhost/lab4)
- **HTTPS**: [https://localhost/lab4](https://localhost/lab4)

## Napomene
- Datoteke za web stranicu nalaze se u direktoriju `/html/lab4` unutar instalacijskog direktorija Nginx-a.
- Rezultati testiranja jasno pokazuju prednosti HTTP/2 protokola, posebno kod učitavanja velikog broja resursa zahvaljujući binarnom prijenosu podataka i paralelizmu zahtjeva.