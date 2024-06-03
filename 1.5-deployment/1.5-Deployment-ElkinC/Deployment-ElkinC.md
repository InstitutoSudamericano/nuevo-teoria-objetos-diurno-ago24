DEPLOYMENT


El deployment, o despliegue en español, es el proceso de lanzar una aplicación o software en un entorno de producción después de pasar por pruebas y desarrollos en entornos de preproducción o pruebas.
1. **Deployment continuo**: Esta teoría defiende la idea de automatizar el proceso de despliegue para que cada cambio de código que pase las pruebas automáticamente se implemente en producción. Esto reduce el tiempo entre el desarrollo y la entrega al usuario final.
    
2. **Entornos de despliegue**: Se recomienda tener múltiples entornos de despliegue, como desarrollo, pruebas, control de calidad y producción. Cada uno sirve para propósitos específicos y permite probar el software en diferentes etapas antes de llegar al entorno de producción.
    
3. **Blue-Green Deployment**: Esta teoría propone tener dos entornos de producción idénticos (blue y green). Mientras uno está activo y sirve a los usuarios, el otro se actualiza con la nueva versión del software. Una vez que la actualización está completa y probada, el tráfico se redirige al nuevo entorno (green), y el antiguo (blue) se convierte en el nuevo entorno para futuras actualizaciones.
    
4. **Rolling Deployment**: En este enfoque, las actualizaciones se implementan en una serie de etapas, con una pequeña porción del tráfico redirigido a la nueva versión en cada etapa. Esto permite detectar problemas gradualmente y revertir la actualización si es necesario.
    
5. **Canary Deployment**: Similar al despliegue azul-verde, en este enfoque se implementa una nueva versión del software solo a un pequeño subconjunto de usuarios antes de una implementación completa. Esto permite detectar problemas con una pequeña audiencia antes de lanzar la actualización a todos los usuarios.
    
6. **Monitoreo y Rollback**: Es crucial monitorear el despliegue en tiempo real para detectar problemas de rendimiento o errores. Si se detecta un problema grave, es importante tener un proceso automatizado para revertir rápidamente a la versión anterior del software.

~~~
Resumen 

Deployment Continuo: Automatización del despliegue para cambios de código probados.
Entornos de Despliegue: Múltiples entornos para probar el software en distintas etapas.
Blue-Green Deployment: Dos entornos idénticos alternados para actualizaciones sin interrupciones.
Rolling Deployment: Implementación gradual para detectar y corregir problemas progresivamente.
Canary Deployment: Prueba de nueva versión con un grupo reducido de usuarios antes de lanzarla completamente.

Monitoreo y Rollback: Vigilancia continua y capacidad de revertir rápidamente en caso de problemas.
 ~~~

 link del video:
 https://youtu.be/UK0qrrSwrW4