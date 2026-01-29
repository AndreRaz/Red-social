# BranchChat: Red Social con Chats Ramificados

Bienvenido al repositorio de **BranchChat**. Este proyecto explora un nuevo paradigma de mensajería donde las conversaciones pueden bifurcarse en ramas temáticas, permitiendo discusiones organizadas y profundas sin perder el hilo principal.

Intento de red social basada en "ramas" para intentar simular una conversación de lenguaje natural.

##  Concepto
Para más detalles sobre la arquitectura y funcionalidades, consulta el documento de [IDEAS](./IDEAS.md).

## Stack Tecnológico
- **Backend:** Python (FastAPI)
- **Base de Datos:** PostgreSQL
- **Frontend:** React / Next.js
- **Tiempo Real:** WebSockets + Redis

##  Configuración del Entorno de Desarrollo

### Requisitos Previos
- Python 3.11+
- Node.js 18+
- PostgreSQL
- Redis

### Backend (Python)
1. Clonar el repositorio.
2. Crear un entorno virtual:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   # o
   venv\Scripts\activate     # Windows
   ```
3. Instalar dependencias:
   ```bash
   pip install -r requirements.txt
   ```
4. Iniciar el servidor (cuando esté implementado):
   ```bash
   uvicorn backend.main:app --reload
   ```

### Frontend
*(Pendiente de inicialización en la carpeta `/frontend`)*

##  Contribuciones
Las ideas son bienvenidas. Por favor abre un Issue para discutir cambios mayores.
