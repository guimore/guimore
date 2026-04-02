# Guido J. Mora Medina
## DevOps Engineer & SysAdmin | Buenos Aires, Argentina
📧 mora.guido@gmail.com | 💼 [LinkedIn](https://linkedin.com/in/guido-mora-42170a1a9/)

---

## 🚀 Sobre mí
Especialista en Infraestructura IT con más de 15 años de trayectoria en entornos críticos de Banca y Telecomunicaciones. Experiencia en administración híbrida Linux/Unix, automatización CI/CD y arquitecturas cloud AWS.

---

## 🛠️ Stack Tecnológico

**DevOps & Cloud**

![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazon-aws&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)

**Sistemas Operativos**

![Red Hat](https://img.shields.io/badge/Red_Hat-EE0000?style=flat&logo=red-hat&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)
![Kali](https://img.shields.io/badge/Kali_Linux-557C94?style=flat&logo=kali-linux&logoColor=white)

**Seguridad**

![Nessus](https://img.shields.io/badge/Nessus-00B4E0?style=flat&logoColor=white)
![Ethical Hacking](https://img.shields.io/badge/Ethical_Hacking-black?style=flat&logoColor=white)

---

## 📂 Proyectos

### 🛒 [Tienda Online - Flask + Docker + Jenkins CI/CD](https://github.com/guimore/tienda-online)
Aplicación web de ecommerce con pipeline CI/CD completo.
- **Stack:** Python, Flask, Docker, Jenkins, GitHub
- **Pipeline:** git push → Jenkins → Docker build → Deploy automático
- **Features:** Login, registro, carrito de compras

### ⚡ [Kafka Lab - Docker + Rancher](https://github.com/guimore/kafka-lab)
Laboratorio de Apache Kafka con mensajería en tiempo real.
- **Stack:** Kafka, Docker, Rancher, Kali Linux
- **Features:** KRaft mode, topics, productor/consumidor en tiempo real

### 🦅 [K8s Security Lab - Kubernetes + pfSense](https://github.com/guimore/k8s-security-lab)
Laboratorio virtualizado de Kubernetes con firewall pfSense para práctica de seguridad ofensiva/defensiva y orquestación de contenedores.
- **Stack:** Kubernetes, pfSense, Kali Linux, Ubuntu Server, Rancher, VirtualBox
- **Red:** NAT (WAN) + Host-Only (LAN) con segmentación por zonas
- **Features:** Control plane completo, worker node, Rancher UI, etcd en SSD, RBAC, TLS

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
| pfSense | pfSense 2.7.2 | Firewall / Gateway | 192.168.56.2 | 1 GB |
| Master | Kali Linux | K8s Control Plane | 192.168.56.104 | 5 GB |
| Worker | Ubuntu Server | K8s Worker Node | 192.168.56.101 | 4 GB |
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

## 🎓 Certificaciones

- 🏆 IBM Cybersecurity Specialist (2025)
- 🏆 Red Hat Certified Engineer (RHCE)
- 🏆 AWS Certified Cloud Practitioner
- 🏆 OpenShift/Containers (DO188)

---

## 📊 GitHub Stats

![Guido's GitHub stats](https://github-readme-stats.vercel.app/api?username=guimore&show_icons=true&theme=dark)
