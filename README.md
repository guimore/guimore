# Guido J. Mora Medina
## DevOps Engineer | SysAdmin | DevSecOps — Buenos Aires, Argentina
📧 mora.guido@gmail.com | 💼 [LinkedIn](https://linkedin.com/in/guido-mora-42170a1a9/) | 🐙 [GitHub](https://github.com/guimore)

---

## 🚀 Sobre mí
Especialista en Infraestructura IT con más de 15 años de trayectoria en entornos críticos de Banca y Telecomunicaciones. Experto en administración híbrida Linux/Unix, automatización CI/CD y arquitecturas cloud AWS. Perfil orientado a DevSecOps, integrando seguridad en cada etapa del pipeline. Experiencia en empresas líderes como Banco Macro, Claro, Ericsson y HP.

---

## 🛠️ Stack Tecnológico

**DevOps, Cloud & IaC**

![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazon-aws&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

**Sistemas Operativos**

![Red Hat](https://img.shields.io/badge/Red_Hat-EE0000?style=flat&logo=red-hat&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)
![Kali](https://img.shields.io/badge/Kali_Linux-557C94?style=flat&logo=kali-linux&logoColor=white)

**Seguridad & Networking**

![IBM Security](https://img.shields.io/badge/IBM_Security-052FAD?style=flat&logo=ibm&logoColor=white)
![pfSense](https://img.shields.io/badge/pfSense-212121?style=flat&logo=pfsense&logoColor=white)
![HAProxy](https://img.shields.io/badge/HAProxy-FF1010?style=flat&logo=haproxy&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00B4E0?style=flat&logoColor=white)
![Ethical Hacking](https://img.shields.io/badge/Ethical_Hacking-black?style=flat&logoColor=white)
![Suricata](https://img.shields.io/badge/Suricata-EF3B2D?style=flat&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-00A9CE?style=flat&logoColor=white)

---

## 📂 Proyectos Destacados

### 🦅 [K8s Security Lab - Kubernetes + pfSense](https://github.com/guimore/k8s-security-lab)
Laboratorio virtualizado de Kubernetes con firewall pfSense para práctica de seguridad ofensiva/defensiva y orquestación resiliente.
- **Arquitectura:** NAT (WAN) + Host-Only (LAN) con segmentación por zonas.
- **Seguridad:** RBAC, TLS habilitados y endurecimiento (Hardening) basado en normas de **IBM Cybersecurity**.
- **Orquestación:** Master en Kali, Workers en Ubuntu Server gestionados vía Rancher UI.
- **IDS/IPS:** Suricata corriendo en nodo Master (Kali) y nodo Worker (Ubuntu) para detección de intrusiones a nivel de red y pods.
- **SIEM:** Wazuh desplegado en pfSense para monitoreo centralizado, correlación de eventos y alertas de seguridad perimetral.

### 🤖 [Ansible Playbooks - IaC](https://github.com/guimore/ansible-playbooks)
Scripts de Infraestructura como Código (IaC) para gestión de flotas de servidores.
- **[apacheinstalacion.yml](https://github.com/guimore/ansible-playbooks/blob/main/apacheinstalacion.yml):** Playbook multi-OS con lógica condicional que detecta la familia del SO (`ansible_os_family`). Instala Apache en entornos **Debian/Ubuntu** (apt) y **RHEL/CentOS** (dnf).
- **[info.yml](https://github.com/guimore/ansible-playbooks/blob/main/info.yml):** Herramienta de auditoría que extrae en tiempo real Hostname, IP, interfaces de red y puntos de montaje de todos los servidores del inventario.

### 🐍 [TP Final Python - Talento Tech](https://github.com/guimore/tp_2025python)
Proyecto enfocado en la resolución de problemas mediante lógica de programación, manejo de estructuras de datos y automatización.
- *Certificación:* Ministerio de Educación (CABA) - 80 horas reloj.

### 🛒 [Tienda Online - Flask + Docker + Jenkins CI/CD](https://github.com/guimore/tienda-online)
Aplicación web de ecommerce con pipeline CI/CD completo.
- **Stack:** Python, Flask, Docker, Jenkins, GitHub
- **Pipeline:** git push → Jenkins → Docker build → Deploy automático
- **Features:** Login, registro, carrito de compras

### ⚡ [Kafka Lab - Docker + Rancher](https://github.com/guimore/kafka-lab)
Laboratorio de Apache Kafka con mensajería en tiempo real.
- **Stack:** Kafka, Docker, Rancher, Kali Linux
- **Features:** KRaft mode, topics, productor/consumidor en tiempo real

### 🛡️ Seguridad e Infraestructura Crítica
- Configuración de balanceadores de carga **HAProxy** para alta disponibilidad.
- Gestión de seguridad perimetral y reglas de firewall en **pfSense**.
- Monitoreo y endurecimiento de sistemas (**Hardening**) basado en los módulos de IBM SkillsBuild.

---

## 🏗️ K8s Security Lab — Arquitectura

```
INTERNET / MÓDEM
        │
        ▼
┌──────────────────────────────┐
│       GATEWAY pfSense        │
├──────────────────────────────┤
│ WAN (em0): 10.0.2.15 (NAT)  │  ◄── Perímetro
│ LAN (em1): 192.168.56.2     │  ◄── Red de Control
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
```

| Componente | Software | Rol | IP | RAM |
|---|---|---|---|---|
| pfSense | pfSense 2.7.2 | Firewall / Gateway + Wazuh | 192.168.56.2 | 1 GB |
| Master | Kali Linux | K8s Control Plane + Suricata | 192.168.56.104 | 5 GB |
| Worker | Ubuntu Server | K8s Worker Node + Suricata | 192.168.56.101 | 4 GB |
| Host | Windows 11 | Hypervisor VirtualBox | 192.168.56.1 | 16 GB |

**Segmentación de red:**

| Zona | Red | Propósito |
|---|---|---|
| WAN | 10.0.2.0/24 | Salida a internet via NAT |
| LAN | 192.168.56.0/24 | Red interna del laboratorio |
| Pod Network | 10.244.0.0/16 | Comunicación inter-pod (Flannel) |
| Service Net | 10.96.0.0/12 | Servicios internos de Kubernetes |

**Objetivos del laboratorio:**
- [x] Segmentación de red con pfSense como firewall perimetral
- [x] Cluster Kubernetes completo con kubeadm
- [x] Orquestación de contenedores con containerd
- [x] Gestión del cluster con Rancher UI
- [x] etcd persistido en SSD
- [x] Swap deshabilitado en todos los nodos
- [x] RBAC y TLS habilitados
- [ ] Deploy de aplicaciones vulnerables para pentesting
- [ ] Network Policies para aislamiento de pods
- [ ] Monitoreo con Prometheus + Grafana
- [ ] Práctica ofensiva con herramientas de Kali

---

## 💼 Experiencia

| Empresa | Rol | Período |
|---|---|---|
| **Banco Macro** | Administrador Unix/Linux & DevOps | 2020 - Actualidad |
| **Freelancer** | DevOps & SysAdmin | 2017 - 2020 |
| **Claro** | Administrador Unix | 2013 - 2017 |
| **Ericsson** | Analista de Incidentes | 2012 - 2013 |
| **HP** | Analista de Seguridad SOC/IAM | 2011 - 2012 |

---

## 🎓 Certificaciones & Educación

### ☁️ Amazon Web Services (AWS)
- **AWS Educate:** [Getting Started with Storage](https://www.credly.com/badges/e2af2623-96f6-4e8d-94fb-09bdf530a829/public_url) — Gestión de S3 y persistencia de datos.
- **AWS Educate:** [Getting Started with Compute](https://www.credly.com/badges/3006a88e-499c-4860-9189-873961168128/public_url) — Implementación de instancias EC2.
- **AWS Certified Cloud Practitioner** — VPC, Lambda, S3, RDS, IAM, DynamoDB.

### 🔐 Cybersecurity (IBM)
- **IBM SkillsBuild:** [Cybersecurity Certificate](https://www.credly.com/badges/a34271a1-9884-45bc-9820-390d12494c74) — Vulnerability Management, SOC, Incident Response, Cloud Security, Forensics.

### 🐧 Red Hat
- 🏆 **Red Hat Certified Engineer (RHCE)** y **RHCSA** — Ansible (RH294)
- 🏆 **OpenShift/Containers (DO188)**

### 🎓 Educación IT
- **Analista de Sistemas** — IFTS Nº12 | Egreso estimado Julio 2026
- **Especialista Python** — Talento Tech (Gobierno de la Ciudad de Buenos Aires) — 80hs

---

## 📊 GitHub Stats

![Guido's GitHub stats](https://github-readme-stats.vercel.app/api?username=guimore&show_icons=true&theme=dark)

---

📫 **¿Hablamos de infraestructura?** [LinkedIn](https://linkedin.com/in/guido-mora-42170a1a9/)
