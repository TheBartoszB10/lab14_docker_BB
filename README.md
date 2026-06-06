# Lab 14 - rozwiązanie


## Użyte polecenia:

Uruchomienie kontenerów: `docker compose up -d`
Przed uruchomieniem w tym samym folderze co plik muszą być pliki `db_root_password.txt` oraz `panel_root_password.txt` z hasłami.

Sprawdzenie czy serwer nginx działa: 
```
bartosz@tismpad ~/c/l/zadanie> curl http://localhost:4001
Serwer działa⏎
```
Sprawdzenie czy można utworzyć bazę danych przez phpMyAdmin:

Stan początkowy:<img width="819" height="197" alt="stan_przed" src="https://github.com/user-attachments/assets/d67df5bc-2e16-4a7e-befb-909e009fbff9" />

Stan po utworzeniu bazy:<img width="783" height="234" alt="stan_po" src="https://github.com/user-attachments/assets/6ed7e61b-52b3-4a15-aebd-a26a77a3028e" />

phpMyAdmin został dołączony do sieci backend, żeby mógł się połączyć z bazą danych. Dołączenie go do sieci `frontend` nie jest w przypadku połączenia przez `localhost` konieczne(dostęp bezpośrednio przez port 6001), lecz w przypadku "poważniejszym" należałoby phpMyAdmin do sieci `frontend` dołączyć, żeby móc wykorzystać nginx jako reverse proxy podczas dostępu.
