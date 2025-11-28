# Tarea 4: Reinforcement Learning - Q-Learning

**Curso:** TICS315 - Inteligencia Artificial  
**Implementación:** Q-Learning aplicado a un entorno de juego 2D con grid

## 📋 Descripción

Este proyecto implementa un agente de **Reinforcement Learning** utilizando el algoritmo **Q-Learning** para navegar en un entorno de juego donde un héroe 🙃 debe:

- ✅ Recolectar trofeos 🏆
- ❌ Evitar zombies 🧟 (o vencerlos con espada 🗡️)
- 🔑 Conseguir llaves para abrir puertas 🚪
- 🚫 Navegar evitando obstáculos

## 🎮 Elementos del Juego

| Emoji | Elemento | Descripción |
|-------|----------|-------------|
| 🙃 | Héroe | Agente controlado por Q-Learning |
| 🏆 | Trofeo | Objetivo principal (+100 pts) |
| 🧟 | Zombie | Enemigo (-100 sin espada, +50 con espada) |
| 🔑 | Llave | Permite abrir puertas (+75 pts) |
| 🚪 | Puerta | Requiere llave para pasar |
| 🗡️ | Espada | Permite vencer zombies (+75 pts) |
| 🚫 | Bloque | Obstáculo infranqueable |
| ⚪ | Vacío | Espacio libre (-1 pt por movimiento) |

## 🚀 Instalación y Ejecución

### Prerrequisitos

- Python 3.12+ (compatible con 3.8+)
- pip (gestor de paquetes)

### Pasos de Instalación

```bash
# 1. Clonar el repositorio
git clone https://github.com/Kanitops/Tarea-4-IA.git
cd Tarea-4-IA

# 2. Crear entorno virtual (opcional pero recomendado)
python3 -m venv .venv
source .venv/bin/activate  # En Windows: .venv\Scripts\activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Ejecutar Jupyter Lab
jupyter lab
```

### Ejecución del Notebook

1. Abrir `Tarea 4 - RL - Q-Learning - Solucion.ipynb`
2. Ejecutar todas las celdas en orden (Cell → Run All)
3. Observar el entrenamiento y resultados

## 📊 Resultados del Entrenamiento

El agente logra una mejora significativa durante el entrenamiento:

- **Episodios de entrenamiento:** 400
- **Recompensa promedio inicial:** ~193 puntos
- **Recompensa promedio final:** ~2312 puntos
- **Mejora total:** +1097.8% 🎯
- **Estados explorados:** 429 únicos

### Visualización del Aprendizaje

![Gráfica de aprendizaje](docs/learning_curve.png)

La gráfica muestra:
- **Izquierda:** Progresión episodio a episodio con media móvil
- **Derecha:** Comparación boxplot primeros vs últimos 50 episodios

## 🧠 Algoritmo Q-Learning

### Fórmula Implementada

```
Q_nuevo(s, a) = Q(s, a) + α * [r + γ * max(Q(s', a')) - Q(s, a)]
```

Donde:
- `s`: Estado actual
- `a`: Acción tomada
- `r`: Recompensa recibida
- `s'`: Nuevo estado
- `α`: Tasa de aprendizaje (learning rate)
- `γ`: Factor de descuento (discount factor)

### Hiperparámetros Utilizados

```python
N_EPISODES = 400           # Total de episodios de entrenamiento
MAX_EPISODE_STEPS = 200    # Pasos máximos por episodio
gamma = 0.95               # Factor de descuento (valora futuro)
alpha = 1.0 → 0.05         # Tasa de aprendizaje decreciente
epsilon = 0.4 → 0.05       # Exploración ε-greedy decreciente
```

## 📝 Preguntas Resueltas

El notebook incluye respuestas detalladas a 7 preguntas pedagógicas:

1. ✅ Implementación de bloques, puertas y llaves
2. ✅ Sistema de espada para vencer zombies
3. ✅ Ajuste de hiperparámetros para mapas complejos
4. ✅ Justificación técnica de los cambios
5. ✅ Análisis de recompensas negativas por movimiento

## 📁 Estructura del Proyecto

```
Tarea-4-IA/
├── README.md                                    # Este archivo
├── AGENTS.md                                    # Guía para desarrolladores
├── requirements.txt                             # Dependencias Python
├── Tarea 4 - RL - Q-Learning (1).ipynb         # Notebook original (plantilla)
├── Tarea 4 - RL - Q-Learning - Solucion.ipynb  # Notebook con soluciones
├── tarea4-IA-2025 (1).pdf                      # Instrucciones de la tarea
├── rubrica-tarea-IA-RL (1).xlsx                # Rúbrica de evaluación
└── .gitignore                                   # Archivos ignorados por Git
```

## 🛠️ Tecnologías Utilizadas

- **Python 3.13.7**
- **NumPy** - Operaciones numéricas y matrices
- **Jupyter Lab** - Entorno interactivo
- **Matplotlib** - Visualización de resultados

## 👥 Autores

- Integrante 1
- Integrante 2
- Integrante 3
- Integrante 4

## 📚 Referencias

- Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction*
- Material del curso TICS315 - Inteligencia Artificial
- [OpenAI Gym Documentation](https://gymnasium.farama.org/)

## 📄 Licencia

Este proyecto es material académico para el curso TICS315.

---

**Fecha de última actualización:** 28 de noviembre de 2025
