# Requerimientos funcionales

## Creación de cuenta
- El sistema debe permitir a los usuarios registrarse proporcionando información básica (nombre, correo electrónico, contraseña, etc.).
- El sistema debe asignar un identificador único a cada nuevo usuario.

## Validación de datos
- El sistema debe validar que todos los campos requeridos estén completos.
- El sistema debe validar que los datos ingresados cumplan con los formatos esperados (ej. formato de correo electrónico, fuerza de la contraseña).
- El sistema debe manejar y mostrar mensajes de error claros si la validación falla.

## Inicio de sesión
- El sistema debe permitir a los usuarios autenticarse usando sus credenciales (nombre de usuario/correo y contraseña).
- El sistema debe restringir el acceso a información o funcionalidades si las credenciales son incorrectas.
- # Requerimientos no funcionales

## Autenticación
- Implementar mecanismos seguros de autenticación:
  - Complejidad de contraseñas (mínimo de caracteres, combinación de tipos).
  - Opción de recuperación de contraseña por correo electrónico.

## Tiempo de respuesta
- El sistema debe procesar la solicitud de registro en un tiempo aceptable, por ejemplo, en menos de *2 segundos*, incluso con alta carga de usuarios.

## Crecimiento de usuarios
- El sistema debe poder soportar un aumento futuro en el número de usuarios sin requerir una re‑arquitectura completa.
- TABLA DE PRUEBAS
ID	Requerimiento
asociado	Datos de entrada	Resultado
esperado	Resultado
obtenido
CP- 001	El sistema debe registrar a un nuevo usuario con datos válidos.	Nombre de usuario: usuario_nuevo Contraseña: Contraseña123 Confirmar contraseña: Contraseña123	El registro se completa con éxito. Se muestra un mensaje de
confirmación.	Se muestra el mensaje: "Usuario registrado correctamente"
CP- 002	El sistema debe evitar el registro si el nombre de usuario ya existe.	Nombre de usuario: usuario_existente Contraseña: Contraseña123 Confirmar contraseña: Contraseña123	El sistema rechaza el registro. Se muestra un mensaje de error indicando
que el usuario ya existe.	Se muestra el mensaje: "El nombre de usuario ya está en uso"
CP- 003	El sistema debe solicitar una contraseña que cumpla con los requisitos de seguridad.	Nombre de usuario: usuario_debil Contraseña: debil Confirmar contraseña: debil	El sistema rechaza el registro. Se muestra un mensaje de error indicando que la contraseña no cumple con los
requisitos.	Se muestra el mensaje: "La contraseña debe tener al menos 8 caracteres, una mayúscula y un número"

TABLA DE VALIDACIÓN
ID	Requerimiento
asociado	Datos de entrada	Resultado
esperado	Resultado
obtenido
CV- 001	El sistema debe validar que la dirección de correo electrónico tenga un formato válido.	Nombre de usuario: usuario_correo Correo electrónico: correo-invalido Contraseña: Contraseña123	El sistema rechaza el registro. Se muestra un mensaje de error indicando que el formato del correo
electrónico es inválido.	“Formato de correo electrónico inválido.”
CV- 002	El sistema debe validar que las contraseñas coincidan.	Nombre de usuario: usuario_nomatch Contraseña: Contraseña123 Confirmar contraseña: Contraseña456	El sistema rechaza el registro. Se muestra un mensaje de error indicando que las contraseñas no
coinciden.	“Las contraseñas no
coinciden.”
## Tipo de mantenimientos propuestos
- *Validación de datos*
  - Verificar que los campos cumplan los formatos requeridos (correo electrónico, password, etc.).
  - Detectar campos vacíos o inconsistentes y mostrar mensajes claros.

- *Corrección de errores*
  - Revisar y solucionar fallos detectados en pruebas (por ejemplo, mensajes de error incorrectos).
  - Aplicar parches de seguridad cuando sea necesario.

## Reflexión sobre el control de versiones en un software de registro de usuarios
1. Seguridad: permite revertir cambios no autorizados o maliciosos.  
2. Integridad de los datos: mantiene un historial que protege la información de los usuarios.  
3. Colaboración: facilita que varios desarrolladores trabajen simultáneamente sin interferir.  
4. Reversibilidad: posibilita volver a una versión estable ante un error.  
5. Auditoría: ofrece un registro completo de todos los cambios para cumplir normativas.  
6. Mejora continua: analiza versiones anteriores para optimizar la experiencia del usuario.  
7. Gestión de errores: ayuda a localizar rápidamente la causa de un problema.
8. "añadir archivo readme.md"
