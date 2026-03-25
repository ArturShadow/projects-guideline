# 📁 Project Structure

## 📌 Objetivo

Este documento describe formas comunes de estructurar un proyecto fullstack, con el objetivo de mantener claridad, organización y escalabilidad.

No existe una única estructura válida. La organización debe adaptarse al tamaño, equipo y necesidades del proyecto.

---

## 🧭 Enfoque general

Se recomienda estructurar el proyecto separando claramente las responsabilidades principales del sistema:

- frontend
- backend
- comunicación (opcional)
- configuración e infraestructura

---

## 🧱 Estrategias de organización

Existen dos enfoques principales:

---

### 🔹 Monorepo

Todo el sistema vive en un solo repositorio.

#### Estructura típica
- `/project-root/`
- `/frontend/`
- `/backend/`
- `/docs/`
- `README.md`

#### Ventajas

- visión unificada del sistema
- cambios coordinados más simples
- configuración centralizada
- ideal para proyectos personales o equipos pequeños

#### Consideraciones

- puede crecer en complejidad con el tiempo
- requiere disciplina en organización

---

### 🔹 Multi-repo

Frontend y backend viven en repositorios separados.

#### Ejemplo

- frontend-repo
- backend-repo

#### Ventajas

- separación clara entre sistemas
- despliegues independientes
- escalabilidad organizacional

#### Consideraciones

- coordinación entre repositorios
- manejo de versiones entre servicios
- mayor overhead inicial

---

## 🧩 Estructura interna (referencial)

### Frontend

Se recomienda organización por features:
- frontend/  
- src/  
- app/  
- core/  
- shared/  
- features/

Ver detalle: [Feature Structure](../frontend/feature-structure.md)

---

### Backend

Se recomienda separar por capas o dominios:
- backend/  
- src/  
- controllers/  
- services/  
- models/  
- routes/

La estructura puede variar según el framework o patrón utilizado.

---

## 📦 Código compartido

En algunos proyectos puede existir código compartido.

### En monorepo
- /shared/

### En multi-repo

- paquete independiente (ej: npm package)
- librería compartida

#### Recomendaciones

- compartir solo contratos claros y estables
- evitar acoplamiento innecesario
- no compartir lógica de negocio sensible entre frontend y backend

---

## ⚙️ Configuración

Se recomienda centralizar configuraciones:
- /config/  
- .env

Ejemplos:

- variables de entorno
- configuración de servicios
- settings globales

---

## 📚 Documentación

Se recomienda mantener documentación dentro del proyecto:
- /docs/

- arquitectura
- decisiones técnicas
- guías

---

## ⚖️ Nivel de complejidad

La estructura debe ser proporcional al proyecto:

- proyectos pequeños → estructura simple
- proyectos medianos → modularización
- proyectos grandes → separación más estricta

---

## 🚫 Problemas comunes

- mezclar frontend y backend sin control
- duplicar código sin necesidad
- estructuras innecesariamente complejas
- falta de consistencia entre módulos

---

## 🔄 Evolución

La estructura puede cambiar conforme el proyecto crece.

Se recomienda:

- comenzar con una estructura simple
- modularizar progresivamente
- reevaluar la estrategia (monorepo vs multi-repo) según el crecimiento

---

## 📌 Principio final

> La estructura debe facilitar el entendimiento del sistema, no complicarlo.