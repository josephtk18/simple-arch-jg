# Sistema de Banca por Internet BP

## Descripción del Proyecto

El **Sistema de Banca por Internet BP** es una solución moderna y escalable diseñada para ofrecer a los clientes acceso seguro y eficiente a servicios bancarios desde aplicaciones web y móviles. Este proyecto implementa funcionalidades clave como consultas de movimientos, transferencias, notificaciones personalizadas y pagos, garantizando alta disponibilidad, seguridad, y cumplimiento con normativas de la industria como **ISO 22301**.

---

## Características Principales

- **Consulta de Datos Básicos y Movimientos**:
  Permite a los usuarios revisar su información bancaria y el historial de transacciones en tiempo real.

- **Transferencias y Pagos**:
  Soporta transferencias internas e interbancarias con confirmaciones en tiempo real y opciones de personalización.

- **Reconocimiento Facial para Onboarding**:
  Integración con **AWS Rekognition** para verificación de identidad y detección de vida como parte del registro.

- **Notificaciones Personalizadas**:
  Uso de **Amazon SNS** para notificaciones push, SMS y email sobre actividades relevantes.

- **Reportes Financieros**:
  Generación de reportes personalizados con análisis visual interactivo.

---

## Arquitectura del Sistema

### **Capa de Integración**
El sistema utiliza un **API Gateway** para enrutar solicitudes a microservicios alojados en un clúster de **AWS EKS**. Las interacciones externas incluyen:
- **Sistema Core Bancario**: Procesamiento de transacciones y consultas de cuenta.
- **AWS Rekognition**: Validación facial en el flujo de onboarding.
- **AWS Cognito**: Gestión de autenticación y autorización.
- **Amazon SNS**: Envío de notificaciones multicanal.

### **Base de Datos**
Se utiliza **Amazon RDS (Multi-AZ)** como base de datos principal para garantizar alta disponibilidad. Los datos críticos se respaldan mediante:
- Réplicas en múltiples zonas de disponibilidad.
- Snapshots periódicos con **AWS Backup**.

### **Infraestructura**
El sistema aprovecha **AWS CloudFront** para entregar contenido estático y minimizar la latencia. La infraestructura está diseñada para tolerancia a fallos y recuperación ante desastres.

---

## Requisitos Técnicos

- **Lenguajes y Frameworks**:
  - Front-End: React para SPA, Flutter/React Native para móvil.
  - Back-End: Node.js/Java Spring en microservicios.

- **Herramientas de Infraestructura**:
  - Contenedores: Kubernetes en AWS EKS.
  - Monitoreo: AWS CloudWatch y AWS X-Ray.

---

## Prácticas de Continuidad y Seguridad

Este proyecto integra las prácticas de **ISO 22301** para la continuidad del negocio:
1. **Alta Disponibilidad (HA)**: Configuración Multi-AZ para servicios críticos.
2. **Tolerancia a Fallos (FT)**: Failover automático en bases de datos y Redis Cache.
3. **Recuperación ante Desastres (DR)**: Backups automáticos con AWS Backup.
4. **Seguridad**: Uso de AWS Cognito y AWS WAF para proteger el acceso.
