# Conecta 4 - Entrenamiento con Q-Learning vs Minimax

Este proyecto implementa una versión del clásico juego **Connect Four** (Conecta 4) en Python, integrando distintos enfoques de inteligencia artificial para simular y comparar el rendimiento entre estrategias de **aprendizaje por refuerzo (Q-Learning)** y **búsqueda adversarial (Minimax y Minimax con poda Alpha-Beta)**.

---

## 🎯 Objetivo

Evaluar el rendimiento de un agente que aprende mediante **Q-Learning** (una técnica de **aprendizaje por diferencias temporales**) frente a oponentes que aplican algoritmos determinísticos como **Minimax** y **Minimax con poda Alpha-Beta**, en una serie de partidas simuladas.

---

## 📦 Estructura del Proyecto

- `ConnectFour`: clase que gestiona el estado del tablero y verifica condiciones de victoria.
- `QLearningAgent`: agente que aprende a jugar mediante Q-Learning con una política epsilon-greedy.
- `train_td`: función de entrenamiento para el agente Q-Learning.
- `minimax` y `minimax_alphabeta`: funciones de búsqueda de adversarios.
- `jugar_partido`: simula enfrentamientos entre agentes.
- `matplotlib`: utilizado para graficar los resultados de los enfrentamientos.

---

## 🤖 Entrenamiento

El agente TD se entrena jugando contra sí mismo durante una cantidad fija de partidas (por defecto 5,000). Durante estas partidas:

- Explora distintas acciones usando una política epsilon-greedy.
- Actualiza su tabla Q en cada turno.
- Aprende a identificar secuencias que lo llevan a ganar o evitar perder.

---

## ⚔️ Enfrentamientos

Se jugaron dos series de **50 partidas**:

- **Agente TD vs Minimax**
- **Agente TD vs Minimax con poda Alpha-Beta**

Se registró cuántas partidas ganó cada tipo de agente.

---

## 📊 Resultados

Los resultados se muestran gráficamente con barras que comparan el número de victorias del agente TD frente a sus oponentes estratégicos.

---

## 📌 Conclusiones

- El agente entrenado con TD Learning **no superó** a los algoritmos de búsqueda.
- Minimax y Alpha-Beta dominan desde el principio porque exploran el árbol de juego y evalúan mejores jugadas.
- El agente TD depende completamente del número de partidas jugadas, los hiperparámetros y la calidad de la función de recompensa.

### 🧠 ¿Qué mejorar?
- Aumentar el número de episodios de entrenamiento.
- Usar redes neuronales (Deep Q-Learning) en lugar de tablas Q.
- Reducir gradualmente el valor de `epsilon` para explorar menos con el tiempo.
- Aplicar funciones de evaluación más sofisticadas.

---

## ▶️ Requisitos

```bash
pip install numpy matplotlib json-c
```
Conclusión General
Este laboratorio 7 demuestra cómo la inteligencia artificial puede aplicarse a juegos clásicos como Conecta 4, permitiendo comparar enfoques basados en aprendizaje (Q-Learning) con estrategias deterministas (Minimax y Alpha-Beta). A través del entrenamiento y simulación de partidas, se evidencia que los métodos de búsqueda todavía tienen una ventaja clara frente a agentes que aprenden desde cero, especialmente cuando se usan tablas Q discretas y pocas partidas de entrenamiento.

Sin embargo, también se ilustra el potencial del aprendizaje por refuerzo para mejorar progresivamente mediante la experiencia. Con ajustes adecuados en los hiperparámetros, más entrenamiento y técnicas más modernas como Deep Q-Learning, el agente puede aspirar a competir en condiciones más justas contra algoritmos clásicos.

