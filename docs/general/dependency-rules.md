# 🔗 Dependency Rules

## 📌 Objetivo

Este documento define lineamientos para gestionar dependencias dentro de una aplicación fullstack, con el fin de reducir acoplamiento, evitar complejidad innecesaria y mantener un sistema mantenible.

---

## 🧭 Principios generales

Las dependencias deben ser:

- **dirigidas** (una sola dirección)
- **explícitas**
- **controladas**

Un sistema bien estructurado evita dependencias implícitas o difíciles de rastrear.

---

## 🔁 Dirección de dependencias

Se recomienda mantener una dirección clara de dependencias:

- capas superiores pueden depender de capas inferiores
- capas inferiores no deben depender de capas superiores

Ejemplo general:


UI → Application → Domain → Infrastructure


---

## 🧩 Separación entre frontend y backend

Frontend y backend deben mantenerse desacoplados.

### Reglas

- el frontend no debe depender de la implementación interna del backend
- el backend no debe depender del frontend
- la comunicación debe realizarse mediante contratos claros (API, DTOs)

---

## 📦 Contratos y comunicación

Se recomienda definir contratos explícitos para la comunicación:

- DTOs
- esquemas de validación
- definiciones de API

### Reglas

- los contratos deben ser estables
- los cambios deben ser controlados
- evitar dependencias implícitas en la estructura de datos

---

## 🔗 Código compartido

El código compartido debe manejarse con cuidado.

### Recomendaciones

- compartir solo lo necesario
- priorizar contratos sobre lógica compartida
- evitar acoplar frontend y backend mediante código compartido

### Ejemplos válidos

- tipos (DTOs)
- validaciones simples
- utilidades genéricas

### Evitar

- lógica de negocio compartida sin control
- dependencias cruzadas entre capas

---

## 🧠 Dependencias dentro del frontend

Se recomienda:

- evitar dependencias entre features
- centralizar lo compartido en capas adecuadas
- mantener separación entre UI, estado y datos

Principio:

> Las partes reutilizables no deben depender de partes específicas.

---

## ⚙️ Dependencias dentro del backend

Se recomienda:

- separar por capas o dominios
- evitar dependencias circulares
- aislar lógica de negocio de infraestructura

---

## 🔄 Dependencias entre módulos

### Reglas

- evitar que un módulo dependa directamente de la implementación interna de otro
- si dos módulos necesitan compartir algo, debe moverse a una capa común
- mantener interfaces claras entre módulos

---

## ⚖️ Nivel de control

El control de dependencias debe ser proporcional al proyecto:

- proyectos pequeños → reglas simples
- proyectos grandes → mayor control y separación

---

## 🚫 Problemas comunes

- dependencias circulares
- acoplamiento entre módulos
- uso excesivo de código compartido
- dependencias implícitas
- mezcla de responsabilidades

---

## 🔄 Evolución

Las reglas de dependencia pueden refinarse conforme el proyecto crece.

Se recomienda:

- revisar dependencias periódicamente
- eliminar acoplamientos innecesarios
- reforzar contratos entre módulos

---

## 📌 Principio final

> Las dependencias mal gestionadas son una de las principales fuentes de complejidad en un sistema.