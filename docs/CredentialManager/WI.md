# Guía de Instalación de Git Credential Manager
**Plataforma**: Ubuntu
**Método de Almacenamiento**: Texto Plano
**Última Actualización**: 10 de febrero de 2025

## Requisitos Previos
- Ubuntu 20.04 o posterior
- Git instalado
- Privilegios de administrador

## Pasos de Instalación

### 1. Instalar Dependencias Requeridas
Primero, asegúrese de que todas las dependencias requeridas estén instaladas:
```bash
sudo apt-get update
sudo apt-get install -y curl libsecret-1-0 dotnet-runtime-6.0
```

### 2. Descargar Git Credential Manager
Descargue la última versión de Git Credential Manager:
```bash
curl -LO "https://github.com/git-ecosystem/git-credential-manager/releases/{LATEST_VERSION}"
```
> ⚠️NOTA : es necesario entrar a la sección releases del repositorio previamente señalado para obtención de la URL actual.

### 3. Instalar el Paquete
Instale el paquete descargado:
```bash
sudo dpkg -i {FILE_NAME}.deb
```
> ⚠️NOTA : FILE_NAME será sustituido por el nombre del fichero .deb descargado.

### 4. Configurar Git para Usar Almacenamiento en Texto Plano
Configure Git para usar almacenamiento en texto plano para las credenciales:
```bash
git config --global credential.credentialStore plaintext
```

### 5. Configurar Git Credential Manager
Inicialice Git Credential Manager:
```bash
git-credential-manager configure
```

### 6. Verificar la Instalación
Verifique que Git Credential Manager esté instalado correctamente:
```bash
git-credential-manager --version
```

## Pruebas de Configuración

1. Intente clonar un repositorio que requiera autenticación:
```bash
git clone https://github.com/username/repository.git
```

2. Ingrese sus credenciales cuando se le solicite
3. Verifique que las credenciales estén almacenadas revisando:
```bash
cat ~/.git-credentials
```

## Solución de Problemas

### Problemas Comunes y Soluciones

1. **Falla en la Instalación**
   - Asegúrese de que todas las dependencias estén instaladas
   - Verifique la compatibilidad de la arquitectura del sistema
   - Verifique los privilegios de administrador

2. **Las Credenciales No Se Guardan**
   - Confirme que el almacenamiento en texto plano esté configurado
   - Verifique los permisos del archivo ~/.git-credentials
   - Asegúrese de que los archivos de configuración tengan el propietario correcto

3. **Errores de Autenticación**
   - Verifique que las credenciales sean correctas
   - Compruebe la conectividad de red
   - Asegúrese de que la URL del repositorio sea correcta

## Desinstalación

Si es necesario, elimine Git Credential Manager:
```bash
sudo dpkg -r gcm
git config --global --unset credential.helper
git config --global --unset credential.credentialStore
rm ~/.git-credentials
```

## Soporte

Para soporte adicional:
- Visite el [repositorio de GitHub de Git Credential Manager](https://github.com/GitCredentialManager/git-credential-manager)
- Consulte la documentación de Ubuntu
- Consulte con su administrador de sistemas

## Aviso de Seguridad

Tenga en cuenta que almacenar credenciales en texto plano es menos seguro que el almacenamiento cifrado. Considere usar esta configuración solo en entornos controlados y nunca almacene credenciales sensibles de esta manera en sistemas compartidos o públicos.
