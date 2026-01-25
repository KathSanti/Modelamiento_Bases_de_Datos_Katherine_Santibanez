# Evaluación Experiencia 1 - Modelo de Base de Datos (MER-E)

Este repositorio contiene el diseño del **Modelo Entidad-Relación Extendido (MER-E)** para la compañía **HiLogic Solutions**, una empresa especializada en la comercialización de productos tecnológico
## Decisiones de Modelamiento

### 1. Jerarquías y Especialización (MER-E)
Se implementaron supertipos y subtipos para manejar reglas de negocio específicas:
* **Contratos:** Se divide en `INDEFINIDO` (con AFP y Salud obligatorios) y `PRACTICANTE` (con compensación y género opcionales).
* **Clientes:** Se clasifica en `VIP` (descuento porcentual) y `NORMAL` (descuento fijo en pesos).

### 2. Entidades Débiles e Identificación
* **Contrato:** Se definió como una entidad dependiente de `SUCURSAL`. La relación es identificadora (línea sólida) porque el número de contrato se liga directamente a la sede de contratación y no se permiten traslados.

### 3. Gestión de Inventario
* Se creó la entidad asociativa `STOCK` para resolver la relación de muchos a muchos entre `SUCURSAL` y `PRODUCTO`, permitiendo controlar la cantidad disponible por cada bodega específica (con un límite de 3,000 unidades).

### 4. Relaciones Críticas
* **Cargo-Trabajador:** Un trabajador solo puede tener un cargo a la vez.
* **Cargo-Practicante:** Se estableció una relación opcional, permitiendo que un alumno pasante pueda o no tener un cargo asignado durante su capacitación.
