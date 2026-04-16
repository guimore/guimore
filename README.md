# Guido J. Mora Medina
## DevOps Engineer | SysAdmin | DevSecOps — Buenos Aires, Argentina
📧 mora.guido@gmail.com | 💼 [LinkedIn](https://linkedin.com/in/guido-mora-42170a1a9/) | 🐙 [GitHub](https://github.com/guimore)

---

## 🚀 Sobre mí
Especialista en Infraestructura IT con más de 15 años de trayectoria en entornos críticos de Banca y Telecomunicaciones. Experto en administración híbrida Linux/Unix, automatización CI/CD y arquitecturas cloud AWS. Perfil orientado a DevSecOps, integrando seguridad en cada etapa del pipeline. Experiencia en empresas líderes como Banco Macro, Claro, Ericsson y HP.

---

## 🛠️ Stack Tecnológico

**DevOps, Cloud & IaC**

Jenkins, Docker, Kubernetes, AWS, Ansible, GitHub Actions, Python

**Sistemas Operativos**

Red Hat, Ubuntu, Kali Linux

**Seguridad & Networking**

IBM Security, pfSense, HAProxy, Nessus, Ethical Hacking, Suricata, Wazuh

---

## 📂 Proyectos Destacados

### K8s Security Lab - Kubernetes + pfSense
Laboratorio virtualizado de Kubernetes con firewall pfSense para práctica de seguridad ofensiva/defensiva y orquestación resiliente.
- Arquitectura: NAT (WAN) + Host-Only (LAN) con segmentación por zonas.
- Seguridad: RBAC, TLS habilitados y endurecimiento (Hardening) basado en normas de IBM Cybersecurity.
- Orquestación: Master en Kali, Workers en Ubuntu Server gestionados vía Rancher UI.
- IDS/IPS: Suricata corriendo en nodo Master (Kali) y nodo Worker (Ubuntu) para detección de intrusiones a nivel de red y pods.
- SIEM: Wazuh desplegado en pfSense para monitoreo centralizado, correlación de eventos y alertas de seguridad perimetral.

### Ansible Playbooks - IaC
Scripts de Infraestructura como Código (IaC) para gestión de flotas de servidores.
- apacheinstalacion.yml: Playbook multi-OS con lógica condicional que detecta la familia del SO (ansible_os_family). Instala Apache en entornos Debian/Ubuntu (apt) y RHEL/CentOS (dnf).
- info.yml: Herramienta de auditoría que extrae en tiempo real Hostname, IP, interfaces de red y puntos de montaje de todos los servidores del inventario.

### TP Final Python - Talento Tech
Proyecto enfocado en la resolución de problemas mediante lógica de programación, manejo de estructuras de datos y automatización.
- Certificación: Ministerio de Educación (CABA) - 80 horas reloj.

### Tienda Online - Flask + Docker + Jenkins CI/CD
Aplicación web de ecommerce con pipeline CI/CD completo.
- Stack: Python, Flask, Docker, Jenkins, GitHub
- Pipeline: git push → Jenkins → Docker build → Deploy automático
- Features: Login, registro, carrito de compras

### Kafka Lab - Docker + Rancher
Laboratorio de Apache Kafka con mensajería en tiempo real.
- Stack: Kafka, Docker, Rancher, Kali Linux
- Features: KRaft mode, topics, productor/consumidor en tiempo real

### Proyecto Nuevo Web - Railway Deploy
Aplicación Python (Flask + Gunicorn) desplegada automáticamente en Railway desde GitHub.  
Cada push al repo reconstruye el contenedor y actualiza la aplicación en producción.

- Stack: GitHub + Railway + Python + Flask + Gunicorn + Dockerfile  
- Demo: https://proyecto-nuevo-web-production.up.railway.app/

Flujo ASCII:

                ┌───────────────────────────┐
                │       GitHub Repo         │
                │  proyecto-nuevo-web       │
                │  - app.py (Flask)         │
                │  - requirements.txt       │
                │  - Dockerfile             │
                └─────────────┬─────────────┘
                              │
                              │ conectado automáticamente
                              ▼
                ┌───────────────────────────┐
                │         Railway           │
                │   - detecta Dockerfile    │
                │   - instala dependencias  │
                │   - construye contenedor  │
                │   - arranca Gunicorn      │
                └─────────────┬─────────────┘
                              │
                              │ despliega contenedor
                              ▼
                ┌───────────────────────────┐
                │   Infra Railway interna   │
                │   - ejecuta tu contenedor │
                │   - expone puerto (5000)  │
                │   - asigna URL pública    │
                └─────────────┬─────────────┘
                              │
                              ▼
                ┌───────────────────────────┐
                │     Usuario / Portfolio   │
                │   Accede vía URL pública  │
                │   Ej: https://proyecto-nuevo-web-production.up.railway.app/
                │   Muestra la app Flask    │
                └───────────────────────────┘

---

## 🏗️ K8s Security Lab — Arquitectura

INTERNET / MÓDEM
        │
        ▼
┌──────────────────────────────┐
│       GATEWAY pfSense        │
├──────────────────────────────┤
│ WAN (em0): 10.0.2.15 (NAT)  │
│ LAN (em1): 192.168.56.2     │
└──────────────┬───────────────┘
               │
┌──────────────┴──────────────────────────────┐
│         HOST-ONLY NETWORK 192.168.56.0/24   │
▼                                             ▼
┌──────────────────────┐      ┌──────────────────────┐
│   MASTER — Kali      │      │  WORKER — Ubuntu     │
├──────────────────────┤      ├──────────────────────┤
│ 192.168.56.104       │◄────►│ 192.168.56.101       │
│ NAT: 10.0.2.15       │      │ NAT: 10.0.2.15       │
├──────────────────────┤      ├──────────────────────┤
│ kube-apiserver :6443 │      │ containerd           │
│ etcd                 │      │ kubelet              │
│ Rancher UI           │      │ pods / workloads     │
│ k3s server           │      │                      │
└──────────────────────┘      └──────────────────────┘

---

## 💼 Experiencia

Empresa         | Rol                                | Período
---------------|-------------------------------------|------------------
Banco Macro    | Administrador Unix/Linux & DevOps   | 2020 - Actualidad
Freelancer     | DevOps & SysAdmin                   | 2017 - 2020
Claro          | Administrador Unix                  | 2013 - 2017
Ericsson       | Analista de Incidentes              | 2012 - 2013
HP             | Analista de Seguridad SOC/IAM       | 2011 - 2012

---

## 🎓 Certificaciones & Educación

Amazon Web Services (AWS)
- AWS Educate: Getting Started with Storage
- AWS Educate: Getting Started with Compute
- AWS Certified Cloud Practitioner

Cybersecurity (IBM)
- IBM SkillsBuild: Cybersecurity Certificate

Red Hat
- Red Hat Certified Engineer (RHCE) y RHCSA
- OpenShift/Containers (DO188)

Educación IT
- Analista de Sistemas — IFTS Nº12 | Egreso estimado Julio 2026
- Especialista Python — Talento Tech (Gobierno de la Ciudad de Buenos Aires) — 80hs

---

## 📊 GitHub Stats

https://github-readme-stats.vercel.app/api?username=guimore&show_icons=true&theme=dark

---

📫 ¿Hablamos de infraestructura? LinkedIn: https://linkedin.com/in/guido-mora-42170a1a9/
