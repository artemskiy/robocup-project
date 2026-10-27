# RoboCup Dev Environment

## 1. Установка

**Windows / macOS**  
Установить [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Windows: включить интеграцию с WSL 2).

**Ubuntu**
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## 2. Работа

**Сборка образа (выполняется один раз):**
```bash
docker build -t my-ubuntu-2204 .
```

**Вход в контейнер (запускает и подключает к терминалу):**
```bash
docker compose up -d && docker compose exec robocup bash
```

**Выход из контейнера:**
```bash
exit
```

**Удалить контейнер (если обновили настройки контейнера):**
```bash
docker compose down
```

**Нюансы**
* Текущая папка проекта на ПК связана с `/workspace` внутри контейнера.
* Пересборка (`docker build`) нужна только при изменении `Dockerfile`.
* Если `docker compose` не работает — использовать `docker-compose` (через дефис).
* Для полной остановки и удаления контейнера используйте `docker compose down`.
