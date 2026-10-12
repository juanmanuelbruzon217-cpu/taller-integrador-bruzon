# Calculadora de Promedio — Taller integrador individual

**Estudiante:** Juan Manuel Bruzon
**Curso:** Buenas Prácticas de Desarrollo de Software
**Institución:** Corporación Universidad de la Costa
**Taller:** Integrador individual · Cortes 1 y 2

## 🌐 Sitio publicado

https://taller-integrador-bruzon.netlify.app

## 📌 Descripción

Página web que calcula el promedio de tres notas e indica si el resultado es **aprobado** (promedio mayor o igual a 3.0) o **reprobado**.

El objetivo del taller no fue cambiar lo que la página hace, sino **auditar y corregir cómo está escrita y versionada**, aplicando las buenas prácticas vistas en clase.

## 🛠️ Tecnologías

- HTML5
- CSS3
- JavaScript
- Git y GitHub (control de versiones)
- Netlify (despliegue)

## 📁 Estructura del proyecto

```
taller-integrador-bruzon/
├── index.html    # Estructura de la página y lógica del cálculo
├── estilos.css   # Estilos del sitio
└── README.md     # Documentación y tabla de hallazgos
```

## 🔍 Tabla de hallazgos de la auditoría

| # | Defecto encontrado | Por qué era un problema | Cómo lo corrigió |
|---|---|---|---|
| 1 | Archivo HTML llamado `Mi Pagina De Notas.HTML` | Tenía espacios, mayúsculas y la extensión en mayúsculas. Los espacios rompen las URLs y los servidores Linux distinguen mayúsculas. Netlify además busca `index.html` | Se renombró a `index.html` |
| 2 | Archivo CSS llamado `Estilos Del Sitio.CSS` | Mismo problema de espacios y mayúsculas, y el `href` del HTML quedaba con espacios | Se renombró a `estilos.css` y se actualizó el enlace en el HTML |
| 3 | Variables `x`, `a`, `b`, `c` | Una sola letra no indica qué almacenan; obliga a leer todo el código para entenderlas | Se renombraron a `cantidadNotas`, `nota1`, `nota2`, `nota3` |
| 4 | Variable `TempValue2` | Usa PascalCase en vez de camelCase, y "Temp" y "2" no describen su contenido. Además era global sin necesidad | Se renombró a `promedio` y se declaró dentro de la función |
| 5 | Función `calc()` | Nombre abreviado que no dice qué calcula | Se renombró a `calcularPromedio()` |
| 6 | IDs `n1`, `n2`, `n3`, `r`, `r2` y clase `cont1` | Nombres crípticos que no indican qué elemento es cada uno, y el CSS dependía de ellos | Se renombraron a `nota1`, `nota2`, `nota3`, `resultadoPromedio`, `resultadoEstado` y `contenedor`, en HTML, JS y CSS |
| 7 | Título de la pestaña `pagina` | No describe el sitio ni ayuda al usuario a identificar la pestaña | Se cambió a `Calculadora de promedio` |
| 8 | Líneas sin función: `let data1 = []`, tres `console.log` de depuración y el bloque comentado `calcularAntiguo` | Código muerto que ensucia el archivo y confunde sobre qué se usa realmente | Se eliminaron |

## 🌿 Flujo de trabajo con Git

### Ramas

| Rama | Propósito |
|---|---|
| `main` | Versión estable y publicada. Desplegada en Netlify |
| `dev` | Integración de cambios. Protegida: exige Pull Request |
| `pruebas` | Rama de pruebas |
| `feature/correcciones` | Rama de trabajo con las correcciones de la auditoría |

### Convención de commits

| Prefijo | Uso |
|---|---|
| `chore:` | Renombrar archivos y tareas de mantenimiento |
| `refactor:` | Renombrar variables, funciones, IDs y clases sin cambiar el comportamiento |
| `style:` | Formato, indentación y eliminación de líneas sobrantes |
| `fix:` | Corrección puntual (título de la pestaña) |
| `docs:` | Documentación (este README) |

### Proceso seguido

1. Se subieron los archivos originales sin corregir a `main`.
2. Se crearon `dev` y `pruebas` a partir de `main`.
3. Se trabajó en `feature/correcciones`, con commits agrupados por tipo de cambio.
4. Pull Request de `feature/correcciones` hacia `dev`.
5. Protección de la rama `dev`.
6. Pull Request de `dev` hacia `main` y despliegue en Netlify.

