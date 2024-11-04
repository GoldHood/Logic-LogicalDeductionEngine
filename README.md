# Logic-LogicalDeductionEngine
🎲 Logical Deduction Engine 🤖 | 📜 Reglas de lógica | 🔍 Motor de Inferencia | 💡 Razonamiento Deductivo


# 🎲 Proyecto: Motor de Deducción Lógica con Ejercicios 🎲

👤 **Autor**: GoldHood
📝 **Nombre**: Martín Verastegui
📧 **Correo**: martin.verastegui@gmail.com
📅 **Fecha**: 3 de noviembre de 2024
🛠️ **Licencia**: MIT License
📂 **Repositorio**: [GitHub - Logic Logical Deduction Engine](https://github.com/GoldHood/Logic-LogicalDeductionEngine)

## ✨ Bienvenidos a nuestro Proyecto de Inferencia Lógica

¡Hola! 👋 Gracias por llegar hasta aquí. Este proyecto ha sido creado con mucho entusiasmo y dedicación para ayudarte a comprender mejor la lógica y el razonamiento deductivo. Queremos que este sea un espacio donde puedas explorar, aprender y divertirte mientras resuelves problemas que reflejan situaciones de la vida real. ¡Nos encantaría que te unas a nosotros en este viaje de descubrimiento! 🚀

### 📝 Descripción del Proyecto
Este proyecto es un motor de inferencia lógica basado en la librería **SymPy**. A través de tres **ejercicios prácticos**, exploramos cómo las reglas lógicas nos ayudan a deducir consecuencias a partir de hechos. Cada ejercicio refleja escenarios interesantes que están diseñados para conectarte con problemas cotidianos y sus posibles soluciones.

Nuestro objetivo es que **te sientas identificado** con estas historias, aprendas sobre lógica, y te diviertas viendo cómo una sola acción puede desencadenar un sinfín de resultados. Esperamos que esta experiencia sea enriquecedora y amena para ti. 😊

---

## 🌟 ¿Por qué este Proyecto?
Vivimos en un mundo donde tomar decisiones correctas es fundamental, y entender sus consecuencias puede ser todo un desafío. A través de estos ejercicios queremos demostrar que la **lógica puede ser divertida** y útil para navegar las decisiones de la vida. Cada problema está pensado para ser sencillo de entender, pero profundo en sus implicaciones, invitándote a pensar, reflexionar y, por qué no, ¡a reírte un poco! 😂

## 🧩 Ejercicios
A continuación, te presentamos los tres ejercicios que hemos desarrollado.

### 🎲 Ejercicio 1: Las Consecuencias de la Apuesta
Pedro ha decidido apostar en las carreras, pero ¿qué consecuencias traerá esto a su vida? 🤔 Este ejercicio explora las decisiones de Pedro y las respuestas de su familia. Es una historia que te hará reflexionar sobre cómo una sola acción puede afectar a todos a tu alrededor.

- **Reglas: Proposiciones y Consecuencias**
  1. Si **Pedro le apostó a las carreras** (P), entonces **se gastó el dinero** (Q).
  2. Si **Pedro se gastó el dinero** (Q), entonces **su esposa no compra joyas** (R) y **su esposa pide el divorcio** (Y).
  3. Si **su esposa no compra joyas** (R), entonces **los niños no comen** (S) o **su esposa está enojada** (T).
  4. **Pedro le apostó a las carreras** (P).
  5. Si **Pedro pide un préstamo** (Z), entonces **tiene dinero** (U).
  6. Si **Pedro tiene dinero** (U), entonces **su esposa puede comprar joyas** (¬R) y **no pedirá el divorcio** (¬Y).
  7. Si **los niños no comen** (S), entonces **el perro tampoco come** (V).
  8. Si **el perro no come** (V), entonces **Pedro siente remordimiento** (W).
  9. Si **Pedro siente remordimiento** (W), entonces **promete no apostar más** (X).

- **Propósito:** Mostrar cómo nuestras decisiones tienen consecuencias, y cómo la lógica nos permite navegar entre esas consecuencias. ¡Veamos si Pedro puede cambiar su destino! ✨

- **Ejemplo de Código:**
  ```python
  from sympy.logic.boolalg import Or, And, Not, Implies, to_cnf
  from sympy.logic.inference import satisfiable
  from sympy.abc import P, Q, R, S, T, U, V, W, X, Y, Z
  
  # Definir las reglas y la base de conocimiento (KB)
  reglas = [
      Implies(P, Q),                    # Si Pedro apuesta, gasta dinero.
      Implies(Q, And(R, Y)),            # Si gasta dinero, su esposa no compra joyas y pide el divorcio.
      Implies(R, Or(S, T)),             # Si no compra joyas, los niños no comen o su esposa se enoja.
      P,                                # Pedro apostó.
      Implies(Z, U),                    # Si pide préstamo, tiene dinero.
      Implies(U, And(Not(R), Not(Y))),  # Si tiene dinero, su esposa compra joyas y no pide divorcio.
      Implies(S, V),                    # Si los niños no comen, el perro tampoco.
      Implies(V, W),                    # Si el perro no come, Pedro siente remordimiento.
      Implies(W, X)                     # Si siente remordimiento, promete no apostar más.
  ]
  
  KB = And(*reglas)
  ```

### 💼 Ejercicio 2: La Economía del Futuro
¿Cómo se puede impulsar la economía de un país? 🌍 Este ejercicio te invita a reflexionar sobre los factores necesarios para el crecimiento económico, como la inversión, el dinero y el origen de los recursos. Aquí podrás ver cómo las reglas del juego cambian dependiendo de quién eres.

- **Reglas: Proposiciones y Consecuencias**
  1. Para que **el país salga adelante** (P), se requiere de **empresas** (E).
  2. Para **hacer una empresa** (E), se requiere **inversión** (I).
  3. Para **invertir** (I), se requiere **dinero** (D).
  4. Si **tengo una empresa** (T), entonces **tengo dinero** (D).
  5. Si **soy peruano** (Pe), **no tengo dinero** (¬D).
  6. Si **soy extranjero** (Ex), **tengo dinero** (D).
  7. **Soy peruano** (Pe).

- **Propósito:** Reflexionar sobre cómo los recursos y el origen de las personas influyen en la economía de un país, y cómo ciertas restricciones afectan el crecimiento. ¿Podremos hacer que el país salga adelante? 🌱

- **Ejemplo de Código:**
  ```python
  from sympy.logic.boolalg import And, Not, Implies, to_cnf
  from sympy.logic.inference import satisfiable
  from sympy import symbols
  from sympy.abc import P, E, I, D, T
  
  # Definir variables adicionales
  Pe = symbols('Pe')  # Soy peruano
  Ex = symbols('Ex')  # Soy extranjero

  # Definir las reglas en forma de implicaciones
  reglas = [
      Implies(P, E),                    # Para que el país salga adelante, se requiere de empresas.
      Implies(E, I),                    # Para hacer una empresa, se requiere inversión.
      Implies(I, D),                    # Para invertir, se requiere dinero.
      Implies(T, D),                    # Si tengo una empresa, entonces tengo dinero.
      Implies(Pe, Not(D)),              # Si eres peruano, no tienes dinero.
      Implies(Ex, D),                   # Si eres extranjero, tienes dinero.
      Pe                                # Soy peruano.
  ]

  KB = And(*reglas)
  ```

### 🍏 Ejercicio 3: La Lógica de Bajar de Peso
¿Quieres perder peso? Este ejercicio muestra cómo **hábitos simples** como hacer ejercicio, dormir bien y comer a la hora, afectan nuestro objetivo de salud. ¡Exploraremos la lógica detrás de nuestros hábitos diarios y su impacto en nuestra vida! 💪🍏

- **Reglas: Proposiciones y Consecuencias**
  1. Si **quiero bajar de peso** (B), debo **comer a la hora** (C), **hacer ejercicio** (D), **dormir bien** (E) y **no ver TV más de 1 hora al día** (F).
  2. Para **dormir bien** (E), debo **hacer ejercicio** (D).
  3. Para **ver TV menos de 1 hora** (F), debo **dormir bien** (E).
  4. **Siempre hago ejercicio** (D).
  5. Si **veo más de 1 hora de TV**, **me siento cansado** (G).
  6. Si **estoy cansado** (G), **no hago ejercicio** (¬D).
  7. Si **trabajo horas extra** (H), **no puedo comer a la hora** (¬C).
  8. Cada vez que **no duermo bien** (¬E), **como más durante el día** (I).
  9. Los **fines de semana** (J), suelo **ver más de 1 hora de TV** (¬F).

- **Propósito:** Ayudarte a ver cómo nuestros hábitos afectan nuestro objetivo de estar saludables y cómo podemos cambiar para mejorar. ¡El poder está en tus manos! ✨

- **Ejemplo de Código:**
  ```python
  from sympy.logic.boolalg import And, Not, Implies, Equivalent
  from sympy.logic.inference import satisfiable
  from sympy import symbols

  # Definir las variables proposicionales
  B, C, D, E, F, G, H, I, J = symbols('B C D E F G H I J')

  # Definir las reglas en forma de implicaciones lógicas
  reglas = [
      Implies(B, And(C, D, E, F)),     # Para bajar de peso, necesito comer a la hora, hacer ejercicio, dormir bien y no ver TV.
      Implies(E, D),                   # Para dormir bien, debo hacer ejercicio.
      Implies(F, E),                   # Para ver TV menos de 1 hora, debo dormir bien.
      Equivalent(D, True),             # Siempre hago ejercicio.
      Implies(Not(F), G),              # Si veo más de 1 hora de TV, me siento cansado.
      Implies(G, Not(D)),              # Si estoy cansado, no hago ejercicio.
      Implies(H, Not(C)),              # Si trabajo horas extra, no como a la hora.
      Implies(Not(E), I),              # Si no duermo bien, como más durante el día.
      Implies(J, Not(F))               # Los fines de semana veo más de 1 hora de TV.
  ]

  KB = And(*reglas)
  ```

## 🔍 ¿Cómo usar este Proyecto?
1. **Instalación**:
   - Clona el repositorio desde GitHub: `git clone https://github.com/GoldHood/Logic-LogicalDeductionEngine`
   - Instala las dependencias necesarias (principalmente **SymPy**): `pip install sympy`

2. **Ejecutar Ejemplos**:
   - Cada ejercicio está diseñado para ser ejecutado desde la terminal.
   - Simplemente navega hasta el archivo del ejercicio correspondiente y ejecuta `python ejercicioX.py` para interactuar con el motor de deducción.

3. **Personalización**:
   - Puedes modificar los hechos o las reglas según tu necesidad, y el sistema recalculará automáticamente las inferencias. ¡Experimenta y diviértete! 🌟

## 🤝 Contribuciones
Este proyecto está bajo la **MIT License**, y las contribuciones son **muy bienvenidas**. Siéntete libre de abrir **issues** o hacer un **pull request** para mejorar el sistema o añadir más ejemplos prácticos.

## 🎓 Objetivo
El objetivo es hacer que el pensamiento lógico sea **accesible y claro** para cualquier persona interesada en aprender. 🌍

Si tienes preguntas, sugerencias, o simplemente quieres conectar, contáctanos a través de [GitHub](https://github.com/GoldHood) o por correo electrónico en **martin.verastegui@gmail.com**.

---
**Recuerda**: La lógica es como un gran rompecabezas 🧩. Cada pieza encaja de una forma específica, y cuando todas encajan, se revela algo maravilloso. ¡Espero que disfrutes este viaje de aprendizaje tanto como nosotros disfrutamos creándolo para ti! 😊✨
