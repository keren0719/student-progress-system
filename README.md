# Student Progress System  
## Documentación de Arquitectura (arc42)

---

# 1. Introducción y Metas

## 1.1 Vista de Requerimientos

El sistema **Student Progress System** tiene como propósito permitir a los estudiantes visualizar y gestionar su progreso académico a lo largo de su carrera universitaria.

El sistema mostrará la **malla curricular organizada por semestres**, permitiendo identificar materias aprobadas, en curso y pendientes. Además, permitirá marcar materias como completadas y visualizar el avance general.

Adicionalmente, el sistema incluirá un módulo de evaluación que permitirá medir el **nivel académico del estudiante** basado en su conocimiento y no solo en las materias cursadas.

El sistema está diseñado para soportar **múltiples carreras**, cada una con su propia estructura curricular y áreas de conocimiento.

---

### Requerimientos funcionales

- RF1: Mostrar la malla curricular por semestres.
- RF2: Permitir visualizar materias aprobadas.
- RF3: Permitir marcar materias como completadas.
- RF4: Mostrar progreso académico (porcentaje o barra).
- RF5: Soportar múltiples carreras.
- RF6: Exponer API REST para gestión académica.
- RF7: Permitir interacción entre frontend y backend.
- RF8: Permitir realizar evaluaciones tipo test.
- RF9: Calcular y mostrar el nivel académico del estudiante.
- RF10: Evaluar al estudiante por áreas de conocimiento.
- RF11: Mostrar resultados por área (ej: programación, matemáticas).

---

### Requerimientos no funcionales

- RNF1: Arquitectura modular.
- RNF2: Escalabilidad.
- RNF3: Separación frontend/backend.
- RNF4: Usabilidad.
- RNF5: Portabilidad mediante Docker.

---

## 1.2 Metas de Calidad

- **Mantenibilidad**
- **Escalabilidad**
- **Portabilidad**
- **Usabilidad**

---

## 1.3 Stakeholders

| Stakeholder | Expectativa |
|------------|------------|
| Estudiantes | Ver su progreso académico y nivel |
| Docentes | Consultar desempeño académico |
| Equipo de desarrollo | Sistema escalable |
| Profesor | Evaluación de arquitectura |

---

# 2. Restricciones de la Arquitectura

- Uso obligatorio de Docker
- Backend en FastAPI (Python)
- Frontend en Next.js
- Comunicación mediante API REST
- Desarrollo incremental

---

# 3. Alcance y Contexto del Sistema

## 3.1 Contexto de Negocio

El sistema permite a los estudiantes visualizar su progreso académico y su nivel de conocimiento dentro de la universidad.

Flujo general:
Usuario → Sistema → Visualización del progreso y nivel académico

---

## 3.2 Contexto Técnico

Componentes:

- Frontend (Next.js)
- Backend (FastAPI)
- Comunicación HTTP (JSON)
- Contenedores Docker

---

# 4. Estrategia de Solución

Se adopta una arquitectura **cliente-servidor**:

- Frontend: interfaz de usuario
- Backend: lógica de negocio
- API REST: comunicación

El sistema incluye un **módulo de evaluación académica** que permitirá:

- Definir áreas de conocimiento por carrera
- Asociar preguntas a cada área
- Evaluar al estudiante mediante tests
- Calcular nivel académico general y por áreas

El nivel se calculará basado en:

- Materias aprobadas
- Resultados de evaluaciones
- Progreso por áreas

---

# 5. Vista de Construcción (Building Block View)

## Nivel 1
- Sistema Student Progress System

## Nivel 2
- Frontend
- Backend

## Nivel 3

### Frontend
- Interfaz de usuario
- Visualización de malla curricular
- Visualización de progreso
- Visualización de nivel académico

### Backend
- API REST
- Lógica de negocio
- Gestión académica
- Módulo de evaluación

---

# 6. Vista de Ejecución (Runtime View)

## Escenario: Consulta del progreso académico

1. El usuario accede al sistema.
2. El frontend muestra la selección de carrera.
3. El usuario selecciona su carrera.
4. El frontend solicita la malla curricular al backend.
5. El backend responde con datos en JSON.
6. El frontend muestra la malla.
7. El usuario visualiza su progreso.

---

## Escenario: Actualización de materias

8. El usuario marca una materia como aprobada.
9. El frontend envía la actualización.
10. El backend procesa.
11. El backend responde.
12. El frontend actualiza la vista.

---

## Escenario: Evaluación académica

13. El usuario accede a evaluación.
14. El frontend solicita preguntas.
15. El backend envía preguntas por áreas.
16. El usuario responde.
17. El frontend envía respuestas.
18. El backend evalúa resultados.
19. El backend calcula nivel académico.
20. El backend envía resultados.
21. El frontend muestra nivel y desempeño.

---

## Flujo general del sistema

Usuario  
↓  
Frontend (Next.js)  
↓ HTTP  
Backend (FastAPI)  
↓ JSON  
Frontend muestra datos  

---

## Flujo de actualización

Usuario marca materia  
↓  
Frontend envía actualización  
↓  
Backend procesa  
↓  
Respuesta  
↓  
Frontend actualiza  

---

## Flujo de evaluación

Usuario inicia test  
↓  
Frontend solicita preguntas  
↓  
Backend envía test  
↓  
Usuario responde  
↓  
Backend evalúa  
↓  
Frontend muestra nivel  

---

# 7. Vista de Despliegue (Deployment View)

- Contenedor Frontend (Node.js)
- Contenedor Backend (Python)

Arquitectura:

Usuario → Navegador → Frontend → Backend

Futuro:

- Base de datos PostgreSQL
- Autenticación

---

# 8. Conceptos Transversales

- Arquitectura cliente-servidor
- API REST
- Contenerización con Docker
- Separación de responsabilidades

---

# 9. Decisiones de Arquitectura

- FastAPI por rendimiento
- Next.js por UI moderna
- Docker por portabilidad
- Arquitectura modular

---

# 10. Requerimientos de Calidad

- Mantenibilidad
- Escalabilidad
- Portabilidad
- Rendimiento

---

# 11. Riesgos y Deuda Técnica

- No hay base de datos aún
- No hay autenticación
- No hay pruebas automatizadas
- No hay CI/CD

---

# 12. Glosario

| Término | Definición |
|--------|------------|
| Malla curricular | Estructura de materias |
| Progreso académico | Avance del estudiante |
| Nivel académico | Medición del conocimiento del estudiante |
| API REST | Comunicación HTTP |
| Docker | Contenedores |
| FastAPI | Backend Python |
| Next.js | Frontend React |

# 13. Prototipo
<img width="1661" height="876" alt="image" src="https://github.com/user-attachments/assets/6f845bb4-fadb-453e-9ddb-512fc1e991a5" />
<img width="1657" height="878" alt="image" src="https://github.com/user-attachments/assets/f207bf58-df52-4d97-9f25-1318bf1a5246" />
<img width="1667" height="870" alt="image" src="https://github.com/user-attachments/assets/64249f99-1b7b-4672-9406-deedd19d2ece" />
<img width="1652" height="870" alt="image" src="https://github.com/user-attachments/assets/06e40142-6546-4185-9377-7aa635515f50" />


