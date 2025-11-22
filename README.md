# 📋 DOCUMENTACIÓN COMPLETA - SISTEMA DE ANÁLISIS DE COMBUSTIBLE

## SISTEMA INTEGRAL DE ANÁLISIS DE COMBUSTIBLE PARA LAS MUNICIPALIDADES


### DOCENTE
**MARIBEL MOLINA BARRIGA**

### CURSO
**FUNDAMENTOS DE SISTEMAS DE INFORMACIÓN**

### CARRERA
**ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS**

### INTEGRANTES
- MALDONADO VILCA VICTOR GONZALO
- MAMANI ANAHUA VICTOR NARCISO
- QUISPE MARCA EDYSSON DARWIN
- SUAREZ HUAMANI MARCO ANTONIO
- VELASQUE ARCOS MIKHAIL GABINO

### FECHA
- Noviembre 2025  

## 📖 DESCRIPCIÓN GENERAL

Sistema web integral para el análisis inteligente del consumo de combustible de la flota vehicular municipal, que combina análisis tradicional con tecnologías de inteligencia artificial para optimizar el control y gestión del combustible.

### 🏗️ ARQUITECTURA

- **Backend:** Flask + Python 3.9+
- **Base de Datos:** SQLite con SQLAlchemy ORM
- **IA/ML:** Scikit-learn (RandomForest)
- **Análisis:** Pandas, NumPy, Matplotlib
- **Frontend:** HTML5, Bootstrap 5, JavaScript
- **Autenticación:** Flask-Login
- **Reportes:** FPDF

---

## ✨ FUNCIONALIDADES PRINCIPALES

### 🔐 1. AUTENTICACIÓN Y SEGURIDAD

- Sistema de login obligatorio
- Gestión de usuarios y roles
- Sesiones seguras
- Control de acceso por funcionalidad

### 📊 2. ANÁLISIS TRADICIONAL

- **Carga de datos:** Archivos Excel con validación automática
- **Procesamiento:** Limpieza y transformación de datos
- **Análisis:** Consumo por mes, dependencia y vehículo
- **Detección de anomalías:** Algoritmos ML + reglas de negocio
- **Reportes PDF:** Gráficos, estadísticas y recomendaciones

### 🤖 3. PREDICCIÓN CON IA

- **Modelo:** RandomForest entrenado dinámicamente
- **Predicciones:** Consumo futuro por vehículo
- **Tendencias:** Análisis de patrones temporales
- **Métricas:** Precisión y confiabilidad del modelo

### 🚨 4. SISTEMA DE ALERTAS

- **Exceso de Consumo:** Umbrales configurables (20% por defecto)
- **Mantenimiento Preventivo:** Por kilometraje (5,000 km) y eficiencia
- **Anomalías Frecuentes:** Patrones anómalos recurrentes
- **Consumo Fin de Semana:** Uso no autorizado

### 📋 5. HISTORIAL Y NOTIFICACIONES

- **Búsqueda avanzada:** Por fecha, usuario, tipo de análisis
- **Notificaciones:** Cambios automáticos en el sistema
- **Registro completo:** Todas las actividades y análisis
- **Exportación:** Historial en múltiples formatos

### 🔍 6. FILTROS AVANZADOS

- **Criterios múltiples:** Fecha, dependencia, consumo, anomalías
- **Tiempo real:** Estadísticas actualizadas automáticamente
- **Exportación:** Datos filtrados en Excel/CSV
- **Persistencia:** Configuraciones guardadas por usuario

### 🌱 7. ANÁLISIS DE EMISIONES

- **Cálculo CO2:** Por vehículo y flota completa
- **Factores de emisión:** Configurables por tipo de combustible
- **Reportes ambientales:** Impacto y recomendaciones
- **Visualizaciones:** Gráficos de emisiones y tendencias

---

## 🛠️ INSTALACIÓN Y CONFIGURACIÓN

### REQUISITOS

- Python 3.9+
- pip
- Navegador web moderno

### INSTALACIÓN

```bash
# 1. Ir al directorio del proyecto
cd "ruta/del/proyecto/FSI"

# 2. Crear entorno virtual
python -m venv venv

# 3. Activar entorno virtual
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# 4. Instalar dependencias
pip install -r requirements.txt

# 5. Ejecutar aplicación
python -m backend.app

# 6. Acceder en navegador
# http://127.0.0.1:5000
```

### CONFIGURACIÓN AVANZADA

```env
# Archivo .env (opcional)
SECRET_KEY=clave_secreta_segura
DATABASE_URL=sqlite:///instance/app.db
FLASK_ENV=development
```

---

## 📁 ESTRUCTURA DEL PROYECTO

```
FSI/
├── backend/
│   ├── app.py                          # Aplicación Flask principal
│   ├── analisis_combustible.py         # Análisis tradicional
│   ├── prediccion_ia.py                # Módulo de IA
│   ├── sistema_alertas.py              # Sistema de alertas
│   ├── historial_notificaciones.py     # Historial y notificaciones
│   ├── filtros_avanzados.py            # Filtros avanzados
│   ├── modulo_emisiones.py             # Análisis de emisiones
│   └── templates/
│       ├── index.html                  # Interfaz principal
│       └── login.html                  # Página de login
├── frontend/static/
│   ├── css/style.css                   # Estilos
│   └── js/script.js                    # JavaScript
├── uploads/                            # Archivos cargados
├── reports/                            # Reportes generados
├── instance/                           # Base de datos SQLite
└── requirements.txt                    # Dependencias Python
```

---

## 🚀 GUÍA DE USO

### 1. ACCESO AL SISTEMA

1. Abrir navegador: `http://127.0.0.1:5000`
2. Ingresar credenciales de usuario
3. Hacer clic en "Iniciar Sesión"

### 2. ANÁLISIS BÁSICO

1. **Cargar datos:** Seleccionar archivo Excel y subir
2. **Configurar análisis:** Elegir mes y dependencia
3. **Ejecutar:** Hacer clic en "Analizar Datos"
4. **Revisar resultados:** Ver estadísticas y anomalías
5. **Descargar reporte:** PDF con análisis completo

### 3. FUNCIONALIDADES AVANZADAS

#### PREDICCIÓN IA

```
1. Entrenar Modelo → Preparar IA con datos históricos
2. Predecir Consumo → Obtener predicciones específicas
3. Analizar Tendencias → Ver patrones temporales
```

#### ALERTAS

```
1. Configurar Alerta → Definir tipo y parámetros
2. Verificar Alertas → Ver alertas activas
3. Gestionar → Activar/desactivar alertas
```

#### FILTROS

```
1. Aplicar Filtros → Configurar criterios
2. Ver Estadísticas → Datos en tiempo real
3. Exportar → Descargar datos filtrados
```

---

## 📊 FORMATO DE DATOS

### ESTRUCTURA DEL EXCEL

**Columnas requeridas:**

| Columna            | Descripción        | Tipo   | Ejemplo        |
| ------------------ | ------------------ | ------ | -------------- |
| FECHA_INGRESO_VALE | Fecha del vale     | Date   | 2025-01-15     |
| PLACA              | Placa del vehículo | Text   | ABC-123        |
| UNIDAD_ORGANICA    | Dependencia        | Text   | GERENCIA_ADMIN |
| CANTIDAD_GALONES   | Galones consumidos | Number | 25.50          |
| KM_RECORRIDO       | Kilómetros         | Number | 150            |
| TIPO_COMBUSTIBLE   | Tipo combustible   | Text   | GASOLINA       |
| PRECIO             | Precio unitario    | Number | 12.50          |
| MES                | Mes del consumo    | Number | 1              |

---

## 🔧 APIs Y ENDPOINTS

### ANÁLISIS

- `POST /upload` - Cargar archivo Excel
- `POST /analyze` - Ejecutar análisis tradicional
- `GET /download-report` - Descargar reporte PDF

### PREDICCIÓN IA

- `POST /prediccion/entrenar` - Entrenar modelo
- `POST /prediccion/predecir` - Realizar predicción
- `POST /prediccion/analizar-tendencias` - Analizar tendencias

### ALERTAS

- `POST /alertas/configurar` - Configurar alerta
- `POST /alertas/verificar` - Verificar alertas
- `GET /alertas/listar` - Listar alertas
- `GET /alertas/resumen` - Resumen de alertas

### HISTORIAL

- `GET /historial/buscar` - Búsqueda avanzada
- `POST /historial/registrar` - Registrar evento
- `GET /historial/exportar` - Exportar historial

### FILTROS

- `POST /filtros/aplicar` - Aplicar filtros
- `GET /filtros/estadisticas` - Estadísticas filtradas
- `GET /filtros/exportar` - Exportar datos

### EMISIONES

- `POST /emisiones/calcular` - Calcular emisiones
- `GET /emisiones/reporte` - Reporte ambiental

---

## 🎯 FLUJO DE TRABAJO

### FLUJO BÁSICO

```
1. Login → 2. Cargar Excel → 3. Análisis → 4. Ver Resultados → 5. Descargar PDF
```

### FLUJO AVANZADO

```
1. Login → 2. Cargar Excel → 3. Entrenar IA → 4. Configurar Alertas →
5. Aplicar Filtros → 6. Análisis Completo → 7. Gestionar Historial
```

### CONTROL DE ACCESO

- **Funcionalidades básicas:** Disponibles siempre
- **Funcionalidades avanzadas:** Solo después del análisis tradicional
- **Decorator `@require_analysis`:** Controla acceso a rutas avanzadas

---

## 🛡️ SISTEMA DE ALERTAS (DETALLE)

### CONFIGURACIONES

| Tipo           | Parámetro         | Valor Por Defecto | Descripción            |
| -------------- | ----------------- | ----------------- | ---------------------- |
| Exceso Consumo | umbral_porcentaje | 20%               | % sobre promedio       |
|                | periodo_analisis  | 30 días           | Período de comparación |
| Mantenimiento  | umbral_km         | 5,000 km          | KM para mantenimiento  |
|                | umbral_eficiencia | 8 km/gal          | Eficiencia mínima      |
| Anomalías      | max_anomalias_mes | 5                 | Máximo anomalías/mes   |
| Fin Semana     | umbral_porcentaje | 30%               | % consumo total        |

### NIVELES DE ALERTA

- **Crítico:** Requiere atención inmediata
- **Alto:** Atención en 24-48 horas
- **Medio:** Revisión en una semana
- **Bajo:** Monitoreo continuo

---

## 🔍 SOLUCIÓN DE PROBLEMAS

### ERRORES COMUNES

#### Error de Importación

```bash
# Verificar directorio y ejecutar correctamente
cd "ruta/al/proyecto/FSI"
python -m backend.app
```

#### Error de Dependencias

```bash
# Reinstalar dependencias
pip install --upgrade pip
pip install -r requirements.txt --force-reinstall
```

#### Error de Base de Datos

```bash
# Recrear base de datos
rm instance/app.db
python -m backend.app
```

#### Error de Archivo Excel

- Verificar formato de columnas
- Comprobar tipos de datos
- Revisar nombres exactos de columnas

### LOGS Y DEBUGGING

- **Logs del sistema:** `app.log`
- **Errores Python:** Consola del servidor
- **Errores JavaScript:** Consola del navegador
- **Base de datos:** `instance/app.db`

---

## 📈 CARACTERÍSTICAS TÉCNICAS

### RENDIMIENTO

- **Carga de archivos:** Hasta 100MB Excel
- **Procesamiento:** ~1000 registros/segundo
- **Respuesta web:** < 2 segundos promedio
- **Base de datos:** SQLite optimizada con índices

### SEGURIDAD

- **Autenticación:** Obligatoria para acceso
- **Sesiones:** Timeout automático
- **Archivos:** Validación de tipo y tamaño
- **SQL:** Protección contra inyección

### ESCALABILIDAD

- **Usuarios concurrentes:** 10-20 (SQLite)
- **Datos:** Millones de registros
- **Reportes:** Generación asíncrona
- **Upgrade:** Migración a PostgreSQL disponible

---

## 🔮 MEJORAS FUTURAS

### FUNCIONALIDADES PLANIFICADAS

- [ ] Dashboard interactivo en tiempo real
- [ ] API REST completa para integración
- [ ] Notificaciones por email/SMS
- [ ] Análisis predictivo avanzado
- [ ] Integración con sistemas GPS
- [ ] App móvil para consultas

### MEJORAS TÉCNICAS

- [ ] Migración a PostgreSQL
- [ ] Implementación de Redis para cache
- [ ] Contenedorización con Docker
- [ ] CI/CD automatizado
- [ ] Monitoreo y métricas
- [ ] Backup automático

---

## 📞 SOPORTE Y MANTENIMIENTO

### CONTACTO TÉCNICO

- **Logs del sistema:** Revisar `app.log`
- **Documentación:** Este archivo
- **Historial:** `RESUMEN_IMPLEMENTACION.md`

### MANTENIMIENTO RUTINARIO

1. **Semanal:** Verificar logs de errores
2. **Mensual:** Backup de base de datos
3. **Trimestral:** Actualización de dependencias
4. **Anual:** Revisión de seguridad

### BACKUP Y RECUPERACIÓN

```bash
# Backup base de datos
cp instance/app.db backups/app_$(date +%Y%m%d).db

# Backup archivos subidos
tar -czf backups/uploads_$(date +%Y%m%d).tar.gz uploads/

# Restaurar
cp backups/app_YYYYMMDD.db instance/app.db
```

---

## 📄 LICENCIA Y CRÉDITOS

**Soporte:** Sistema FSI  
**Última actualización:** Noviembre 2025

---
