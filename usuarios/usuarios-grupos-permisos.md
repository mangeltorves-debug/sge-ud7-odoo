Gestión de Usuarios, Grupos y Permisos en Odoo SGE

Este documento detalla la política de control de acceso y seguridad implementada en nuestra instancia de Odoo para el Sistema de Gestión Empresarial (SGE), aplicando estrictamente el principio de mínimo privilegio: cada usuario cuenta únicamente con los permisos estrictamente necesarios para desempeñar las funciones de su puesto de trabajo, evitando exposiciones innecesarias de datos corporativos o financieros.

1. Relación de Usuarios Internos y Asignación de Puestos

Para cumplir con la estructura organizativa y los requisitos de la práctica, se han dado de alta tres usuarios internos, cada uno equipado con su respectiva fotografía o avatar, correo electrónico de acceso y permisos adaptados a su rol operativo:

Estela (Comercial Junior): Configurada como usuaria interna con permisos en el módulo de Ventas limitados a la opción «Usuario: solo mostrar documentos propios». Gracias a esta restricción, Estela puede gestionar y crear sus propios presupuestos y pedidos, pero carece por completo de visibilidad sobre las operaciones de sus compañeros y no posee acceso al módulo de Facturación ni Contabilidad.

Gervasio (Responsable de Ventas): Configurado como usuario interno con perfil de Administrador en el módulo de Ventas. Su rol le otorga visibilidad global sobre todos los presupuestos y operaciones comerciales de la compañía, permitiéndole supervisar al equipo y validar ofertas de mayor envergadura sin interferir en los asientos contables puros.

Miguel Ángel (Administrador General y Técnico / Tu Nombre): Configurado como superusuario administrador del sistema con plenos derechos sobre todos los módulos instalados (Ventas, Inventario, Facturación y Ajustes). Su función abarca la administración global de la plataforma, la gestión de copias de seguridad, la creación de grupos y el mantenimiento técnico del entorno Odoo.

2. Análisis del Tipo de Usuario Asignado

En la arquitectura de Odoo, la clasificación de los usuarios determina su nivel de interacción con la base de datos y su impacto en las licencias del sistema:

Usuarios Internos: Son empleados de la organización que operan directamente dentro del back-office de Odoo para realizar tareas administrativas, comerciales o de gestión diaria. Todos nuestros usuarios creados (Estela, Gervasio y Miguel Ángel) pertenecen a esta categoría, ya que requieren acceso operativo a las aplicaciones del SGE.

Usuarios de Portal: Están destinados a clientes externos o proveedores. Permiten acceder a una vista web simplificada y segura para consultar sus propias facturas, albaranes, presupuestos o estado de pedidos sin interactuar con la gestión interna de la empresa. (Por ejemplo, se puede habilitar un usuario portal para el cliente Innovaciones Andaluzas S.A.).

Usuarios Públicos: Corresponden a visitantes anónimos que navegan por la tienda online corporativa o el sitio web público de la empresa, sin acceso a datos privados ni herramientas de gestión interna.

3. Configuración del Grupo Propio y Derechos de Acceso (Modo Desarrollador)

Para demostrar la capacidad de personalización avanzada en Odoo, se ha activado el modo desarrollador desde los ajustes generales y se ha creado un grupo de seguridad propio adaptado a la jerarquía de la empresa.

Nombre del Grupo: Torves Tech / Comercial Junior

Grupos Heredados: El grupo hereda de forma natural de los permisos base de usuario interno de Ventas, asegurando la compatibilidad con el núcleo del sistema.

Derechos de Acceso sobre Modelos (L/E/C/B):
Para el modelo de presupuestos y clientes, se han configurado los privilegios específicos desglosados en las cuatro casillas de control:

Lectura (Read): Marcada (permite consultar los registros autorizados).

Escritura (Write): Marcada (permite modificar los datos existentes permitidos).

Creación (Create): Marcada (permite dar de alta nuevos registros comerciales).

Eliminación (Unlink / Delete): Desmarcada (aplica una restricción estricta de seguridad impidiendo que este perfil pueda borrar registros críticos del sistema).

Asignación: Este grupo propio ha sido asignado específicamente al usuario Estela para reforzar su perfil operativo limitado.

4. Demostración y Pruebas de Funcionamiento de los Permisos

Para validar que las restricciones de seguridad operan correctamente aplicando el principio de mínimo privilegio, se han realizado pruebas cruzadas iniciando sesión con cada perfil en ventanas de navegación independientes:

Prueba con Estela (Comercial): Al iniciar sesión con sus credenciales, se comprobó que al acceder al módulo de Ventas únicamente visualiza los presupuestos creados por ella misma, ocultándose los registros de Gervasio u otros comerciales. Al intentar buscar el menú de Contabilidad o Facturación, Odoo muestra una restricción de acceso impidiendo su visualización. Asimismo, al intentar eliminar un contacto de la base de datos, el sistema bloquea la acción debido a la desactivación del permiso de borrado en su grupo.

Prueba con Gervasio (Responsable de Ventas): Al iniciar sesión, el sistema le permite visualizar la lista completa de presupuestos de todos los comerciales de la empresa, validando con éxito su rol de supervisión global y permitiéndole aprobar operaciones comerciales de equipo.

Prueba con Miguel Ángel (Administrador): Al iniciar sesión con el perfil principal, se confirma el acceso total a la configuración de parámetros del sistema, la gestión avanzada de usuarios y el control absoluto de los módulos de Ventas, Inventario y Facturación.