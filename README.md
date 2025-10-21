# Playground para aprender a usar python notebooks con Jupyter en entornos de Conda

## 📦 Instalar Conda en Windows

Instalar **[Miniconda](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe)** (Selecciona "Just Me" y deja la ruta por defecto).

Una vez instalado MiniConda por primera vez abrir AnacondaPrompt y escribir "conda init bash" (De esta forma se podrá usar conda desde Git Bash)

```bash
conda init bash
```

---

## 🛠️ Entornos (Conda)

**Windows (Git Bash):**
```bash
cd DIRECTORIO/DONDE/TENGAIS/EL/PROYECTO
conda env create -f envs/myenvironment.yml
conda activate myenv
```

---

## 📓 Ejecutar notebooks con Jupyter (opcional de momento pero necesario si acabamos usando un repo de linux)

Activa primero tu entorno `myenv` y ejecuta:

```bash
python -m ipykernel install --user --name myenv --display-name "my first python environment"
```

Una vez instalado el entorno, ejecuta:
```bash
jupyter lab --no-browser --ip=0.0.0.0
```

> Abre la URL con token que imprime Jupyter en tu navegador de Windows (ultimo link de todos). Dentro de JupyterLab, selecciona el kernel **my first python environment** para ejecutar los notebooks con ese entorno.

---

### 🐱 Haz tu primer git add -> git commit -> git push

Dentro del proyecto, solo una vez:
```bash
git config user.name "Usuario_Github"
git config user.email "correo_usuario_github@empresa.com"
```

Create una rama nueva desde Github y usando los comandos del documento de drive colocate en la rama y haz el add, el commit y el push

---

## 🔄 Actualizar entornos

- Actualizar el entorno
  ```bash
  conda env update -f envs/tools/myenvironment.yml --prune
  ```

- Borrar el entorno:
  ```bash
  conda deactivate
  conda env remove -n myenv
  ```

---

### 🚨 Limpieza si eliminas entornos
Quitar kernel “zombi” antes de borrar un entorno:
```bash
jupyter kernelspec list
jupyter kernelspec uninstall myenv -y
```
