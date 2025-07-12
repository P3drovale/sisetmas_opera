# Funciones del Simulador de Interrupciones Linux

## Funciones de Utilidad y Sistema

```c
void get_timestamp(char *buffer, size_t size)
```

## Funciones de Trazabilidad

```c
void add_trace(const char *event)
void add_trace_with_irq(const char *event, int irq_num)
void add_trace_silent(const char *event)
void add_trace_with_irq_silent(const char *event, int irq_num)
void set_log_level(log_level_t level)
void toggle_timer_logs(void)
void add_trace_smart(const char *event, int irq_num, int is_timer_related)
```

## Funciones de Validación y Estado

```c
int validate_irq_num(int irq_num)
int is_irq_available(int irq_num)
const char* get_irq_state_string(irq_state_t state)
```

## Funciones de Inicialización

```c
void init_idt()
void init_system_stats()
void update_stats(int irq_num, unsigned long execution_time)
```

## Funciones de Registro de ISR

```c
int register_isr(int irq_num, void (*isr_function)(int), const char *description)
int unregister_isr(int irq_num)
```

## Función de Despacho

```c
void dispatch_interrupt(int irq_num)
```

## Funciones ISR (Interrupt Service Routines)

```c
void timer_isr(int irq_num)
void keyboard_isr(int irq_num)
void custom_isr(int irq_num)
void error_isr(int irq_num)
```

## Función de Hilo

```c
void* timer_thread_func(void* arg)
```

## Funciones de Visualización y Estado

```c
void show_idt_status()
void show_recent_trace()
int is_timer_related_trace(const trace_entry_t *entry)
void show_last_trace()
void show_last_n_non_timer_traces(int n)
void debug_trace_buffer()
void show_system_stats()
void show_help()
void show_menu()
void logging_submenu()
```

## Funciones de Pruebas

```c
void run_interrupt_test_suite(void)
void test_concurrent_interrupts()
void test_stress_interrupts()
```

## Funciones de Entrada y Control

```c
void clear_input_buffer()
int get_valid_input(int min, int max)
void wait_for_enter()
void improved_main_initialization()
```

## Función Principal

```c
int main()
```

---

**Total de funciones:** 32 funciones

**Categorías principales:**
- **Sistema y utilidades:** 1 función
- **Trazabilidad y logging:** 7 funciones  
- **Validación:** 3 funciones
- **Inicialización:** 3 funciones
- **Manejo de ISR:** 3 funciones
- **ISR específicas:** 4 funciones
- **Hilos:** 1 función
- **Interfaz y visualización:** 9 funciones
- **Pruebas:** 3 funciones
- **Control de entrada:** 4 funciones
- **Principal:** 1 función