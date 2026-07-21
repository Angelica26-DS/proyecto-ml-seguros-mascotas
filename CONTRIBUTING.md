# Guía de colaboración del proyecto

## Proyecto

**Predicción del Precio de Seguros para Mascotas**  
**Bootcamp Data Science - The Bridge**

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

## Descripción de las ramas

### `main`

- Contiene únicamente versiones estables del proyecto.
- No se desarrolla directamente sobre esta rama.

### `develop`

- Rama de integración.
- Aquí se unen los cambios aprobados procedentes de las ramas `feature`.

### `feature/preprocessing`

Responsable del pipeline de preparación de datos:

- Limpieza de datos.
- Tratamiento de valores nulos.
- Ingeniería de variables.
- Codificación (Encoding).
- Escalado.
- División Train/Test.

### `feature/modeling`

Responsable del entrenamiento de modelos:

- Entrenamiento.
- Comparación de algoritmos.
- Optimización de hiperparámetros.
- Selección del mejor modelo.

### `feature/evaluation`

Responsable de:

- Evaluación del modelo.
- Métricas.
- Interpretabilidad.
- Persistencia.
- Resultados y conclusiones.

---

# Normas del equipo

- No trabajar directamente sobre `main`.
- No trabajar directamente sobre `develop`.
- Cada integrante desarrollará su trabajo únicamente sobre su rama `feature`.
- Todos los cambios se integrarán mediante **Pull Request**.
- Antes de realizar un merge, otro integrante revisará los cambios.
- El merge de `develop` hacia `main` solo se realizará cuando exista una versión estable del proyecto.

---

# Configuración del entorno de desarrollo

> **Importante**
>
> Esta configuración únicamente debe realizarse una vez después de clonar el repositorio.

## 1. Crear el entorno virtual

Desde la raíz del proyecto:

```bash
python -m venv .venv
```

---

## 2. Activar el entorno virtual

### Windows (Git Bash)

```bash
source .venv/Scripts/activate
```

### Windows (PowerShell)

```powershell
.\.venv\Scripts\Activate.ps1
```

Cuando el entorno esté activo aparecerá:

```text
(.venv)
```

---

## 3. Instalar las dependencias

```bash
pip install -r requirements.txt
```

---

## 4. Registrar el kernel de Jupyter

```bash
python -m ipykernel install --user --name=proyecto_ml_seguros --display-name "Proyecto ML - Seguros"
```

---

## 5. Seleccionar el kernel

Abrir cualquiera de los notebooks y seleccionar:

```
Proyecto ML - Seguros
```

---

## 6. Verificación

```python
import pandas as pd
import numpy as np

print("Entorno configurado correctamente.")
```

---

## Importante

- No subir nunca la carpeta `.venv`.
- No modificar `requirements.txt` sin comunicarlo previamente al equipo.
- Cada desarrollador trabajará siempre sobre su propia rama `feature`.

---

# Mantener la rama actualizada

Antes de comenzar una nueva sesión de trabajo:

## 1. Actualizar `develop`

```bash
git checkout develop
git pull origin develop
```

## 2. Cambiar a tu rama

```bash
git checkout feature/preprocessing
```

(Sustituir por `feature/modeling` o `feature/evaluation` según corresponda.)

## 3. Incorporar los últimos cambios

```bash
git merge develop
```

## 4. Verificar el estado

```bash
git status
```

Realizar este proceso:

- Antes de comenzar a trabajar.
- Antes de crear un Pull Request.
- Después de que otro compañero realice un merge sobre `develop`.

---

# Flujo de trabajo recomendado

1. Actualizar `develop`.
2. Cambiar a la rama `feature`.
3. Realizar los cambios.
4. Revisar el estado del repositorio.

```bash
git status
```

5. Añadir únicamente los archivos necesarios.

```bash
git add <archivo>
```

6. Verificar nuevamente.

```bash
git status
```

7. Crear el commit.

```bash
git commit -m "feat: descripción del cambio"
```

8. Subir la rama.

```bash
git push origin feature/preprocessing
```

9. Crear un Pull Request hacia `develop`.

10. Esperar la revisión del equipo antes del merge.

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

### Ejemplos

```text
feat: crear pipeline de preprocesamiento

fix: corregir tratamiento de valores nulos

docs: actualizar CONTRIBUTING

model: entrenar Random Forest

data: actualizar muestra del dataset

chore: reorganizar estructura del proyecto
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
│   │   ├── 01_preprocessing.ipynb
│   │   ├── 02_modeling.ipynb
│   │   └── 03_evaluation.ipynb
│   └── utils/
│
├── .gitignore
├── CONTRIBUTING.md
├── README.md
└── requirements.txt
```

---

# Checklist antes de realizar un commit

Antes de registrar cambios comprobar siempre:

- [ ] Ejecutar `git status`.
- [ ] Revisar que únicamente se subirán los archivos necesarios.
- [ ] Confirmar que `.venv` no aparece entre los cambios.
- [ ] Verificar que no se incluyen datos privados del proyecto.
- [ ] Revisar que los notebooks contienen únicamente los cambios previstos.
- [ ] Ejecutar nuevamente `git status`.

Solo después ejecutar:

```bash
git commit -m "..."
```

---

# Buenas prácticas

- Realizar commits pequeños y frecuentes.
- Escribir mensajes de commit claros y descriptivos.
- Probar el código antes de subir los cambios.
- Mantener el código y los notebooks organizados.
- Documentar las decisiones importantes.
- Comunicar cualquier cambio estructural antes de realizar un merge.
- Ante cualquier duda sobre Git o el flujo de trabajo, consultar con el equipo antes de continuar.

---

# Equipo de trabajo

| Integrante | Rama principal | Responsabilidad |
|------------|----------------|-----------------|
| **Angélica Sánchez** | `feature/preprocessing` | Preparación de datos, organización del proyecto y coordinación |
| **Hugo** | `feature/modeling` | Entrenamiento y optimización de modelos |
| **Carlos** | `feature/evaluation` | Evaluación, métricas, interpretación y documentación |