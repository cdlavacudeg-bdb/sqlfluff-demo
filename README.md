# SQLFluff – Configuración Corporativa (Oracle)

## 📌 Descripción

Este repositorio contiene una configuración estándar de **SQLFluff** orientada a
entornos **DevOps / SRE** para garantizar **calidad, legibilidad y consistencia**
en código SQL, con foco inicial en **Oracle Database**.

La configuración está diseñada para:
- Uso local por desarrolladores
- Integración en pipelines CI/CD
- Reducción de deuda técnica en SQL legacy
- Evitar discusiones de estilo en code reviews

---

## 🎯 Objetivos de la configuración

- Estandarizar el formato SQL a nivel corporativo
- Detectar errores de legibilidad y ambigüedad
- Forzar buenas prácticas (ej. evitar `SELECT *`)
- Permitir autofix seguro (`sqlfluff fix`)
- Minimizar ruido innecesario en CI

---

## 🗄️ Dialecto y contexto

| Parámetro | Valor |
|----------|------|
| Dialecto | Oracle |
| Templater | raw |
| Longitud máxima | 120 caracteres |
| Uso | SQL estático (vistas, scripts, reportes) |

---

## 🔤 Capitalización

| Elemento | Política |
|--------|----------|
| Keywords | MAYÚSCULAS |
| Funciones | MAYÚSCULAS |
| Tablas / columnas | minúsculas |

Ejemplo esperado:

```sql
SELECT
    emp_id,
    emp_name,
    salary
FROM hr.employees
WHERE salary > 10000;
``
