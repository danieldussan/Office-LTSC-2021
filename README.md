# Activación de Office LTSC 2021

Este repositorio proporciona una guía para instalar y corregir el error de licencia no activada en Microsoft Office LTSC 2021, incluyendo **Access**, **Word**, **Excel** y **PowerPoint**.

## Instalación de Office LTSC 2021

1. **Clonar el repositorio**:
   Abre una terminal y ejecuta el siguiente comando para clonar el repositorio:
   ```bash
   git clone https://github.com/danieldussan/Office-LTSC-2021.git
   ```
   También puedes descargar el repositorio de forma manual y seguir con los demás pasos.

2. **Abrir CMD como administrador**:
   Haz clic derecho en el ícono de "Símbolo del sistema" y selecciona **"Ejecutar como administrador"**.

3. **Dirigirse a la carpeta del repositorio**:
   Navega a la carpeta donde clonaste el repositorio:
   ```bash
   cd /d <ruta_del_repositorio>
   ```

4. **Ejecutar el comando de configuración**:
   Ejecuta el siguiente comando para iniciar la instalación de Office:
   ```bash
   setup /configure Configuration.xml
   ```

## Si no tienes activo el producto, haz los siguientes pasos

### Paso 1: Navegar a la Carpeta de Office

Dependiendo de si tienes una versión de **32 bits** o **64 bits** de Office, abre una terminal y ejecuta uno de los siguientes comandos:

#### Para 32 bits
```bash
cd /d %ProgramFiles(x86)%\Microsoft Office\Office16
```

#### Para 64 bits
```bash
cd /d %ProgramFiles%\Microsoft Office\Office16
```

### Paso 2: Instalar la Licencia

Ejecuta el siguiente comando para instalar la licencia. Este comando buscará el archivo de licencia correspondiente:
```bash
for /f %x in ('dir /b ..\root\Licenses16\ProPlus2021VL_KMS*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%x"
```

### Paso 3: Activar Office

Ejecuta los siguientes comandos uno por uno para activar Office:
```bash
cscript ospp.vbs /setprt:1688
cscript ospp.vbs /unpkey:6F7TH >nul
cscript ospp.vbs /inpkey:FXYTK-NJJ8C-GB6DW-3DYQT-6F7TH
cscript ospp.vbs /sethst:e8.us.to
cscript ospp.vbs /act
```

## Notas

- Asegúrate de tener **permisos de administrador** al ejecutar estos comandos.
- Asegúrate de tener **instalado Git** en tu dispositivo.
- Si experimentas problemas, verifica que todos los archivos necesarios están en las ubicaciones correctas.

## Licencia

Este proyecto está bajo la [Licencia MIT](LICENSE).
