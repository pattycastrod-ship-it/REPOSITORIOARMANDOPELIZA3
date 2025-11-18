Propuesta de mantenimiento para el mecanismo de contraseñas en el registro de usuarios

1\. objetivo

Garantizar que las contraseñas almacenadas en el sistema sean resistentes a ataques y que el proceso de registro mantenga una buena experiencia de usuario.

2\. alcance

\- Políticas de creación de contraseñas

\- Hashing y almacenamiento seguro

\- Renovación y caducidad

\- Gestión de recuperación y MFA (autenticación multifactor)

\- Monitoreo y auditoría

3\. acciones clave

Área	Acción	Responsable	Periodicidad

Política de contraseñas	Definir longitud mínima (≥12), complejidad (mayúsculas, minúsculas, números, símbolos) y prohibir patrones comunes.	Equipo de seguridad	Cada 6 meses o cuando haya cambios regulatorios

Hashing	Usar argon2id (o bcrypt con coste adecuado) y almacenar solo el hash, nunca la contraseña en texto plano.	DevOps / Backend	Al desplegar cambios de dependencia

Rotación	Obligar a cambiar la contraseña cada 90 días y después de cualquier incidente.	Administrador de cuentas	Cada 90 días (recordatorio automático)

MFA	Habilitar OTP o clave de seguridad como segundo factor opcional, con incentivo para activarlo.	UX / Seguridad	Durante onboarding y después de cada cambio de contraseña

Validación de correo	Enviar enlace de verificación y requerir confirmación antes de activar la cuenta.	Backend	Cada registro

Bloqueo de cuentas	Bloquear tras 5 intentos fallidos y requerir desbloqueo vía email o soporte.	Operaciones	En tiempo real

Auditoría	Registrar intentos de login, cambios de contraseña y uso de MFA.	SIEM / Logs	Diario, con retención de 12 meses

Pruebas de penetración	Simular ataques de fuerza bruta y de diccionario.	Equipo de pentesting	Anual o tras cambios mayores

Actualizaciones	Mantener dependencias (libs de hashing, frameworks) al día.	DevOps	Mensual

4\. cronograma sugerido

\- Mes 1: Revisar y actualizar la política de contraseñas; implementar argon2id.

\- Mes 2: Configurar MFA opcional y flujos de recuperación.

\- Mes 3: Ajustar mecanismos de bloqueo y registro de auditoría.

\- Mes 4: Realizar primera prueba de penetración y ajustar parámetros.

\- Meses 5‑12: Ciclo de revisión mensual de logs y actualizaciones de dependencias; rotación automática de contraseñas.

5\. recursos necesarios

\- Herramientas de hashing (argon2, bcrypt).

\- Servicio de envío de emails (para verificación y recuperación).

\- Plataforma de MFA (Google Authenticator, Authy, o hardware key).

\- Sistema de logs centralizado (ELK, Splunk).

\- Presupuesto para pruebas de penetración externas (aprox. USD 2 000‑3 000 al año).

6\. métricas de éxito

\- % de usuarios con MFA activado (> 70 % en 6 meses).

\- Tasa de contraseñas comprometidas (objetivo 0).

\- Tiempo medio de detección de intentos de fuerza bruta (< 5 min).

\- Cumplimiento de política de rotación (≥ 95 % de usuarios renovados a tiempo).


