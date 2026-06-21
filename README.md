# Sistema de Automatización de Conciliación Bancaria — COOPRUDEA
Flujo automatizado desarrollado en n8n que realiza el proceso completo de conciliación bancaria: cruza los movimientos del banco con los registros contables, actualiza el papel de trabajo y envía los resultados al correo registrado.

# Requisitos
- Credencial de Google Cloud para el formulario
- Los archivos de entrada en formato .xlsx con la estructura definida en el manual de usuario

# Estructura del repositorio
├── flujo_conciliacion.json   # Flujo exportado, listo para importar en n8n
├── manual_usuario.pdf        # Manual de uso para el área contable
└── README.md

# Instalación en Cloud
1. Ingresar a n8n Cloud.
2. Crear un nuevo flujo.
3. Ir a ··· (menú) → Import from file y seleccionar My workflow(13).json.
4. Configurar la credencial de Gmail en el nodo correspondiente.
5. Activar el flujo.

# Instalación en local
1. Ejecutar en consola 'n8n start'
2. Ingresar a 'localhost:5678'
3. Crear un nuevo flujo.
4. Ir a ··· (menú) → Import from file y seleccionar My workflow(13).json.
5. Configurar la credencial de Gmail en el nodo correspondiente.
6. Activar el flujo.

# Uso
1. Abrir la URL del formulario.
2. Cargar los 4 archivos requeridos (.xlsx).
3. Ingresar las 2 fechas de conciliación.
4. Presionar Submit y esperar entre 1 y 3 minutos.
5. El resultado llega al correo registrado.

# Estructura de archivos de entrada

| Archivo | Cabeceras / Hojas requeridas |
|---|---|
| Movimientos bancarios | Formato descarga Bancolombia (separado por comas) |
| Libro mayor | Formato descarga sistema contable interno |
| Conciliación DIA | Concepto, Referencia, Referencia, Doc, Valor, Nota |
| Papel de trabajo | ConsigNoContPendiente, RetirosNoContPendiente, RetContNoBancoPendiente, ConsigContNoBancoPendiente, Balances  |

Importante: los nombres de las columnas y hojas deben respetarse exactamente. Cualquier cambio puede impedir que el flujo funcione correctamente.

# Autores
Desarrollado por Karen Jimenez, Mily Sierra y Luisa Sotoo para COOPRUDEA — 2026.
