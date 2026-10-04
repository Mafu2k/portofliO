# Portfolio

Moja strona-wizytówka dostępna pod [lukaszjanicki.dev](https://lukaszjanicki.dev): krótko o mnie,
doświadczenie, projekty z GitHuba i kontakt. Zrobiona w Vue 3 i Vite, a animacje przy przewijaniu
obsługuje GSAP (ScrollTrigger).

## Uruchomienie

```bash
npm install
npm run dev      # http://localhost:5173
npm run build    # wersja produkcyjna w dist/
```

## Jak to jest zbudowane

Strona to jeden komponent `src/App.vue`. Wszystkie treści, czyli umiejętności, oś czasu
z doświadczeniem, lista projektów i kolory języków, są w `src/data/profile.js`. Żeby dodać
projekt albo zmienić opis, wystarczy edytować ten plik bez ruszania szablonu.
Filtry w sekcji projektów generują się same na podstawie pola `lang`.

Domena jest ustawiona w `public/CNAME`.

## Licencja

MIT
