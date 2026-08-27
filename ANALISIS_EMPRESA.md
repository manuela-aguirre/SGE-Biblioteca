# Análisis de la Biblioteca COTECNOVA

## 1. Datos Generales

- **Nombre:** Biblioteca de la Corporación de Estudios Tecnológicos del Norte del Valle.
-**Tipo de Proyecto:** Sistema para la gestión de préstamos de material bibliográfico.
- **Opciones:** Gestión de libros, ejemplares, usuarios, préstamos, reservas, autores, editoriales, géneros y ubicaciones.
- **Usuarios:** La biblioteca COTECNOVA actualmente maneja los siguientes usuarios: 
-__**Usuario general:**__ Se conforman principalmente por los estudiantes, docentes, egresados y administrativos, los cuáles consultan el catálogo, revisan la disponibilidad del material, realiza reservan y consultan el historial de préstamos.
-__**Administrador/Bibliotecario**__ Gestiona los libros, ejemplares, usuarios, préstamos y ubicaciones, además, valida reservas y  genera informes. 
-**Tecnología del prototipo:** Se busca implementar conocimientos adquiridos en semestres anteriores, además, implementar las herramientas brindadas este semestre, inicialmente el proyecto se desarrolla con HTML, PHP y MySQL. 

## 2. Procesos Clave

El presente proyecto tiene como objetivo automatizar los procesos manuales que se manejan actualmente en la biblioteca COTECNOVA, ya que estos han generado una mala gestión del material bibliográfico disponible, uno de los principales problemas es la mala gestión del inventario. Por esto, los procesos clave encontrados después de analizar el funcionamiento de la biblioteca son: 

- **Préstamos:** Usuario/Bibliotecario ➔ Registro de préstamo ➔ Selección de ejemplar ➔ Seguimiento de fechas (préstamo, devolución, limite de prestamo) ➔ Entrega o vencimiento de la reserva. 
-**Reservas:** Usuario ➔ Selección de ejemplar disponible ➔ Reserva ➔ Validación por el administrador ➔ Cancelación, entrega o vencimiento de la reserva. 
- **Gestión de libros:** Autor → Libro → Editorial y Género.
- **Ejemplares:** Registro ➔ asignación de ubicación ➔ control de estado (disponible, prestado, dañado, dado de baja) 
- **Gestión de Usuarios:** Registro de usuario ➔ Asignación de rol ➔ Control de límite de préstamos según el rol.
-**Generación de Informes:** Inventario (por ejemplar) e informes de préstamos/reservas activos, con datos de usuarios y fechas. 

## 3. Entidades (Tablas)

- **Usuarios**
- **Préstamos**
- **Préstamo_Ejemplar**
- **Ejemplares**
- **Estado ejemplar**
-**Ubicación**
- **Libros**
- **Autores**
- **Autor_Libro**
- **Editorial**
- **Género**
- **Libro_Género**
- **Reservas**

## 4. Requerimientos Funcionales
- Registrar libros con título, autor, código de barras, número, signatura, tipo de marerial y ubicación. 
- Búsqueda avanzada por código de barras, autor, signatura o nombre del libro. 
- Consulta pública de disponibilidad (disponible, prestado, reservado) 
- Reserva de libros con nombre, documento, carrera, semestre y fecha de reclamo. 
- Registro y gestión de préstamos y devoluciones por parte del administrador. 
- Generación de informes de inventario y de préstamos/reservas. 
- Consulta de historial de préstamos y reservas por parte del usuario. 
- Edición y eliminación de libros del inventario. 

## 5. Requerimientos No Funcionales. 
- Accesibilidad desde computadores y celulares. 
- Interfaz intuitiiva para todos los perfiles de usuario. 
- Protección de datos personales conforme la normativa vigente (Ley 1581 de 2012, Decreto 1377 de 2013)
- Copias de seguridad diarias. 
- Disponibilidad 24/7 con tiempo de inactividad mínimo. 
- Autenticación de dos pasos para usuarios administrativos. 
- Soporte para gasta 100 usuarios simultáneos. 
- Compatibilidad con Chrome, Firefox y Opera. 

## 6. Reglas de Negocio relacionadas con el Reglamento de la Biblioteca. 
- **Plazos de préstamo:** Los prestamos pueden ser de largo plazo (15 días), mediano plazo (8 días) y corto plazo (3 días), se debe tener en cuenta que los docentes y administrativos tienen un plazo mayor. 
- **Multa por mora:** 1% de SMDLV por día de retraso en entrega del material bibliográfico. 
- **Pago del material:** En caso de daño de material, el usuario debe reponerlo con una edición igual o superior, o pagar su valor en un plazo de 15 días. 
- **Condonación de multas:** 100% por incapacidad médica, calamidad o reposición de material. 

## 7. Preguntas Clave
- **¿Qué información se guarda de un usuario?** Tipo_documento, Numero_documento, primer_nombre,segundo nombre, primer_apellido, segundo_apellido, correo, telefono, direccion, fecha_registro, clave, rol, limite_prestamos.
- **¿Qué información se guarda de un libro?** id.libro, titulo, descripcion, isbn, stock, portada_url.
- **¿Qué información se guarda de un ejemplar?** id_ejemplar, id_libro, id_editorial, edicion, medio_adquisicion, tipo_material, valor, f_registro, recibido_por, recibido_de, no_ejemplar, fecha_adquisicion, codigo_barras, signatura, paginas, anio_edicion, num_entrada, id_ubicacion, id_estado.
- **¿Cómo se relaciona un préstamo con un ejemplar?** Un préstamo se relaciona con uno o varios ejemplares mediante la tabla intermedia prestamo_ejemplar, que contiene los campos id_prestamo, id_ejemplar y estado. Esto permite que un préstamo incluya varios ejemplares y que un ejemplar pueda prestarse en distintos momentos.
- **¿Cómo se relaciona un libro con sus autores y géneros?** Mediante las tablas intermedias autor_libro y libro_genero, ya que un libro puede tener varios autores y pertenecer a varios géneros, y a la vez un autor puede escribir varios libros y un género puede agrupar varios libros.
