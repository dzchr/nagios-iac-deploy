## 🚀 Automatización Infraestructura Nagios - Terraform + GitHub Actions

Este repositorio contiene la automatización de infraestructura en AWS para desplegar Nagios Core usando **Terraform**. Permitiendo mayor control, versionamiento y automatización futura mediante GitHub Actions.

## 📦 Componentes desplegados

- **Amazon ECS (Fargate):** Servicio para ejecutar contenedores Docker sin administrar servidores.
- **Amazon ECR:** Imagen personalizada de Nagios Core 4.4.14 basada en Debian.
- **Application Load Balancer (ALB):** Exposición pública del servicio web por HTTP.
- **Amazon EFS:** Almacenamiento persistente montado en los contenedores.
- **Security Groups:** Controlan acceso entre ALB, ECS y desde el exterior.
- **Subnets, VPC, IAM roles:** Reutilizables o configurables según tu entorno.

## ⚙️ Requisitos

- ✅ Cuenta en AWS
- ✅ Terraform v1.5+ instalado
- ✅ Imagen Docker de Nagios
- ✅ Variables de entorno exportadas manualmente:

## 🧪 Estructura del repositorio

terraform-nagios/
├── main.tf              # Recursos principales (ECS, ALB, EFS, roles)
├── variables.tf         # Variables de entorno y configuración
├── outputs.tf           # Valores exportables (DNS ALB, ID cluster, etc.)
├── provider.tf          # Configuración del proveedor AWS
├── README.md            # Este documento

### 🚀 Cómo desplegar

Clona el repositorio y entra al directorio

git clone https://github.com/tuusuario/terraform-nagios.git
cd nagios-iac-deploy

Exporta tus credenciales temporales:

export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
export AWS_SESSION_TOKEN=...
export AWS_REGION=us-east-1

Inicializa Terraform:
terraform init

Previsualiza los recursos:
terraform plan

Aplica la infraestructura:
terraform apply

📍 Futuro: GitHub Actions
Este repositorio está preparado para incluir un workflow de GitHub Actions que automatice el despliegue al hacer cambios en los archivos .tf.

🎓 Autor
Christopher Cabrera González
📧 chr.cabrera@duocuc.cl
📘 Duoc UC – Ingeniería en Infraestructura y Plataformas Tecnológicas
🧪 Proyecto académico – Automatización

