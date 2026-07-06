# Guía de colaboración del proyecto

## Proyecto

**Predicción del Precio de Seguros para Mascotas**  
Bootcamp Data Science - The Bridge

Este documento establece las normas de trabajo del equipo para mantener un desarrollo ordenado, minimizar conflictos y facilitar la integración del código.

---

# Flujo de trabajo (Git Flow)

El proyecto utiliza el siguiente flujo de ramas:

```
main
│
└── develop
      ├── feature/preprocessing
      ├── feature/modeling
      └── feature/evaluation
```

### Descripción de las ramas

**main**
- Contiene únicamente versiones estables del proyecto.
- No se desarrolla directamente sobre esta rama.

**develop**
- Rama de integración.
- Aquí se unen los cambios aprobados de las ramas `feature`.

**feature/preprocessing**
- Limpieza de datos.
- Tratamiento de valores nulos.
- Eliminación de duplicados.
- Ingeniería de variables.
- Codificación (Encoding).
- Escalado.
- División Train/Test.

**feature/modeling**
- Entrenamiento de modelos.
- Comparación de algoritmos.
- Optimización de hiperparámetros.
- Selección del mejor modelo.

**feature/evaluation**
- Evaluación de modelos.
- Métricas.
- Interpretabilidad.
- Persistencia del modelo.
- Resultados y conclusiones.

---

# Normas del equipo

- No trabajar directamente sobre `main`.
- No trabajar directamente sobre `develop`.
- Cada integrante desarrollará su trabajo únicamente en su rama `feature`.
- Antes de comenzar una tarea, actualizar la rama desde `develop`.
- Todos los cambios se integrarán mediante **Pull Request**.
- Antes de realizar el merge, otro integrante revisará los cambios.
- El merge de `develop` hacia `main` solo se realizará cuando exista una versión estable del proyecto.

---

# Mantener la rama actualizada

Antes de comenzar una nueva sesión de trabajo:

### 1. Actualizar `develop`

```bash
git checkout develop
git pull origin develop
```

### 2. Cambiar a tu rama de trabajo

```bash
git checkout feature/preprocessing
```

(Sustituir por `feature/modeling` o `feature/evaluation` según corresponda).

### 3. Incorporar los últimos cambios

```bash
git merge develop
```

### 4. Verificar el estado

```bash
git status
```

Realiza este proceso:

- Antes de comenzar a trabajar.
- Antes de crear un Pull Request.
- Después de que otro compañero haga un merge sobre `develop`.

---

# Flujo de trabajo recomendado

1. Actualizar `develop`.
2. Cambiar a tu rama `feature`.
3. Realizar los cambios.
4. Registrar los cambios:

```bash
git add .
git commit -m "feat: descripción del cambio"
```

5. Subir la rama:

```bash
git push origin feature/preprocessing
```

6. Crear un Pull Request hacia `develop`.
7. Esperar la revisión del equipo antes del merge.

---

# Convención de commits

| Prefijo | Uso |
|----------|-----|
| `feat:` | Nueva funcionalidad |
| `fix:` | Corrección de errores |
| `docs:` | Documentación |
| `refactor:` | Mejora del código |
| `model:` | Entrenamiento o evaluación de modelos |
| `data:` | Cambios relacionados con los datos |
| `chore:` | Configuración o mantenimiento |

Ejemplos:

```text
feat: crear pipeline de preprocesamiento

fix: corregir tratamiento de valores nulos

docs: actualizar README

model: entrenar Random Forest

data: añadir muestra del dataset

chore: actualizar estructura del proyecto
```

---

# Organización del proyecto

```
proyecto-ml-seguros-mascotas/
│
├── src/
│   ├── data_sample/
│   ├── img/
│   ├── models/
│   ├── notebooks/
│   └── utils/
│
├── .gitignore
├── CONTRIBUTING.md
├── README.md
├── main.ipynb
└── requirements.txt
```

---

# Buenas prácticas

- Realizar commits pequeños y frecuentes.
- Escribir mensajes de commit claros y descriptivos.
- Probar el código antes de subir los cambios.
- Mantener el código y los notebooks organizados.
- Comunicar al equipo cualquier cambio importante antes de realizar un merge.
- Si existe alguna duda sobre Git o el flujo de trabajo, consultar con el equipo antes de continuar.

---

# Equipo de trabajo

| Integrante | Rama principal | Responsabilidad |
|------------|----------------|-----------------|
| **Angélica Sánchez** | `feature/preprocessing` | Preparación de datos, organización del proyecto y coordinación |
| **Hugo** | `feature/modeling` | Entrenamiento y optimización de modelos |
| **Carlos** | `feature/evaluation` | Evaluación, métricas, interpretación y documentación |