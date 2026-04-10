# Лабораторной работа №4.1. Частные облачные системы
## Вариант 18: Membership System (Учет участников клуба/программы)

### 1. Цель работы
Применить полученные знания по созданию и развертыванию трехзвенного приложения (Frontend + Backend + Database) в кластере Kubernetes. Научиться организовывать взаимодействие между микросервисами.

### 2. Описание архитектуры
Приложение состоит из трех основных компонентов:
1.  **Database (PostgreSQL)**: Хранит данные об участниках клуба (ФИО, уровень подписки, дата окончания).
2.  **Backend (FastAPI)**: Предоставляет REST API для выполнения CRUD-операций с базой данных. Обрабатывает запросы от фронтенда и взаимодействует с Postgres через SQLAlchemy.
3.  **Frontend (Streamlit)**: Пользовательский интерфейс, позволяющий добавлять новых участников и просматривать список существующих. Общается с бэкендом через HTTP-запросы.

**Схема взаимодействия:**
`Streamlit (User UI) <-> FastAPI (Business Logic) <-> PostgreSQL (Data Storage)`

В Kubernetes взаимодействие настроено через DNS-имена сервисов (`backend-service`, `postgres-service`).

### 3. Технологический стек
- **Backend**: Python, FastAPI, SQLAlchemy, Pydantic, Uvicorn.
- **Frontend**: Python, Streamlit, Pandas, Requests.
- **Database**: PostgreSQL 13.
- **Orchestration**: Docker, Kubernetes.

### 4. Листинги кода

#### Backend: `src/backend/main.py`
```python
# (Код Backend API)
# См. файл src/backend/main.py
```

#### Frontend: `src/frontend/app.py`
```python
# (Код Frontend UI)
# См. файл src/frontend/app.py
```

#### Dockerfiles
**Backend:**
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

**Frontend:**
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 8501
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

#### Kubernetes Manifest: `k8s/fullstack.yaml`
```yaml
# (Полный манифест Deployment и Service)
# См. файл k8s/fullstack.yaml
```

### 5. Скриншоты выполнения

#### Сборка образов
<img width="935" height="428" alt="Снимок экрана 2026-04-09 225835" src="https://github.com/user-attachments/assets/260acfd8-cb66-4bd4-ac9f-d01699e2eaf5" /> <br1/>

<img width="937" height="430" alt="Снимок экрана 2026-04-09 225907" src="https://github.com/user-attachments/assets/6971b54d-256c-460c-8906-0d8e5ea49932" /> <br2/>

#### Статус подов
<img width="642" height="186" alt="Снимок экрана 2026-04-09 225929" src="https://github.com/user-attachments/assets/552be306-1473-48f0-acd1-41ac6b94ece2" /> <br3/>

```bash
# kubectl get pods
NAME                               READY   STATUS    RESTARTS   AGE
postgres-deploy-xxxxxxxx-xxxxx     1/1     Running   0          5m
backend-deploy-xxxxxxxx-xxxxx      1/1     Running   0          4m
frontend-deploy-xxxxxxxx-xxxxx     1/1     Running   0          4m
```

#### Работающее приложение
<img width="1851" height="979" alt="image" src="https://github.com/user-attachments/assets/ee4873a5-402f-4a01-8634-e7957c6946ce" /> <br4/>

<img width="480" height="121" alt="Снимок экрана 2026-04-10 112457" src="https://github.com/user-attachments/assets/11dba119-15bb-4109-9466-e5fa27a4422c" />


База данных:

<img width="1019" height="201" alt="image" src="https://github.com/user-attachments/assets/fce9cb76-bc26-414e-acae-2cac33843e94" /> <br5/>


