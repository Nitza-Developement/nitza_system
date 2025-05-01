# 🔐 Tutorial: Configurar SSH

Este tutorial te guía paso a paso para que puedas conectarte a tus servidores por SSH **sin tener que escribir la contraseña cada vez**. (`autenticación con llave`)

---

## 🧾 Requisitos previos

- Tener acceso a los servidores vía SSH con usuario y contraseña.
- Tener configurado el archivo `~/.ssh/config` con tus hosts.
- (opcional) Tener instalado [Visual Studio Code](https://code.visualstudio.com/) y la extensión **Remote - SSH**.
- (opcional) Tener instalado [Termius](https://termius.com/) u otro gestor de acceso SSH.

## 🧩 Ejemplo de archivo `~/.ssh/config`:
```ssh
Host servidor_1            # Alias que usaremos para conectarnos
  HostName 192.168.1.10    # Dirección IP o nombre del servidor
  User admin               # Usuario con el que nos autenticamos

Host servidor_2            # Alias de otra conexión
  HostName 203.0.113.25  
  User devuser
```

## 1. Verificar si ya tienes una llave SSH
En la terminal (puedes usar la terminal integrada de VSCode o Termius), ejecuta:
```bash
ls ~/.ssh/id_rsa.pub
```
- Si el archivo existe, pasa al paso 3.
- Si no existe, ve al paso 2.

## 2. Generar una nueva clave SSH
Ejecuta en la terminal:
```bash
ssh-keygen -t rsa -b 4096 -C "tu_correo_personal@ejemplo.com"
```
Presiona `Enter` en cada paso para aceptar los valores por defecto.
Esto creará dos archivos:

- `~/.ssh/id_rsa` (clave privada)
- `~/.ssh/id_rsa.pub` (clave pública)

## 3. Copiar tu clave pública al servidor
Ejecuta este comando para cada servidor:
```bash
ssh-copy-id ALIAS_DEL_HOST
```
Ejemplo:
```bash
ssh-copy-id servidor_1
ssh-copy-id servidor_2
```

## 4. Verificar conexión sin contraseña
Intenta conectarte:
```bash
ssh servidor_1
# o
ssh 192.168.1.10
```

### 📝 NOTA sobre IdentityFile (llaves .pem)
Si tu servidor requiere una llave privada específica (por ejemplo, `.pem` para AWS), agrégala al `~/.ssh/config`:
- Lugo de recibir el fichero `.pem` Asegúrate de colocarlo en una ubicación segura, como `~/.ssh/.`
```ssh
Host mi_servidor_produccion
  HostName ec2-11-22-33-44.compute-1.amazonaws.com
  User ec2-user
  IdentityFile ~/.ssh/mi_llave.pem   # ubicacion del fichero .pem
```
Asegúrate de que el archivo .pem tenga permisos adecuados:
```bash
# (Linux/MacOs)
chmod 400 ~/.ssh/mi_llave.pem
```
```bash
# Windows PowerShell
IdentityFile /c/Users/TU_USUARIO/.ssh/mi_llave.pem
```

## (Opcional) [Conectar desde VSCode](https://code.visualstudio.com/docs/remote/ssh)
1. Abre VSCode.
2. Instala la extensión Remote - SSH.
3. Presiona F1 o Ctrl+Shift+P y busca: Remote-SSH: Connect to Host....
4. Selecciona el host (servidor_1, etc.) de la lista.
5. VSCode se conectará al servidor y abrirá una ventana remota.

## (Opcional) Conectar desde Termius
2. Abre Termius y haz clic en "Hosts" (barra lateral izquierda).
3. Presiona "New Host" o el símbolo +.
4. Rellena los campos:
  - Label: Un nombre identificativo (ej. Servidor Producción)
  - Address: La IP o dominio del servidor (ej. 192.168.1.10)
  - Username: El usuario (ej. bob o admin)
  - Password: Solo si no usas llave SSH, pero recomendado usar clave privada
  - [SSH Key](https://termius.com/documentation/import-ssh-keys): Selecciona el archivo `.pem` o `id_rsa` desde tu sistema de archivos
6. Guarda los cambios y haz doble clic en el host para conectarte.

NOTA : Tambien puede [importar la configuración de los shh_hosts](https://termius.com/documentation/import-from-ssh-config)
