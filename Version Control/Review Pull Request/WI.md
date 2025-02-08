# Guía de revisión de Pull Requests usando VSCode

## Requisitos previos
- VSCode instalado
- Extensión [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) instalada
- Cuenta de GitHub configurada en VSCode
- Git instalado y configurado localmente

## 1. Revisión inicial de documentación
1. Verifica que el PR incluya:
   - Descripción detallada de cambios
   - Capturas de pantalla/grabaciones para cambios visuales
   - Pasos para probar los cambios
   - Enlaces a tareas en [odoo](odoo.ladetec.com) relacionadas

## 2. Checkout y prueba local
1. En VSCode, ve a la sección GitHub Pull Requests
2. Haz clic derecho en el PR > "Checkout Pull Request"


   ![1](https://github.com/user-attachments/assets/2428a9ea-7895-4597-85a5-22cce89b12f3)



3. Verifica que los cambios se descargaron:

   
![2](https://github.com/user-attachments/assets/eb00a8ce-e378-4066-8cd4-b0154a67d92b)



## 3. Verificación independiente
1. Sigue los pasos de prueba documentados
2. Para cambios visuales:
   - Compara con las capturas proporcionadas
   - Prueba en diferentes resoluciones
   - Verifica estados de hover/focus
3. Para cambios funcionales:
   - Ejecuta pruebas unitarias
   - Prueba casos límite
   - Verifica integración con otros componentes

## 4. Revisión de código
1. En la vista "Changes":
   - Revisa la calidad del código
   - Verifica convenciones del proyecto
   - Busca problemas de seguridad
  
     
     ![3](https://github.com/user-attachments/assets/b1da2f27-b7e1-4643-a8df-350bcb6090f7)

     

2. Agrega comentarios:
   - Hover sobre la línea > ícono `+`
  
     
     ![Captura de pantalla (311)](https://github.com/user-attachments/assets/877f6224-21b3-4380-b321-48bffcdf00d4)

   - Para múltiples líneas: selecciona > clic derecho > "Add Comment"

## 5. Acciones finales
1. Aprobar:
   - "Add Review" > "Approve"
   - Confirma que probaste los cambios localmente


2. Solicitar cambios:
   - "Add Review" > "Request Changes"
   - Detalla qué necesita modificación
   - Incluye evidencia de problemas encontrados

## 6. Limpieza
1. Al aprpobar cambios elimina la rama del "Pull Request"

   ![7](https://github.com/user-attachments/assets/3aa53358-d3d3-4b4f-a77d-e52f40d91b68)

2. Asegúrate de volver a tener la rama **dev** actualizada

![8](https://github.com/user-attachments/assets/d58ba054-6acc-4adb-882d-1724150741b7)


## Mejores prácticas
- No apruebes sin probar localmente
- Documenta todos los problemas encontrados
- Verifica que los cambios coincidan con la documentación
- Prueba en un entorno limpio
