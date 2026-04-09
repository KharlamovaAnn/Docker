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
<img width="751" height="367" alt="Снимок экрана 2026-04-07 073849" src="https://github.com/user-attachments/assets/3be2a594-1bfa-4f40-abbb-11dfa2217ed3" /> <br1/>

<img width="745" height="335" alt="Снимок экрана 2026-04-07 073900" src="https://github.com/user-attachments/assets/fa79b2d3-1af7-4c30-95c1-e90ccb0a0572" /> <br2/>

#### Статус подов
<img width="750" height="199" alt="Снимок экрана 2026-04-07 073918" src="https://github.com/user-attachments/assets/f11ec864-376e-493d-be84-12755d2f7c36" /> <br3/>

```bash
# kubectl get pods
NAME                               READY   STATUS    RESTARTS   AGE
postgres-deploy-xxxxxxxx-xxxxx     1/1     Running   0          5m
backend-deploy-xxxxxxxx-xxxxx      1/1     Running   0          4m
frontend-deploy-xxxxxxxx-xxxxx     1/1     Running   0          4m
```

#### Работающее приложение
<img width="1851" height="979" alt="image" src="https://github.com/user-attachments/assets/ee4873a5-402f-4a01-8634-e7957c6946ce" /> <br4/>



База данных:

<img width="815" height="354" alt="image" src="https://github.com/user-attachments/assets/d4493722-f88f-4cca-94a1-b6eb4710fd3a" /> <br5/>


<img width="522" height="248" alt="image" src="https://github.com/user-attachments/assets/a9c5509a-e2b7-4538-8b30-2c527b4bbb75" /> <br6/>
