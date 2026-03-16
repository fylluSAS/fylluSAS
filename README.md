<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=36&pause=1000&color=00C853&center=true&vCenter=true&width=800&lines=Fyllu+%E2%80%94+Commerce+Engine;Estandarizando+el+comercio+conversacional+en+LATAM" alt="Fyllu" />
</p>

<p align="center">
  <strong>Amazon estandarizó la logística. Stripe estandarizó los pagos.</strong><br/>
  <strong>Fyllu estandariza el comercio conversacional.</strong>
</p>

---

## El Problema

En LATAM, **+70% de las PYMES venden por WhatsApp**. Pero sin estructura:

- 📉 **30-50% de ventas se pierden** por respuestas tardías
- 🔇 Cero datos sobre qué se vende, qué se pierde, por qué
- 📱 El "sistema" es un hilo de WhatsApp que nadie revisa
- 🔄 Más ventas = más personas contestando = más caos

**Las PYMES no necesitan más canales. Necesitan estructura en el canal que ya usan.**

---

## Commerce Engine

Nuestro producto principal: un **motor de agentes comerciales autónomos** que transforma conversaciones en operaciones.

<p align="center">
  <img src="https://img.shields.io/badge/Entiende-Intención_en_lenguaje_natural-00C853?style=for-the-badge" alt="Entiende"/>
  <img src="https://img.shields.io/badge/Consulta-Catálogo_en_tiempo_real-1976D2?style=for-the-badge" alt="Consulta"/>
  <img src="https://img.shields.io/badge/Genera-Órdenes_automáticas-FF6F00?style=for-the-badge" alt="Genera"/>
  <img src="https://img.shields.io/badge/Mide-Cada_interacción-7B1FA2?style=for-the-badge" alt="Mide"/>
</p>

**No es un chatbot.** Es la capa de inteligencia comercial que convierte cada conversación de WhatsApp en una oportunidad trazable: con intención detectada, catálogo consultado, orden generada y métricas emitidas.

---

## Arquitectura

```
┌─────────────────────────────────────────────────────────┐
│                    Commerce Engine                       │
│                                                         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌────────┐ │
│  │ Messaging│  │  Agent   │  │  Sales   │  │Catalog │ │
│  │ (WABA)   │→ │(Vertex AI│→ │ (Orders) │← │(Supabase│ │
│  └──────────┘  │ Gemini)  │  └──────────┘  │  )     │ │
│                └──────────┘       │         └────────┘ │
│                     ↑             ↓                     │
│              ┌──────────┐  ┌──────────┐                │
│              │  Agent   │  │ Analytics│                 │
│              │  Policy  │  │ (Metrics)│                 │
│              │(per tenant│  └──────────┘                │
│              │ Supabase)│                               │
│              └──────────┘                               │
└─────────────────────────────────────────────────────────┘
```

---

## Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi" alt="FastAPI"/>
  <img src="https://img.shields.io/badge/Vertex_AI-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" alt="Vertex AI"/>
  <img src="https://img.shields.io/badge/Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white" alt="Gemini"/>
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js"/>
  <img src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase"/>
  <img src="https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" alt="GCP"/>
  <img src="https://img.shields.io/badge/Cloud_Run-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" alt="Cloud Run"/>
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase"/>
  <img src="https://img.shields.io/badge/WhatsApp_API-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions"/>
</p>

---

## Principios

| Principio | Qué significa |
|-----------|--------------|
| 🏗️ **Clean Architecture** | El dominio tiene cero dependencias externas |
| 🧩 **Domain-Driven Design** | Bounded contexts, lenguaje ubicuo, modelos ricos |
| 🔌 **Adapter Pattern** | El dominio NO conoce al proveedor LLM |
| 👥 **Multi-tenant** | Cada negocio es un espacio aislado desde el día 1 |
| 📡 **Event-Driven** | Eventos de dominio para comunicación entre contextos |
| 📊 **Observable** | OpenTelemetry desde el día 1 — si no lo mides, no existe |

---

## Modelo B2B2C

```
  Fyllu (Commerce Engine)
         │
         ▼
  ┌─────────────┐     ┌──────────────┐
  │  PYME       │     │  Cliente     │
  │  (paga)     │────▶│  final       │
  │  Dashboard  │     │  (WhatsApp)  │
  └─────────────┘     └──────────────┘
```

- **Fyllu → PYME**: SaaS B2B — el negocio paga por Commerce Engine
- **PYME → Cliente**: El negocio usa Commerce Engine para atender a sus clientes
- **Todos ganan**: El negocio vende más, el cliente recibe mejor servicio, Fyllu crece

---

## Estado Actual

- 🟢 **PRD completo** con deep research de validación y riesgos
- 🟢 **Primer cliente confirmado** — tienda de ropa, inicio en días
- 🟢 **Arquitectura definida** — Clean/Hexagonal + DDD + Multi-tenant
- 🟡 **En curso**: Hardcore AI by 30X (12 sesiones — idea a producción)

---

<p align="center">
  <a href="https://fyllu.net">
    <img src="https://img.shields.io/badge/Web-fyllu.net-00C853?style=for-the-badge&logo=google-chrome&logoColor=white"/>
  </a>
  <a href="https://github.com/kiketach">
    <img src="https://img.shields.io/badge/Founder-@kiketach-100000?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</p>

<p align="center">
  <sub>Bogota, Colombia — Construyendo el futuro del comercio conversacional para LATAM</sub>
</p>
