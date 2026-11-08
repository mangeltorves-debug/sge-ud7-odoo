Paso 1: Creación del Presupuesto (Rol: Comercial - Estela)

    Usuario responsable: Estela (Comercial Junior).

    Acción: Estela inicia sesión en el sistema con su cuenta de comercial y accede al módulo de Ventas. Crea un nuevo presupuesto dirigido al cliente empresa Colchones Paco S.A.

    Detalle de líneas del presupuesto:

        Línea 1: Tabla de madera mesa (Cantidad: 2 u., Precio unitario: 120.00 €, Impuesto: IVA 21%).

        Línea 2: Pata mesa de hierro (Cantidad: 8 u., Precio unitario: 25.00 €, Impuesto: IVA 21%).

        Línea 3 (Con descuento): Lampara de mesa negra (Cantidad: 3 u., Precio unitario: 45.00 €, Descuento aplicado: 10%, Impuesto: IVA 21%).

    Condiciones comerciales:

        Plazo de pago: 30 días fecha factura.

        Fecha de validez: Válido por 15 días naturales desde su emisión.

    Referencia del documento generado: Presupuesto S00012 (o referencia equivalente generada por el sistema).

    Estado inicial: Presupuesto (Borrador enviado). Estela imprime el documento en formato PDF desde Odoo para su archivo o envío comercial.

Paso 2: Confirmación del Pedido (Rol: Responsable de Ventas - Gervasio)

    Usuario responsable: Gervasio (Responsable de Ventas).

    Acción: Gervasio accede al sistema con su rol de administración de ventas para revisar el documento comercial creado por su equipo. Tras validar la viabilidad económica y los márgenes aplicados, accede al presupuesto S00012.

    Referencia del documento: Pedido de Venta S00012 (transicionado desde el presupuesto).

    Estado: Se pulsa el botón Confirmar pedido (Confirm), pasando el documento de estado Presupuesto a Pedido de Venta (Sales Order). Esto genera automáticamente la orden de salida de almacén correspondiente.

Paso 3: Validación de la Orden de Entrega y Stock (Inventario)

    Usuario responsable: Miguel Ángel (Administrador Técnico / Supervisor de Logística) o automatizado por el flujo de almacén.

    Acción: Se comprueba el módulo de Inventario (Inventory). Al confirmar el pedido de venta, se genera de manera automática la operación de salida de mercancías.

    Referencia del documento: Albarán de salida WH/OUT/00015.

    Verificación de stock: Se valida la transferencia de salida donde la cantidad hecha coincide exactamente con la cantidad pedida (2 Tablas de madera, 8 Patas de hierro y 3 Lámparas negras). Al validar el albarán (Validate), el sistema descuenta de forma automática las unidades del stock físico del almacén de Torves.

    Estado final del albarán: Hecho (Done).

Paso 4: Facturación y Registro del Pago (Rol: Administración / Facturación)

    Usuario responsable: Perfil de Administración / Facturación (o supervisión administrativa).

    Acción: Una vez entregado el material, se accede al pedido de venta S00012 y se hace clic en Crear factura (Create Invoice), seleccionando una factura regular.

    Referencia del documento: Factura de cliente INV/2026/00008.

    Revisión y Publicación: El contable revisa las líneas fiscales, comprueba que el NIF de Colchones Paco S.A. y los datos de la empresa Torves (ESA12345674) son correctos, y pulsa Confirmar (Post). El estado pasa de Borrador a Publicado.

    Registro del Pago: Se pulsa el botón Registrar pago (Register Payment), introduciendo el importe total, el diario de banco y la fecha de cobro.

    Estado final de la factura: El documento queda automáticamente marcado con la etiqueta verde de Pagado (Paid).

Paso 5: Estado Final y Análisis Comercial

    Estado del Pedido: Si se regresa al módulo de Ventas, el pedido S00012 muestra el indicador de facturación completo en estado Facturado (Fully Invoiced).

    Análisis de Ventas: En el informe gráfico de Ventas (Reporting > Sales), se visualiza el volumen de negocio generado por Estela con el cliente Colchones Paco S.A., reflejando el impacto de los artículos vendidos (tablas, patas y lámparas) en la cuenta de resultados de Torves.