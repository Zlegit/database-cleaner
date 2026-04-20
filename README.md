# 🔥 Database Cleaner / Data Parser Pro Max

Herramienta avanzada en Python para **limpiar, normalizar y convertir bases de datos** en múltiples formatos a un JSON estructurado y optimizado.

Diseñada para trabajar con archivos desorganizados y extraer información útil como usuarios, contraseñas, IPs, emails y hashes de forma automática.

---

## 🚀 Características

* 🧼 Limpieza automática de datos
* 📂 Soporte para múltiples formatos:

  * `.txt`
  * `.log`
  * `.csv`
  * `.json`
  * `.sql`
* 🧠 Detección inteligente de:

  * IPs
  * Emails
  * Dominios
  * Hashes
* 🔄 Normalización de datos en formato estándar
* 🧹 Eliminación de duplicados
* 🌐 Renombrado automático de archivos basado en dominio detectado
* ⚠️ Sistema de logs para errores (`errors.txt`)
* ⚡ Procesamiento masivo de archivos

---

## 📁 Estructura del Proyecto

```
project/
│
├── databases/        # Archivos de entrada
├── output/           # Resultados procesados
├── errors.txt        # Registro de errores
└── main.py           # Script principal
```

---

## ⚙️ Instalación

1. Clona el repositorio:

```bash
git clone https://github.com/tuusuario/database-cleaner.git
cd database-cleaner
```

2. Ejecuta el script:

```bash
python main.py
```

---

## 🧪 Uso

Al ejecutar el programa verás un menú interactivo:

```
🔥 DATA PARSER PRO MAX 🔥

LIST | ALL | EXIT
```

### Comandos:

* `LIST` → Lista los archivos disponibles en `/databases`
* `ALL` → Procesa todos los archivos automáticamente
* `EXIT` → Salir del programa

---

## 🧠 Cómo funciona

### 🔍 Extracción de datos

El script analiza cada línea buscando patrones como:

* `user:password`
* `user,password`
* `user|password`
* etc.

Además detecta automáticamente:

* IPs mediante regex
* Emails
* Hashes (MD5, SHA1, SHA256, etc.)

---

### 🧾 Normalización

Todos los datos se convierten a este formato estándar:

```json
{
  "user": "",
  "password": "",
  "ip": "",
  "email": "",
  "hash": ""
}
```

---

### 🌐 Detección de dominio

El sistema intenta detectar el dominio más frecuente en los usuarios:

Ejemplo:

```
user@netflix.com
```

➡️ El archivo final se guardará como:

```
netflix.com.json
```

Si no se detecta un dominio válido:
➡️ Se mantiene el nombre original del archivo

---

### 🧹 Eliminación de duplicados

Los registros repetidos se eliminan automáticamente antes de guardar el resultado final.

---

## 📊 Output

Los archivos procesados se guardan en:

```
/output/
```

Formato:

```
[dominio].json
```

---

## ⚠️ Manejo de errores

Todos los errores se registran en:

```
errors.txt
```

Incluye:

* Archivos vacíos
* Fallos de parsing
* Errores de JSON

---

## 💡 Ejemplo

### Input:

```
john:123456
mike,password123
admin@site.com:admin
```

### Output:

```json
[
  {
    "user": "john",
    "password": "123456",
    "ip": "",
    "email": "",
    "hash": ""
  }
]
```

---

## 🔒 Disclaimer

Este proyecto está destinado únicamente a fines educativos y de procesamiento de datos propios.
No se debe utilizar con información sin autorización.

---

## 🧠 Futuras mejoras

* Interfaz gráfica (GUI)
* Exportación a CSV / SQL
* Filtros avanzados
* Multithreading para mayor velocidad
* API REST

---

## ⭐ Contribuir

Pull requests y mejoras son bienvenidas.

---

## 📜 Licencia

MIT License

---

🔥 Hecho para procesar datasets como un verdadero pro.
