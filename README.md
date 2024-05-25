### 1. Tworzenie sieci Docker

```bash
docker network create lab10net
```

### 2. Przygotowanie pliku HTML
Plik index.html został przygotowany i umieszczony w lokalnym katalogu html.

### 3. Konfiguracja katalogów dla logów
Utworzono katalogi web1, web2, web3 wewnątrz głównego katalogu lab10 dla logów nginx.

### 4. Uruchomienie kontenerów
Kontenery zostały uruchomione z użyciem następujących poleceń:
```bash
docker run --name web1 -v $(pwd)/html:/usr/share/nginx/html:ro -v $(pwd)/lab10/web1:/var/log/nginx -d --network lab10net -p 8081:80 nginx:latest
docker run --name web2 -v $(pwd)/html:/usr/share/nginx/html:ro -v $(pwd)/lab10/web2:/var/log/nginx -d --network lab10net -p 8082:80 nginx:latest
docker run --name web3 -v $(pwd)/html:/usr/share/nginx/html:ro -v $(pwd)/lab10/web3:/var/log/nginx -d --network lab10net -p 8083:80 nginx:latest
```

### 5. Dostępność stron HTML
Dostęp do stron każdego z serwerów sprawdzony przez przeglądarkę pod adresami:

http://localhost:8081
http://localhost:8082
http://localhost:8083
