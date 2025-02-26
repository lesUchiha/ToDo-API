# SwiftTask API - Documentación Oficial

## Introducción
SwiftTask API es una API RESTful diseñada para la gestión eficiente de tareas. Permite a los usuarios crear, actualizar y eliminar tareas de manera individualizada según su dirección IP.

## Base URL
```
https://tu-dominio.com/api/v1/
```

## Autenticación
Esta API usa direcciones IP para identificar a cada usuario, por lo que no es necesario registrarse.

---

## **Endpoints**

### 1. Obtener todas las tareas
**GET** `/tasks`

**Respuesta Exitosa (200):**
```json
[
    {
        "id": "1",
        "titulo": "Terminar proyecto",
        "descripcion": "Finalizar documentación de SwiftTask API",
        "completado": false,
        "fecha_creacion": "2025-02-25T12:00:00Z"
    }
]
```

---

### 2. Crear una nueva tarea
**POST** `/tasks`

**Cuerpo de la solicitud:**
```json
{
    "titulo": "Nueva tarea",
    "descripcion": "Descripción de la tarea"
}
```

**Respuesta Exitosa (201):**
```json
{
    "id": "2",
    "titulo": "Nueva tarea",
    "descripcion": "Descripción de la tarea",
    "completado": false,
    "fecha_creacion": "2025-02-25T13:00:00Z"
}
```

---

### 3. Actualizar una tarea
**PUT** `/tasks/{id}`

**Cuerpo de la solicitud:**
```json
{
    "titulo": "Tarea actualizada",
    "descripcion": "Nueva descripción",
    "completado": true
}
```

**Respuesta Exitosa (200):**
```json
{
    "id": "2",
    "titulo": "Tarea actualizada",
    "descripcion": "Nueva descripción",
    "completado": true,
    "fecha_creacion": "2025-02-25T13:00:00Z"
}
```

---

### 4. Eliminar una tarea
**DELETE** `/tasks/{id}`

**Respuesta Exitosa (200):**
```json
{
    "message": "Tarea eliminada exitosamente"
}
```

---

### 5. Notificaciones (Opcional)
**GET** `/notifications`

**Respuesta Exitosa (200):**
```json
[
    {
        "id": "1",
        "mensaje": "Tienes 3 tareas pendientes",
        "fecha": "2025-02-25T15:00:00Z"
    }
]
```

---

## **Errores Comunes**

| Código | Descripción |
|--------|-------------|
| 400 | Solicitud inválida |
| 404 | Tarea no encontrada |
| 500 | Error interno del servidor |

---

## **Integración en Python**

Ejemplo de uso con `requests`:
```python
import requests

API_URL = "https://tu-dominio.com/api/v1/tasks"

# Crear una tarea
data = {"titulo": "Aprender FastAPI", "descripcion": "Crear un proyecto con FastAPI"}
response = requests.post(API_URL, json=data)
print(response.json())
```

---

## **Conclusión**
SwiftTask API es una solución eficiente y fácil de integrar en cualquier aplicación que requiera gestión de tareas. Si tienes alguna duda, contáctanos.

