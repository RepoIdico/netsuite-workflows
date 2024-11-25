# NetSuite Workflows Migration: Legacy to Success Tax

## 📄 **Descripción**
Este repositorio contiene todos los **Workflows** de NetSuite que se migrarán del entorno **Legacy Tax** al entorno **Success Tax**. La migración forma parte de la transición hacia el nuevo modelo de impuestos habilitado por NetSuite para mejorar la gestión fiscal y cumplir con las nuevas regulaciones.

---

## 📂 **Estructura del Repositorio**
- `Objects/Workflows/`: Carpeta que contiene los archivos de los workflows exportados en formato XML o JSON, organizados por módulo o funcionalidad.
  - `Fletes/`: Workflows relacionados con el proceso de Costos de Feltes.

---

## 🔧 **Requisitos**
1. **NetSuite Tools**:
   - SuiteCloud Development Framework (SDF).
   - SuiteScript habilitado en la cuenta.
2. **Permisos**:
   - Acceso a la cuenta de producción y sandbox.
   - Permisos para importar/exportar workflows.
3. **Configuraciones**:
   - La funcionalidad de **Success Tax** debe estar habilitada en el entorno destino.

---

## 🚀 **Guía de Uso**
### **Exportar Workflows desde NetSuite**
1. Utiliza el siguiente comando de SDF para exportar un Workflow desde NetSuite:
   ```bash
   suitecloud object:import --scriptid <script_id> --type WORKFLOW --destinationfolder workflows/<category>

## ✅ Plan de migración
- 1. Identificación de Workflows: Se listan y clasifican los workflows relevantes para la transición.
- 2. Validación Previa: Se prueban los workflows existentes en un entorno sandbox.
- 3. Exportación y Modificación: Los workflows se exportan y ajustan según los requisitos de Success Tax.
- 4. Importación a Sandbox: Se prueban los workflows en el entorno Success Tax sandbox.
- 5. Pruebas Finales: Validación funcional con datos reales en sandbox.
- 6. Migración a Producción: Implementación en el entorno de producción Success Tax.

## 📊 Workflows incluidos

| **Script ID**       | **Nombre del Workflow**          | **Módulo**        |
|----------------------|----------------------------------|-------------------|
| `customworkflow_idico_wf_freight_control` | IDICO WF Freight Control      | Sales             | 
