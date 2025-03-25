# Análisis Forense de Memoria con Volatility

🕵️ **Investigación forense sobre memoria RAM utilizando Volatility para la detección de actividad maliciosa**  

Este repositorio contiene el informe del **Laboratorio de Fundamentos de la Seguridad en el Software y los Componentes (FSSC)**, donde se ha llevado a cabo un análisis de memoria RAM utilizando **Volatility** para detectar procesos sospechosos, conexiones activas y código malicioso inyectado en el sistema.

## 🔍 Descripción

El objetivo de este laboratorio es aplicar técnicas de **análisis forense de memoria**, identificando artefactos digitales en una imagen de memoria obtenida de un sistema Windows XP y una imagen de memoria infectada con malware (**Cridex**).  
El análisis incluye:
- **Extracción de información clave de la memoria RAM**: Procesos activos, archivos abiertos, conexiones de red, DLLs cargadas y servicios del sistema.
- **Detección de actividad sospechosa**: Uso de `malfind` para localizar inyección de código en procesos críticos.
- **Identificación de malware en memoria**: Exploración de patrones y artefactos en procesos de Windows (`explorer.exe`, `svchost.exe`, `winlogon.exe`).
- **Generación y análisis de imágenes de memoria propias**: Uso de herramientas como **WinPMem** y **LiME** para extraer memoria en entornos Windows y Linux.

## 📁 Contenido del Repositorio

- `Practica 2 Laboratorio FSSC.pdf` → Informe detallado con los resultados del análisis.
- **Comandos y scripts utilizados en Volatility** (próximamente).

## 🛠 Herramientas Utilizadas

### 🔹 **Análisis Forense con Volatility**
- **`imageinfo`** → Identificación del perfil del sistema y metadatos de la imagen de memoria.
- **`pslist` / `pstree`** → Listado de procesos en ejecución y su jerarquía.
- **`netscan`** → Análisis de conexiones de red activas y procesos asociados.
- **`dlllist`** → Extracción de DLLs cargadas en la memoria.
- **`filescan`** → Identificación de archivos abiertos en el sistema.
- **`svcscan`** → Análisis de servicios en ejecución.
- **`envars`** → Recuperación de variables de entorno.
- **`malfind`** → Detección de inyección de código en procesos del sistema.

### 🔹 **Generación de Imágenes de Memoria**
- **WinPMem** → Creación de volcados de memoria en Windows para análisis en Volatility.
- **LiME (Linux Memory Extractor)** → Obtención de imágenes de memoria en sistemas Linux.

## 🚀 Resultados y Hallazgos

- **Detección de procesos sospechosos** (`svchost.exe`, `cmd.exe`, `explorer.exe`) con comportamientos anómalos.
- **Identificación de conexiones sospechosas** a direcciones IP externas en el puerto 443.
- **Presencia de malware inyectado en memoria** (`Cridex`), con ejecutables detectados en procesos como `winlogon.exe` y `reader_sl.exe`.
- **Problemas en la generación de imágenes propias** debido a errores en la resolución de símbolos en Volatility 2 y 3.

## 📌 Posibles Mejoras

- **Automatización del análisis** con scripts en Python para ejecución de múltiples comandos en Volatility.
- **Detección avanzada de rootkits** mediante módulos específicos de Volatility.
- **Uso de técnicas de análisis de memoria en entornos modernos** (Windows 10, Linux actual).

## 🤝 Contribuciones

Si deseas mejorar este análisis, agregar nuevos métodos o expandir la detección de amenazas, haz un **fork**, añade tus cambios y envía un **Pull Request**.

## 📜 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
