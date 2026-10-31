# DOCENTIA

Sistema de evaluación docente de la Corporación Universitaria Autónoma del Cauca.

| Carpeta     | Contenido                                   |
| ----------- | ------------------------------------------- |
| `backend/`  | API REST: Spring Boot, Java 21 y PostgreSQL |
| `frontend/` | Aplicación web: React con Vite              |

## Levantar todo con Docker

Solo necesitas Docker Desktop abierto:

```bash
docker compose up --build -d
```

La aplicación queda en <http://localhost:5173> y la API en <http://localhost:8090/api>. Los usuarios
de demo están en `backend/README.md`; la contraseña es `Docentia2026*`.

```bash
docker compose logs -f api   # ver el arranque del backend
docker compose down          # apagar y conservar los datos
docker compose down -v       # apagar y borrar los datos; al subir vuelve el seed
```

Para cambiar puertos o credenciales de desarrollo, copia `.env.example` como `.env`.

El recorrido de demo está en `frontend/docs/checklist-demo-sprint3.md`, y el contrato de la API en
`backend/docs/`.
