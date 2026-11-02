# 📦 Gestor de Catálogo TUU v2.0

Aplicación de escritorio para Windows, desarrollada en Python y Streamlit, que permite crear, organizar, editar y validar catálogos de productos compatibles con el formato Excel de **TUU Desk**.

Está orientada especialmente a minimarkets, almacenes y pequeños comercios que necesitan administrar grandes cantidades de productos sin registrarlos individualmente en su plataforma de ventas.

## 🎯 Objetivo

Facilitar la administración de productos mediante una interfaz sencilla, con herramientas para mantener un catálogo ordenado, generar identificadores, detectar errores y preparar los datos para su posterior importación a TUU Desk.

**Importante:** esta aplicación no se conecta directamente a TUU Desk. La transferencia del catálogo se realiza mediante archivos Excel.

## ✨ Funcionalidades principales

### 📋 Gestión del catálogo
- Importar catálogos Excel compatibles con TUU.
- Crear catálogos nuevos.
- Agregar, editar y eliminar productos.
- Buscar y filtrar por nombre, marca, categoría y códigos.
- Editar directamente desde una planilla.
- Guardar automáticamente los cambios.
- Deshacer y rehacer modificaciones.
- Detectar posibles productos duplicados.

### 🔢 Generación de SKU
- Generar SKU individuales o masivos.
- Identificar productos sin SKU.
- Validar la información necesaria antes de generar.
- Corregir campos desde la tabla de generación.
- Conservar los SKU existentes.

### 🏷️ Códigos de barras
- Registrar códigos comerciales mediante teclado o lector.
- Generar códigos internos EAN-13.
- Generar códigos internos de forma masiva.
- Identificar códigos comerciales e internos mediante el registro de la aplicación.
- Evitar sobrescribir códigos existentes.

### 🛒 Simulador de caja
- Buscar productos mediante código de barras.
- Probar lecturas con una pistola lectora.
- Simular un carrito de compras.
- Calcular cantidades y totales.
- Detectar códigos inexistentes.
- Registrar productos encontrados con problemas.
- Reiniciar la prueba y limpiar los historiales.

El simulador es una herramienta de validación. No registra ventas reales ni modifica el inventario.

### 🖨️ Etiquetas y cartillas
- Generar etiquetas de productos en PDF.
- Seleccionar varios productos y definir cantidades de impresión.
- Generar cartillas de códigos de barras.
- Filtrar por marca, categoría y origen del código.
- Buscar productos específicos.
- Imprimir documentos en tamaño carta con tres columnas.

Las etiquetas incluyen categoría, nombre, SKU, código de barras, número del código y precio.

## 💻 Requisitos

### Para utilizar la versión instalable

- Windows 10 u 11.
- Espacio disponible para instalar y ejecutar la aplicación.
- Navegador web compatible para visualizar la interfaz local.
- Lector de códigos de barras USB opcional.

No es necesario instalar Python ni Visual Studio Code cuando se utiliza el instalador completo.

### Para ejecutar desde el código fuente

- Python compatible con las dependencias del proyecto.
- Streamlit.
- pandas.
- openpyxl.
- rapidfuzz.
- ReportLab.
- Las demás dependencias declaradas por el proyecto.

## 🚀 Uso básico

1. Iniciar Gestor de Catálogo TUU.
2. Importar un Excel existente o crear un catálogo nuevo.
3. Completar los datos de los productos.
4. Revisar los productos incompletos o duplicados.
5. Generar SKU y códigos internos cuando corresponda.
6. Probar los códigos mediante el simulador de caja.
7. Generar etiquetas o cartillas si se necesitan.
8. Exportar el catálogo para importarlo manualmente a TUU Desk.

## 📊 Formato Excel compatible

El catálogo utiliza las 11 columnas oficiales de la plantilla TUU:

| Columna | Descripción |
|---|---|
| NOMBRE* | Nombre del producto |
| Descripción | Descripción del producto |
| PESO | Peso o contenido |
| PRECIO* | Precio de venta |
| PRECIO COSTO | Costo del producto |
| ¿EXENTO?* | Indicador de exención |
| CÓDIGO SKU | Identificador interno |
| CÓDIGO DE BARRAS | Código comercial o interno |
| MARCAS | Marca |
| CATEGORIAS | Categoría |
| ¿HABILITADO?* | Estado del producto |

Los campos marcados con asterisco son obligatorios según la plantilla utilizada.

La generación de SKU y códigos internos puede exigir información adicional para mantener la calidad del catálogo.

## 🔒 Protección de datos

La aplicación trabaja con una copia del catálogo importado para evitar modificar directamente el archivo original.

Incluye mecanismos de guardado, historial de cambios y validación. Se recomienda mantener respaldos periódicos de los archivos Excel.

## 🛠️ Tecnologías

- Python
- Streamlit
- pandas
- openpyxl
- rapidfuzz
- ReportLab
- PyInstaller, para empaquetar la aplicación
- Inno Setup, para crear el instalador de Windows

## 📁 Estructura del proyecto

```text
Programa Catalogo/
├── app.py
├── launcher.py
├── modules/
│   ├── excel_manager.py
│   ├── duplicate_detector.py
│   ├── product_form.py
│   ├── sku_generator.py
│   ├── sku_registry.py
│   ├── barcode_generator.py
│   ├── barcode_registry.py
│   └── etiquetas_pdf.py
├── data/
├── instaladores/
└── README.md
```

## ⚠️ Consideraciones

- Los códigos internos deben probarse con el lector antes de su uso operativo.
- El simulador valida el catálogo local, pero no garantiza la aceptación de códigos por TUU Desk.
- Los códigos comerciales existentes no deben reemplazarse innecesariamente.
- La importación final a TUU Desk es responsabilidad del usuario.
- La aplicación no constituye un sistema de ventas ni un inventario conectado en tiempo real a TUU.

## 📌 Estado del proyecto

**Versión:** 2.0

**Estado:** funcionalidades principales implementadas; preparación del instalador y distribución.

## 👨‍💻 Desarrollo

Proyecto desarrollado como solución de gestión de catálogos para pequeños comercios y como parte de un proceso de aprendizaje y desarrollo de software con Python.

---

**Gestor de Catálogo TUU v2.0** — Una herramienta sencilla para organizar, validar y preparar catálogos de productos.
