# tota — strona biblioteki

Statyczna, responsywna strona dokumentacji biblioteki `tota` — prostej biblioteki Python do tworzenia i uczenia sieci neuronowych.

## Lokalny podgląd

Wymagany jest tylko Python 3:

```bash
python3 -m http.server 8000
```

Otwórz <http://localhost:8000>.

## Zawartość

- opis biblioteki i jej architektury,
- szybki start z przykładem kodu,
- dokumentacja `Neuron`, `Layer` i `Network`,
- interaktywny wybór funkcji aktywacji,
- wersja biblioteki: `0.4.0`.

## Publikacja na Cloudflare Pages

### Opcja A — połączenie z GitHubem (zalecana)

1. Wejdź na [dash.cloudflare.com](https://dash.cloudflare.com/) i wybierz konto.
2. Otwórz **Workers & Pages → Create application → Pages → Connect to Git**.
3. Połącz konto GitHub i wybierz repozytorium `tota-website`.
4. Ustaw:
   - **Production branch:** `main`
   - **Framework preset:** `None`
   - **Build command:** pozostaw puste
   - **Build output directory:** `/` (katalog główny repozytorium)
5. Kliknij **Save and Deploy**.
6. Cloudflare poda adres w formacie `https://tota-website.pages.dev`.

Każdy kolejny push do `main` uruchomi automatyczne wdrożenie.

### Opcja B — ręczne wdrożenie przez Wrangler

Na komputerze z Node.js:

```bash
npm install -g wrangler
wrangler login
wrangler whoami
```

Następnie, w katalogu repozytorium:

```bash
wrangler pages project create tota-website
wrangler pages deploy . --project-name=tota-website
```

Jeśli projekt Pages już istnieje, wystarczy ponownie wykonać drugą komendę. Po wdrożeniu użyj adresu wyświetlonego przez Wrangler.

> Nie wpisuj tokenów API do repozytorium. Przy wdrożeniu lokalnym użyj `wrangler login`, a w CI skonfiguruj sekret `CLOUDFLARE_API_TOKEN` w ustawieniach GitHub Actions.

## Ważna uwaga o kodzie biblioteki

Ta strona dokumentuje aktualnie zainstalowaną wersję `tota 0.4.0` z projektu autora. Repozytorium strony jest osobne od repozytorium kodu biblioteki; link do kodu można podmienić w `index.html`, gdy repozytorium biblioteki będzie już publiczne.
