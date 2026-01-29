# Concepto: Red Social con Chats Ramificados (BranchChat)

## 1. La Idea Central: Conversaciones en Árbol
En las apps de mensajería tradicionales, las conversaciones múltiples sobre diferentes temas se mezclan en un solo hilo lineal, causando confusión. 
**BranchChat** permite que cualquier mensaje en un chat se convierta en el punto de partida de una nueva "rama"

### Funcionalidades Clave
1.  **Chat Principal Lineal**: El flujo normal de conversación.
2.  **Creación de Ramas**: Al responder a un mensaje específico, el usuario puede elegir "Responder aquí" (lineal) o "Abrir nueva Rama" (divergente).
3.  **Visualización de Árbol**: Una vista o mapa mental que muestra cómo las conversaciones se han bifurcado desde el hilo original.
4.  **Colapso/Expansión**: Los usuarios pueden minimizar ramas que no les interesan.
5.  **Tags por Rama**: Cada rama puede tener un título o etiqueta autogenerada (ej. "Planificación Vacaciones", "Discusión sobre Película").

## 2. Stack Tecnológico Sugerido

### Backend (API & Lógica)
*   **Lenguaje**: Python 3.11+
*   **Framework**: **FastAPI** 
    *   *Por qué*: Alto rendimiento, soporte nativo de asincronía (crucial para WebSockets y chats en tiempo real), fácil documentación con OpenAPI.
*   **Base de Datos**: **PostgreSQL**
    *   *Por qué*: Manejo robusto de relaciones complejas (mensajes padres/hijos, estructuras de árbol con CTEs recursivos).
*   **Real-time**: **WebSockets** (nativo en FastAPI) + **Redis** (para manejo de pub/sub de mensajes).

### Frontend (Interfaz de Usuario)
*   **Framework**: **React** (con Vite) o **Next.js**.
    *   *Sugerencia*: **React + Vite** para una SPA (Single Page Application) rápida y fluida.
*   **Estilos**: **Tailwind CSS**.
    *   *Por qué*: Desarrollo rápido, diseño moderno y consistente.
*   **Visualización de Grafos**: Librería como `react-flow` o `d3.js` para visualizar el árbol de mensajes.

## 3. Estructura de Datos (Boceto)

**Modelo Message:**
- `id`: UUID
- `content`: Text/Media
- `parent_message_id`: UUID (null si es el inicio)
- `branch_id`: UUID (identificador de la rama visual)
- `created_at`: Datetime
- `author_id`: UUID

## 4. Próximos Pasos
1.  Configurar entorno Python.
2.  Inicializar proyecto React.
3.  Definir endpoints de API básicos.
