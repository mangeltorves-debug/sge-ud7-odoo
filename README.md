Configuración Inicial del Sistema (Módulos y Catálogo)
* **Módulos Instalados:** todos los de venta
* **Datos de la Compañía (Ajustes):**
    * Nombre ficticio: *Torves*
    * Identificador fiscal (NIF/VAT): `ESA12345674`
    * Personalización del diseño de documentos (plantillas profesionales, colores corporativos y pie con datos fiscales).
* **Catálogo Comercial (4 Ítems):**
    * *Tabla  de madera mesa* .
    * *Pata mesa de hierro* .
    * *Lampara de mesa negra* .
    * *Bombilla led* .
* **Cartera de Clientes:**
    * *Colchones Paco S.A.* (Cliente Empresa / Persona jurídica con NIF).
    * *Kike Montilla* (Cliente Particular / Individuo).
    * Control de Acceso, Usuarios y Principio de Mínimo Privilegio

Siguiendo las políticas de seguridad en sistemas ERP, se han configurado usuarios específicos aplicando estrictamente el principio de mínimo privilegio 
(documentado en profundidad en usuarios-grupos-permisos.md):

Estela (Comercial Junior): Usuario interno con permisos en Ventas limitados a documentos propios. Sin acceso a contabilidad ni permisos de eliminación de registros.

Gervasio (Responsable de Ventas): Usuario interno con perfil Administrador en Ventas, con visibilidad global sobre las operaciones de todo el equipo comercial.

Miguel Ángel (Administrador General y Técnico): Superusuario con plenos derechos de gestión global, mantenimiento de servidores y configuración de parámetros.

Grupo de Seguridad Personalizado: Creado desde el modo desarrollador bajo la denominación Torves Tech / Comercial Junior, configurando de forma 
granular los derechos de acceso sobre modelos (Lectura, Escritura, Creación permitidas; Eliminación denegada).