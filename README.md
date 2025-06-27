# 🤖 Marketplace con Asesor de IA por Voz

🚀 [**Aplicación desplegada**](https://cyber-product-verse.lovable.app)

🎥 [**Video Explicativo**](https://drive.google.com/file/d/1CLDRoDpZIJZseELxJEJYvLFBmjQCH8fE/view?usp=sharing)

---

## 📜 Descripción del Proyecto

Este proyecto es un **MVP (Minimum Viable Product)** para un marketplace de nueva generación, desarrollado como respuesta a una prueba técnica.

El objetivo principal fue construir una experiencia de compra **futurista** donde los usuarios no solo pueden navegar por productos, sino también **interactuar con un asesor de IA por voz** que ofrece recomendaciones **contextuales y en tiempo real**.

La aplicación simula una experiencia de compra personal y guiada, transformando una simple transacción en una **conversación inteligente**, gracias a la integración de un sistema de **Retrieval-Augmented Generation (RAG)**. Este sistema permite que la IA base sus respuestas en **datos específicos de los productos** almacenados en la base de datos, garantizando relevancia y precisión.

---

## ✨ Características Principales

- 🎨 **Interfaz de Marketplace Futurista**  
  Navegación intuitiva por productos construida rápidamente con Lovable.

- 🧠 **Asesor de IA por Voz**  
  Ciclo completo de interacción por voz que incluye:
  - **Speech-to-Text (Whisper)**: Transcripción precisa del audio del usuario.
  - **Embeddings (text-embedding-ada-002)**: Conversión de texto a vectores para recuperación semántica.
  - **Generación de Respuesta (GPT-4 Turbo)**: IA contextual que responde con base en los productos recuperados.
  - **Text-to-Speech (TTS-1-HD)**: Respuesta de la IA en audio con voz natural.

- 🔎 **Búsqueda Semántica**  
  El sistema entiende el significado de la consulta, no solo palabras clave, para encontrar productos relevantes.

- 💬 **Componente de Chat Flotante**  
  UI limpia e interactiva que maneja toda la lógica del asistente conversacional.

---

## 🛠️ Stack Tecnológico

| Área              | Tecnología / Servicio            | Propósito |
|-------------------|----------------------------------|-----------|
| **Frontend**      | React, Lovable, TailwindCSS      | UI rápida, moderna y componentizada |
| **Backend**       | Supabase                         | Base de datos (PostgreSQL), autenticación, almacenamiento |
| **Búsqueda RAG**  | pgvector (extensión de Supabase) | Almacenamiento y recuperación de embeddings |
| **IA & Voz**      | OpenAI API                       | Módulos de IA y síntesis de voz |

---

### 🔍 Modelos de OpenAI Utilizados

| Función             | Modelo OpenAI              |
|---------------------|----------------------------|
| Transcripción       | `Whisper-1`                |
| Embeddings          | `text-embedding-ada-002`   |
| Generación de texto | `gpt-4-turbo-preview`      |
| Text-to-Speech      | `tts-1-hd`                 |

---

## 🏛️ Arquitectura y Flujo de Datos

```plaintext
🎙️ Entrada del Usuario (Voz/Texto)
   ↓
🗣️ Transcripción (Speech-to-Text - Whisper)
   ↓
🔢 Embedding del Texto (OpenAI Embeddings)
   ↓
🔍 Recuperación de Productos (RPC Supabase + pgvector)
   ↓
📦 Inyección de Contexto (Augmented Prompt)
   ↓
🤖 Generación de Respuesta (GPT-4 Turbo)
   ↓
🔊 Síntesis de Audio (Text-to-Speech)
   ↓
🧏‍♂️ Reproducción Automática en Navegador
```
---

## 📩 Contacto

Puedes contactarme a través de:

- ✉️ **Correo:** [jblancomarquez54@gmail.com]
- 💼 **LinkedIn:** [https://www.linkedin.com/in/juan-pablo-blanco-marquez-b61797279/](https://www.linkedin.com/in/juan-pablo-blanco-marquez-b61797279/)
- 🧠 **Portafolio / GitHub:** [https://github.com/juanpa544](https://github.com/juanpa544)

> ¡Estoy abierto a nuevas oportunidades, colaboraciones y retos técnicos interesantes!

---

## 🙌 Gracias por tomarte el tiempo de revisar este proyecto!

---

