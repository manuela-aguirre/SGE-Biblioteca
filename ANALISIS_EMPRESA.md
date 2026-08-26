# Análisis de la Biblioteca COTECNOVA

## 1. Datos Generales

- **Nombre:** Biblioteca COTECNOVA.
- **Opciones:** Gestión de libros, ejemplares, usuarios, préstamos, reservas, autores, editoriales, géneros y ubicaciones.
- **Usuarios:** Personas registradas en la biblioteca y personal encargado de la administración.

## 2. Procesos Clave

- **Préstamos:** Usuario → Préstamo → Ejemplar → Devolución.
- **Gestión de libros:** Autor → Libro → Editorial y Género.
- **Ejemplares:** Registro → Ubicación → Préstamo → Devolución.
- **Reservas:** Usuario → Reserva → Libro o material solicitado.

## 3. Entidades (Tablas)

- **Usuarios**
- **Préstamos**
- **Préstamo_Ejemplar**
- **Ejemplares**
- **Ubicación**
- **Libros**
- **Autores**
- **Autor_Libro**
- **Editorial**
- **Género**
- **Libro_Género**
- **Reservas**

## 4. Preguntas Clave

- **¿Qué información se guarda de un usuario?**
- **¿Qué información se guarda de un libro?**
- **¿Cómo se relaciona un préstamo con un ejemplar?**

## Completar el Formato (15 min)

### Preguntas guía:

- **¿Qué campos debe tener la tabla de usuarios?**

  `id_usuario`, `nombres`, `apellidos`, `telefono`, `direccion`, `fecha_registro`, `clave`, `rol`, `limite_prestamos`.

- **¿Qué campos debe tener la tabla de libros?**

  `id_libro`, `titulo`, `descripcion`, `portada_url`, `isbn`.

- **¿Qué campos debe tener la tabla de ejemplares?**

  `id_ejemplar`, `id_libro`, `edicion`, `medio_adquisicion`, `tipo_material`, `valor`, `f_registro`, `recibido_por`, `recibido_de`, `no_ejemplar`, `fecha_adquisicion`, `codigo_barras`, `signatura`, `paginas`, `anio_edicion`, `num_entrada`.

- **¿Cómo se relaciona un préstamo con un ejemplar?**

  Un préstamo se relaciona con uno o varios ejemplares mediante la tabla `prestamo_ejemplar`, que contiene los campos `id_prestamo`, `id_ejemplar` y `estado`.
