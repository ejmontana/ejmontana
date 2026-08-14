<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=190&section=header&text=Enderson%20Monta%C3%B1a&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=32&desc=Tech%20Lead%20%C2%B7%20Full%20Stack%20%C2%B7%20Ingenier%C3%ADa%20de%20IA&descSize=18&descAlignY=52" width="100%"/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&pause=1200&center=true&vCenter=true&width=620&color=58A6FF&lines=Coordinador+de+Proyectos+%26+Tech+Lead;Agentes+aut%C3%B3nomos+con+Claude+Code+y+MCP;AWS+%C2%B7+Terraform+%C2%B7+Spec-Driven+Development;.NET+%C2%B7+Node.js+%C2%B7+React+Native+%C2%B7+SQL+Server" alt="Typing SVG" />

</div>

## 👋 Sobre mí

Soy **Coordinador de Proyectos y Tech Lead** en **Galilei Smart Solutions**: lidero el equipo técnico que construye el ecosistema completo de la empresa — web, móvil, APIs e infraestructura — y donde más invierto hoy es en **integrar IA de verdad en el ciclo de desarrollo y en el producto**: agentes autónomos, servidores MCP propios y desarrollo dirigido por especificaciones.

También estudio Medicina, y me gusta el cruce entre software y salud (de ahí [medi-dosis](https://github.com/ejmontana/medi-dosis)).

---

## 🤖 Ingeniería de IA

### Agentes autónomos

- **symphony-claude** — orquestador de agentes de larga duración: hace polling de **Linear** y despacha sesiones autónomas de **Claude Code** en workspaces aislados que implementan el ticket, abren el PR, atienden el code review y mergean. Concurrencia en dos niveles, reintentos con backoff exponencial, detección de stalls, pool SSH para ejecución distribuida, TUI propia de monitoreo y contabilidad de tokens/costo por sesión. **144 tests.**
- **Equipos multi-agente** en repos de producción: hasta 9 agentes especializados (arquitecto, revisor, tester, auditor de seguridad, DevOps) con flujo `spec → implement → test → security-audit → review → merge`.

### Model Context Protocol (MCP)

- **mcp-sqlserver** — servidor MCP de grado producción para SQL Server, publicado como paquete npm del equipo: 7 tools, clasificación de sentencias seguras/peligrosas con confirmación explícita, preview de filas afectadas, **auditoría automática en BD y backup previo de cada cambio**, modo readonly y multi-base de datos.
- **symphony-linear** — MCP server stdio que da a cada agente acceso a la API GraphQL de Linear sin exponer credenciales en el prompt.

### IA en producto

- **Triage de tickets de helpdesk con Gemini**: genera título, prioridad, módulo afectado y queries de diagnóstico sugeridas, con contexto real del negocio inyectado desde la BD.
- **Chatbot empresarial con tool-calling** de solo lectura sobre BD multi-tenant (Vercel AI SDK + Gemini, streaming): límite diario de tokens, rate limiting, sanitización de entrada y esquema inyectado solo en el primer mensaje.
- **Bots conversacionales multicanal**: recordatorios por lenguaje natural en Telegram (DeepSeek), respuestas con voz sintetizada (ElevenLabs) e imágenes (DALL·E), y chat por streaming contra un **LLM self-hosted** (Llama vía Ollama).

### Spec-Driven Development

- **spec-kit** adoptado en 6+ repos del equipo: constitución vinculante por repo, ciclo `specify → plan → tasks → implement`, y un workflow de CI (`speckit-validate`) que hace **enforcement automático en cada PR**.
- Escribí las **guías y el playbook de adopción** para el equipo; también aplico **AWS AI-DLC** para ingeniería inversa y migración planificada de sistemas legacy.

```mermaid
flowchart LR
    A["📋 Ticket en Linear"] --> B["🎼 symphony-claude<br/>orquestador"]
    B --> C["🤖 Agentes Claude Code<br/>workspaces aislados"]
    M["🔌 Servidores MCP<br/>SQL Server · Linear"] -. tools .-> C
    S["📐 spec-kit<br/>constitution · specs · plan"] -. gobierna .-> C
    C --> D["PR + code review"]
    D --> E["⚙️ GitHub Actions<br/>CI · speckit-validate · OIDC"]
    E --> F["☁️ AWS<br/>ECS · EC2 · S3/CloudFront"]
```

---

## ☁️ AWS e Infraestructura como Código

Migración real on-prem → AWS por fases, con **Terraform** modular (12 módulos, 11 stacks con state independiente y blast radius controlado):

- **Cómputo**: ECS Fargate, ECR, EC2 Windows/IIS, Application Auto Scaling
- **Red y entrega**: VPC, ALB, S3 + CloudFront (con CloudFront Functions), Route 53, ACM, VPN site-to-site
- **Datos**: RDS for SQL Server — migración nativa por backup/restore desde S3, **cutover < 15 min** con runbooks
- **Seguridad**: WAF (managed rules + rate limit), Secrets Manager, IAM con **OIDC de GitHub Actions** — cero credenciales de larga vida en CI/CD
- **Operación**: CloudWatch (alarmas), SNS, SES v2 con DKIM/SPF, AWS Budgets, bitácora y runbooks de cutover

---

## 🛠️ Stack

<div align="center">

**Backend & APIs**

<img src="https://skillicons.dev/icons?i=dotnet,cs,nodejs,nestjs,express,ts,graphql" alt="backend"/>

**Cloud & DevOps**

<img src="https://skillicons.dev/icons?i=aws,terraform,docker,githubactions,nginx,linux,powershell,bash" alt="devops"/>

**Frontend & Mobile**

<img src="https://skillicons.dev/icons?i=react,nextjs,astro,angular,tailwind,vite" alt="frontend"/>

**Datos & Plataformas**

<img src="https://skillicons.dev/icons?i=postgres,mysql,mongodb,supabase,redis,py" alt="data"/>

<br/>

![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Claude](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logo=claude&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-000000?style=for-the-badge&logo=modelcontextprotocol&logoColor=white)
![Expo](https://img.shields.io/badge/React_Native_·_Expo-000020?style=for-the-badge&logo=expo&logoColor=white)
![Odoo](https://img.shields.io/badge/Odoo_18-714B67?style=for-the-badge&logo=odoo&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-4285F4?style=for-the-badge&logo=googlegemini&logoColor=white)

</div>

---

## 🏢 Lo que construyo en Galilei

Como coordinador, lidero el desarrollo de un ecosistema empresarial completo:

| Producto | Qué es | Stack |
|---|---|---|
| **Gali360 / GaliSuite Web** | Back-office comercial y financiero multi-tenant con chatbot IA integrado | Next.js 16 · Supabase · Arquitectura Hexagonal + DDD |
| **GaliSales** | App móvil de ventas en campo: pedidos, cobranza, GPS tracking en background | React Native · Expo · EAS · Clean Architecture |
| **Gali BI** | App móvil de Business Intelligence con motor de KPIs estilo DAX | Expo · Supabase · RLS endurecido |
| **ERP web** | 16 módulos de negocio (facturación, cartera, bancos, logística…) | React · .NET Web API · SQL Server |
| **Hub bancario** | Conciliación de pagos multi-banco: webhooks con HMAC-SHA256, OAuth2, auto-conciliación | .NET 9 · N-Capas · multi-tenant |

**Integraciones empresariales**: SAP → ERP, puente REST para Microsoft Dynamics GP, WhatsApp Flows de Meta (cifrado RSA-OAEP + AES-GCM), y suites de addons custom para **Odoo 18** (POS, moneda dual, eCommerce con checkout por WhatsApp).

> El código de estos proyectos es privado por acuerdos de confidencialidad. Los detalles de arquitectura los cuento con gusto en una entrevista.

---

## 📌 Proyectos públicos

| Proyecto | Qué resuelve | Stack |
|---|---|---|
| **[medi-dosis](https://github.com/ejmontana/medi-dosis)** | Calculadora de dosificación con validación de fármacos de alto riesgo · [demo](https://medi-dosis.vercel.app) | React 19 · Zod |
| **[crud-user-admin](https://github.com/ejmontana/crud-user-admin)** | Full stack: API REST con JWT, carga de archivos y asistente con IA | Express · TS · SQL Server |
| **[portalCautivo](https://github.com/ejmontana/portalCautivo)** | Portal cautivo WiFi con panel de administración | React · TS |
| **[PortafolioV2](https://github.com/ejmontana/PortafolioV2)** | Portafolio profesional | Astro 5 |
| **[simulacion-newton](https://github.com/ejmontana/simulacion-newton)** | Simulación de las leyes de Newton · [demo](https://simulacion-newton.vercel.app) | React |

---

## 📊 GitHub

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=ejmontana&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true" height="165" alt="stats"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ejmontana&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" height="165" alt="langs"/>

<img src="https://streak-stats.demolab.com?user=ejmontana&theme=tokyonight&hide_border=true&locale=es" height="165" alt="streak"/>

</div>

---

## 📫 Contacto

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Enderson_Montana-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/endersonmontana)
[![Email](https://img.shields.io/badge/Email-enderson__josep%40hotmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:enderson_josep@hotmail.com)

<br/>

<img src="https://komarev.com/ghpvc/?username=ejmontana&color=58A6FF&style=flat-square&label=Visitas" alt="views"/>

<br/><br/>

<i>💻 "Leading teams, building complete solutions, shipping AI that works." </i>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=110&section=footer" width="100%"/>

</div>
