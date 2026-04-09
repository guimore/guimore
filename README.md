# 🚀 Infrastructure, Automation & Security Lab - Guido Mora

Este repositorio es mi centro de operaciones. Aquí documento mi evolución como **SRE / DevOps**, integrando automatización de infraestructura, desarrollo en Python y seguridad perimetral.

## 🛠️ Tecnologías y Herramientas
* **Cloud:** AWS (EC2, S3, IAM, Cloud Practitioner level)
* **IaC:** Ansible (Automatización de configuraciones e idempotencia)
* **Programación:** Python (Automatización de procesos y lógica de backend)
* **Seguridad:** IBM Cybersecurity Framework (SIEM, Vulnerability Management, Incident Response)
* **OS:** Linux (Ubuntu Server, Kali, RHEL)

---

## 📂 Proyectos y Automatización

### 🤖 Infraestructura como Código (Ansible)
* **[apacheinstalacion.yml](./automation/apacheinstalacion.yml):** Playbook avanzado con lógica condicional que detecta la familia del Sistema Operativo (`ansible_os_family`). Instala y configura Apache tanto en entornos **Debian/Ubuntu** (apt) como **RHEL/CentOS** (dnf).
* **[info.yml](./automation/info.yml):** Herramienta de auditoría automatizada. Utiliza `gather_facts` para extraer en tiempo real el Hostname, IP principal, interfaces de red y puntos de montaje de todos los servidores del inventario.

### 🐍 Desarrollo Python (Talento Tech - 80hs)
* **TP Final Python:** Proyecto enfocado en la resolución de problemas mediante lógica de programación, manejo de estructuras de datos y automatización. 
* *Certificación:* Ministerio de Educación (CABA) - 80 horas reloj.

### 🛡️ Seguridad e Infraestructura Crítica
* Configuración de balanceadores de carga **HAProxy** para alta disponibilidad.
* Gestión de seguridad perimetral y reglas de firewall en **pfSense**.
* Monitoreo y endurecimiento de sistemas (**Hardening**) basado en los módulos de IBM SkillsBuild.

---

## 📜 Certificaciones y Badges Digitales

### ☁️ Amazon Web Services (AWS)
* **AWS Educate:** [Getting Started with Storage](https://www.credly.com/badges/e2af2623-96f6-4e8d-94fb-09bdf530a829/public_url) - Gestión de S3 y persistencia de datos.
* **AWS Educate:** [Getting Started with Compute](https://www.credly.com/badges/3006a88e-499c-4860-9189-873961168128/public_url) - Implementación de instancias EC2.

### 🔐 Cybersecurity (IBM)
* **IBM SkillsBuild:** [Cybersecurity Certificate](https://www.credly.com/badges/a34271a1-9884-45bc-9820-390d12494c74) - Especialización en gestión de amenazas, respuesta a incidentes y seguridad en la nube.

### 🎓 Educación IT
* **Analista de Sistemas:** Estudiante de 2do año (IFTS).
* **Especialista Python:** Talento Tech (Gobierno de la Ciudad de Buenos Aires).

---
📫 **¿Hablamos de infraestructura?** [LinkedIn](TU_LINK_DE_LINKEDIN_ACA)
