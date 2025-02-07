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
3. Verifica que los cambios se descargaron:
![2](https://github.com/user-attachments/assets/399b8613-70e0-4632-8c73-9ed82bb0f697)


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
     ![3](https://github.com/user-attachments/assets/71236c89-293e-4771-9004-60f6f322d7e6)


## 4. Revisión de código
1. En la vista "Changes":
   - Revisa la calidad del código
   - Verifica convenciones del proyecto
   - Busca problemas de seguridad
     
2. Agrega comentarios:
   - Hover sobre la línea > ícono `+`
   - Para múltiples líneas: selecciona > clic derecho > "Add Comment"
![Captura de pantalla (311)](https://github.com/user-attachments/assets/df415d27-eb27-4d2f-b67f-9cfbfd169c21)

## 5. Acciones finales
1. Aprobar:
   - "Add Review" > "Approve"
   - Confirma que probaste los cambios localmente
![5](https://github.com/user-attachments/assets/a99c15bb-aa97-4a0c-b8df-f5db49f0d472)

2. Solicitar cambios:
   - "Add Review" > "Request Changes"
   - Detalla qué necesita modificación
   - Incluye evidencia de problemas encontrados

## 6. Limpieza
1. Al aprpobar cambios elimina la rama del "Pull Request"
   ![8](https://github.com/user-attachments/assets/de1f014a-51da-4f0a-991b-4ad7ce14bd0d)

2. Asegúrate de volver a tener la rama **dev** actualizada
![9](https://github.com/user-attachments/assets/0b0773dd-5188-4d0b-b270-e79eb777a8c4)

## Mejores prácticas
- No apruebes sin probar localmente
- Documenta todos los problemas encontrados
- Verifica que los cambios coincidan con la documentación
- Prueba en un entorno limpio
