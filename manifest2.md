В WEB-проект проекте будут созданы такие компоненты:
1. Фротэнд
2. Бэкенд
3. Сервис авторизации
4. Сервис логирования
5. Модуль администрирования

Каждый компонент описывается в **JSON** с обязательными полями:
- `name` – уникальное имя.  
- `type` (`web`, `service`, `module`).  
- `description` – назначение компонента.  
- `owners` – ответственные.  
- `interfaces` – как компонент общается с другими.  
- `dependencies` – от каких сервисов зависит.  
- `health_check` – эндпоинт для мониторинга.  
- `deployment` – способ развертывания.  

Связи между компонентами:

Frontend → (HTTPS) → Backend  
Backend → (gRPC) → Auth-Service  
Backend → (Kafka) → Logging-Service  
Admin-Module → (HTTP) → Backend  
Admin-Module → (SQL) → Database  


В связях должно быть явное описание протокола (REST, gRPC, WebSocket, Kafka).  
