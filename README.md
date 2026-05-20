# sistema-reservas-hotel-unad[README.md](https://github.com/user-attachments/files/28073206/README.md)
# 🏨 Sistema de Reservas de Hotel
### Curso: Programación 213023 | UNAD | Fase 4 – Prácticas Simuladas

---

## 📋 Descripción

Sistema de gestión de reservas de hotel desarrollado en **Python** con enfoque en **Programación Orientada a Objetos (POO)** y **manejo robusto de excepciones**. El sistema permite realizar y cancelar reservas, solicitar servicios del hotel y gestionar la disponibilidad de habitaciones, registrando todos los eventos en un archivo de log.

---

## 🎯 Objetivo de Aprendizaje

> Implementar el manejo de excepciones en el desarrollo de aplicaciones orientadas a objetos buscando estabilidad y robustez, permitiendo una gestión adecuada de errores en el funcionamiento de las soluciones.

---

## 👥 Integrantes del Grupo

| Nombre | Usuario GitHub | Rama |
|--------|---------------|------|
| Daniel Alejandro Guio | @daniel-guio | `feature/daniel` |

---

## 🗂️ Estructura del Repositorio

```
sistema-reservas-hotel/
│
├── 📓 sistema_hotel.ipynb       # Jupyter Notebook principal (ejecutar aquí)
├── 🐍 sistema_hotel.py          # Código fuente Python
├── 📋 hotel_log.txt             # Log generado tras la ejecución
├── 📄 Fase4_Informe_Grupo.pdf   # Documento de entrega en PDF
└── 📖 README.md                 # Este archivo
```

---

## ⚙️ Tecnologías Utilizadas

- **Python 3.10+**
- **Módulo `logging`** – registro de eventos
- **Módulo `datetime`** – manejo de fechas
- **Jupyter Notebook** – ejecución interactiva

---

## 🚀 Cómo ejecutar el proyecto

### Opción 1 – Jupyter Notebook (recomendado)
```bash
# 1. Clonar el repositorio
git clone https://github.com/usuario/sistema-reservas-hotel.git
cd sistema-reservas-hotel

# 2. Instalar Jupyter si no lo tienes
pip install notebook

# 3. Abrir el notebook
jupyter notebook sistema_hotel.ipynb
```
Ejecuta las celdas en orden con **Shift + Enter**.

### Opción 2 – Script Python directo
```bash
python sistema_hotel.py
```

---

## 🧩 Componentes del Sistema

### Excepciones Personalizadas
| Excepción | Cuándo se lanza |
|-----------|----------------|
| `HotelException` | Clase base de todas las excepciones del sistema |
| `HabitacionNoDisponibleError` | Habitación ya está ocupada |
| `ReservaInvalidaError` | Datos de reserva incorrectos o fallo de pago |
| `ClienteNoEncontradoError` | Cliente no registrado en el sistema |
| `ServicioNoDisponibleError` | Servicio del hotel fuera de operación |
| `PagoFallidoError` | Error en el procesamiento del pago |

### Estructuras de Manejo de Excepciones
- ✅ `try / except` — captura de errores esperados
- ✅ `try / except / else` — lógica de éxito separada del manejo de errores
- ✅ `try / finally` — registro garantizado al finalizar cada operación
- ✅ Encadenamiento de excepciones (`raise ... from e`)

### Habitaciones Disponibles
| Número | Tipo | Precio/Noche |
|--------|------|-------------|
| 101 | Simple | $80 |
| 102 | Simple | $80 |
| 201 | Doble | $150 |
| 202 | Doble | $150 |
| 301 | Suite | $300 |

---

## 🧪 Simulaciones Ejecutadas (14 en total)

| # | Descripción | Resultado |
|---|-------------|-----------|
| 1 | Reserva válida – Ana Torres, Hab. 101 | ✅ Confirmada |
| 2 | Reserva válida – Luis Pérez, Hab. 201 | ✅ Confirmada |
| 3 | Habitación 101 ya ocupada | ❌ HabitacionNoDisponibleError |
| 4 | Cliente no registrado 'Pedro Fictional' | ❌ ClienteNoEncontradoError |
| 5 | Fechas de entrada y salida iguales | ❌ ReservaInvalidaError |
| 6 | Fecha de entrada en el pasado | ❌ ReservaInvalidaError |
| 7 | Habitación 999 inexistente | ❌ ReservaInvalidaError |
| 8 | Reserva válida – María Gómez, Suite 301 | ✅ Confirmada |
| 9 | Servicio de spa – Ana Torres | ✅ Confirmado |
| 10 | Servicio 'bar_nocturno' no disponible | ❌ ServicioNoDisponibleError |
| 11 | Servicio con cliente no registrado | ❌ ClienteNoEncontradoError |
| 12 | Cancelar reserva #1 (válida) | ✅ Cancelada |
| 13 | Cancelar reserva #99 (no existe) | ❌ ReservaInvalidaError |
| 14 | Reservar Hab. 101 tras liberarla | ✅ Confirmada |

---

## 📝 Sistema de Logging

Todos los eventos se registran automáticamente en `hotel_log.txt`:

```
2026-05-20 19:43:47 | INFO  | Sistema de Reservas de Hotel iniciado correctamente.
2026-05-20 19:43:47 | INFO  | Reserva exitosa: Reserva #1 | Cliente: Ana Torres ...
2026-05-20 19:43:47 | ERROR | Error al hacer reserva: La habitación 101 no está disponible.
2026-05-20 19:43:47 | DEBUG | Proceso de reserva finalizado para cliente: Ana Torres
```

---

## 📚 Referencias

- Van Rossum, G., y Drake Jr, F. L. (2024). *El tutorial de Python – Errores y excepciones*. https://docs.python.org/es/3.12/tutorial/errors.html
- Cuevas Álvarez, A. (2016). *Python 3: curso práctico*. RA-MA Editorial.
- Romano, F., Baka, B., y Phillips, D. (2019). *Getting Started with Python*. Packt Publishing.

---

> **UNAD** – Escuela de Ciencias Básicas Tecnología e Ingeniería (ECBTI) | Ingeniería de Sistemas | 2026
