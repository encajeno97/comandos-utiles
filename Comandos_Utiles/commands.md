### Comandos utiles

**Crear directorios**
```bash
mkdir nombre_directorio (nombre que quieras poner a la carpeta)
```

## 🧾 Significado de `777` en permisos de archivos (Linux/Unix)

### 📘 Estructura de permisos
Los permisos se dividen en tres grupos:

| Grupo | Significado |
|--------|--------------|
| **User (u)** | Propietario del archivo |
| **Group (g)** | Usuarios del mismo grupo |
| **Others (o)** | Todos los demás usuarios |

Cada grupo puede tener estos permisos:

| Permiso | Letra | Valor | Descripción |
|----------|--------|--------|--------------|
| **Read** | r | 4 | Leer el archivo o listar un directorio |
| **Write** | w | 2 | Modificar el archivo o escribir en un directorio |
| **Execute** | x | 1 | Ejecutar el archivo o acceder al contenido del directorio |

---

### ⚙️ Cálculo de permisos
Cada dígito es la suma de los valores:

| Permisos | Valor | Significado |
|-----------|--------|-------------|
| rwx | 7 | lectura, escritura y ejecución |
| rw- | 6 | lectura y escritura |
| r-x | 5 | lectura y ejecución |
| r-- | 4 | solo lectura |

---

### 🔢 Significado de `777`


