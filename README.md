🤖 Marketplace con Asesor de IA por Voz

🚀 Demo en Vivo

Prueba la aplicación aquí: https://cyber-product-verse.lovable.app
📜 Descripción del Proyecto
Este proyecto es un MVP (Minimum Viable Product) para un marketplace de nueva generación, desarrollado como respuesta a una prueba técnica. El objetivo principal fue construir una experiencia de compra futurista donde los usuarios no solo pueden navegar por productos, sino también interactuar con un asesor de IA por voz que ofrece recomendaciones contextuales y en tiempo real.
La aplicación simula una experiencia de compra personal y guiada, transformando una simple transacción en una conversación inteligente. El núcleo de la innovación reside en la integración de un sistema de Retrieval-Augmented Generation (RAG) que permite a la IA basar sus respuestas en los datos específicos de los productos almacenados en mi base de datos, garantizando relevancia y precisión.
✨ Características Principales
Interfaz de Marketplace Futurista: Navegación intuitiva por productos construida rápidamente con Lovable.
Asesor de IA por Voz: Ciclo completo de interacción por voz que incluye:
Speech-to-Text: Transcripción precisa de la voz del usuario a texto.
Text-to-Speech: Conversión de la respuesta de la IA en audio con una voz natural.
IA Contextual (RAG): Las respuestas de la IA no son genéricas. Se "aumentan" con información relevante recuperada en tiempo real desde una base de datos vectorial.
Búsqueda Semántica: El sistema entiende el significado de la pregunta del usuario, no solo las palabras clave, para encontrar los productos más relevantes.
Componente de Chat Flotante: Una UI de chat limpia, interactiva y autónoma que maneja toda la lógica de la IA.
🛠️ Stack Tecnológico
Área	Tecnología / Servicio	Propósito
Frontend	React, Lovable, TailwindCSS	Desarrollo rápido de la UI, componentización y diseño moderno.
Backend & Database	Supabase	Base de datos PostgreSQL, autenticación y almacenamiento de embeddings.
Búsqueda Vectorial	pgvector (Extensión de Supabase)	Almacenamiento y consulta de embeddings de productos para el sistema RAG.
IA & Voz	OpenAI API	
↳ Speech-to-Text	Whisper-1	Transcripción de alta fidelidad del audio del usuario.
↳ Embeddings	text-embedding-ada-002	Conversión de texto (productos y preguntas) a vectores numéricos.
↳ Generación de Texto	GPT-4 Turbo Preview	Razonamiento y generación de respuestas contextuales basadas en el RAG.
↳ Text-to-Speech	TTS-1-HD	Síntesis de voz natural y de alta calidad para las respuestas de la IA.
🏛️ Arquitectura y Flujo de Datos
El sistema está diseñado con una arquitectura desacoplada y un flujo de datos claro para el proceso de IA:
Entrada del Usuario (Voz/Texto): El usuario interactúa con el componente FloatingChat. Si es por voz, el navegador graba el audio.
Transcripción (Speech-to-Text): El audio se envía a la API Whisper de OpenAI, que lo convierte en texto.
Generación de Embedding: El texto de la pregunta se envía a la API de Embeddings de OpenAI para convertirlo en un vector numérico (ej. [0.02, 0.15, ..., -0.08]).
Recuperación de Contexto (Retrieval): Este vector se envía a una función RPC de Supabase (match_products). Esta función utiliza pgvector para realizar una búsqueda de similitud de coseno contra los embeddings de todos los productos en la base de datos, devolviendo los 3 productos más relevantes.
Aumento del Prompt (Augmentation): El contexto recuperado (la información de los productos similares) y el contexto del producto actual se inyectan en un prompt estructurado junto con la pregunta original del usuario.
Generación de Respuesta (Generation): El prompt final y enriquecido se envía a GPT-4, que genera una respuesta coherente y basada estrictamente en el contexto proporcionado.
Síntesis de Voz (Text-to-Speech): La respuesta de texto de GPT se envía a la API TTS de OpenAI, que la convierte en un archivo de audio MP3.
Salida al Usuario: El audio se reproduce automáticamente en el navegador, completando la conversación.
🚧 Desafíos y Soluciones
Durante el desarrollo, me encontré con un desafío significativo que demuestra mi capacidad de adaptación. La especificación original sugería el uso del SDK de Gemini Live. Sin embargo, enfrenté obstáculos persistentes relacionados con la disponibilidad del modelo y los límites de cuota (Error 404 Not Found y 429 Too Many Requests), incluso después de crear nuevos proyectos y cuentas.
En lugar de quedarme bloqueado, tomé una decisión estratégica alineada con un entorno de desarrollo real: pivotar hacia una solución probada y robusta. Decidí implementar el ciclo de voz completo utilizando la API de OpenAI.
Esta decisión me permitió:
Cumplir el Requisito Principal: Entregar una experiencia de voz de alta calidad.
Demostrar Resiliencia: No permitir que un obstáculo con una API de terceros detuviera el progreso del proyecto.
Mostrar Versatilidad Técnica: Integrar con éxito un stack alternativo (Whisper y TTS), demostrando un conocimiento más amplio del ecosistema de IA.
