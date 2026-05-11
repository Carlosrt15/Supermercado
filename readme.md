# 🚀 Git Cheat Sheet - Preparación de Examen

Este documento resume los comandos y flujos de trabajo esenciales de Git utilizados durante la práctica del proyecto **Supermercado**.

---

## 🛠️ 1. Configuración de Usuario
Para establecer la identidad que firmará los commits.

* **Configurar nombre global:**
  ```bash
  git config --global user.name "Sonia201120"
  ```
* **Verificar configuración activa:**
  ```bash
  git config user.name
  git config --list --global
  ```

---

## 📂 2. Gestión de Repositorios y Remotos
Creación de la estructura local y conexión con servidores externos (GitHub).

* **Crear e inicializar repo local:**
  ```bash
  git init Supermercado
  ```
* **Vincular el primer remoto (origin):**
  ```bash
  git remote add origin https://github.com
  ```
* **Añadir un segundo remoto con alias:**
  ```bash
  git remote add repo2 https://github.com
  ```
* **Listar todos los remotos configurados:**
  ```bash
  git remote -v
  ```

---

## 🔄 3. Inspección y Sincronización
Comandos para comparar y traer cambios sin romper el flujo de trabajo.

* **Consultar cambios remotos (sin descargar archivos):**
  ```bash
  git fetch origin
  ```
* **Ver diferencias entre local y remoto (Rama master):**
  ```bash
  git diff master origin/master
  ```
* **Descargar e integrar cambios directamente:**
  ```bash
  git pull origin master
  ```
* **Enviar cambios locales al servidor:**
  ```bash
  git push origin master
  ```

---

## ⚠️ 4. Resolución de Conflictos
Procedimiento cuando la misma línea ha sido modificada en local y remoto.

1. **Identificar el conflicto:** Aparece al hacer `pull` y la terminal muestra `(master|MERGING)`.
2. **Localizar marcas en el archivo:** 
   - `<<<<<<< HEAD`: Tu cambio local.
   - `=======`: Divisor.
   - `>>>>>>> [ID-Commit]`: Cambio del remoto.
3. **Limpiar el archivo:** Borrar las marcas y dejar solo el texto final deseado.
4. **Finalizar la fusión:**
   ```bash
   git add inventario.txt
   git commit -m "Resolución de conflicto"
   git push origin master
   ```

---

## 🔍 5. Comandos de Diagnóstico
* **Estado actual de los archivos:** `git status`
* **Historial de commits simplificado:** `git log --oneline`
* **Historial gráfico de ramas:** `git log --graph --oneline --all`
