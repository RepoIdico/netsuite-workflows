### README del Workflow: **IDICO WF Freight Control**

#### **Descripción**
Este workflow implementa la lógica para deshabilitar ciertos campos en función del valor seleccionado en el campo personalizado **"Freight As"**. Su objetivo principal es garantizar que solo los campos relevantes sean editables según las reglas de negocio definidas.

#### **Tecnologías y Herramientas**
- **NetSuite**: ERP utilizado para gestionar registros y flujos de trabajo.
- **SuiteFlow**: Utilizado para la creación del workflow visual.
- **Campos personalizados**: Se manejan campos específicos relacionados con la gestión de costos de transporte (e.g., `custbody_inbound_freight_price`, `custcol_outbound_freight_cost`).
- **Condiciones de Visual Builder**: Reglas personalizadas definidas mediante fórmulas y listas personalizadas.

#### **Arquitectura**
- **Registro asociado**: El workflow aplica a los registros de tipo:
  - **Estimate**
  - **Sales Order**
- **Estados y Acciones**:
  - **Estado inicial**: "State 1".
  - **Acciones principales**:
    - Se ejecutan **antes de la carga** (`BEFORELOAD`) para deshabilitar campos según el valor del campo "Freight As".
    - Se activan también **después de la edición de campo** (`AFTERFIELDEDIT`) cuando el campo "Freight As" es modificado.

**Diagrama de Arquitectura**:
(Se puede incluir un diagrama representando los estados, transiciones y acciones en el flujo).

#### **Detalles del Código XML**
- **Script ID**: `customworkflow_idico_wf_freight_control`
- **Estado**: `TESTING`
- **Campos clave controlados**:
  - `custbody_inbound_freight_price` (Precio de flete de entrada).
  - `custcol_outbound_freight_cost` (Costo de flete de salida).
  - `custbody_evol_freight_as` (Freight As).
- **Reglas y Condiciones**:
  - Cuando el valor de "Freight As" está en la lista definida (e.g., `"IDICO Freight As1"`), deshabilita o habilita dinámicamente campos específicos.
  - Se utilizan parámetros personalizados vinculados a listas personalizadas (`customlist_idico_freight_as`).

#### **Resultados de la Implementación**
- **Entregables**:
  - Campos irrelevantes deshabilitados en registros de órdenes de venta y estimaciones.
  - Validaciones dinámicas de acuerdo con reglas personalizadas.
- **Impacto**:
  - Mejora en la precisión de los datos ingresados.
  - Reducción de errores humanos en la configuración de costos de transporte.
- **Pruebas y Validación**:
  - Verificado en entorno de pruebas (`TESTING`) con datos simulados de órdenes de venta.

#### **Especificaciones Técnicas**
- **Estados y Acciones**:
  - `BEFORELOAD`: Control inicial de los campos antes de la carga del registro.
  - `AFTERFIELDEDIT`: Ajustes dinámicos al modificar "Freight As".
- **Condiciones personalizadas**:
  - Fórmulas empleadas para evaluar los valores seleccionados en "Freight As".
- **Historial**: Activado solo durante la etapa de pruebas.

#### **Mantenimiento y Actualización**
- Asegurarse de mantener actualizada la lista personalizada `customlist_idico_freight_as`.
- Probar el flujo después de cualquier cambio en campos relacionados o estructura de registros.

#### **Licencia y Créditos**
- **Licencia**: Propiedad interna de la organización.
- **Créditos**: Creado por el equipo de desarrollo interno para la gestión avanzada de costos de transporte en NetSuite.

¿Hay algún detalle adicional que te gustaría incluir o ajustar?