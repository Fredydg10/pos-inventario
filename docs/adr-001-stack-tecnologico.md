# ADR 001: Stack Tecnológico para POS e Inventario

## Fecha
2026-10-08

## Contexto
Necesitamos desarrollar un sistema de Punto de Venta (POS) e Inventario para pequeños negocios que requiera:
- Gestión de stock en tiempo real
- Transacciones ACID para ventas
- Interfaz rápida y responsiva
- Control de roles (cajero vs administrador)
- Generación de PDFs

## Decisión
Hemos seleccionado el siguiente stack tecnológico:

**Frontend:** Angular 18+ con TypeScript
**Backend:** Node.js con Express/NestJS
**Base de Datos:** PostgreSQL
**Cache:** Redis (para inventario en tiempo real)
**Estilos:** Tailwind CSS

## Alternativas Consideradas

### Frontend
- **React**: Más flexible pero requiere más decisiones de arquitectura
- **Vue.js**: Curva de aprendizaje más suave pero menos adoption empresarial

### Backend
- **Python (FastAPI/Django)**: Excelente para prototipado pero menor performance en I/O
- **Java Spring**: Muy robusto pero mayor complejidad y tiempo de desarrollo
- **Go**: Excelente performance pero curva de aprendizaje más pronunciada

### Base de Datos
- **MySQL**: Similar a PostgreSQL pero menos características avanzadas
- **MongoDB**: Más flexible pero no garantiza ACID en transacciones complejas

## Consecuencias Positivas
✅ Angular proporciona estructura opinionada ideal para equipos
✅ TypeScript ofrece tipado fuerte para prevenir errores en cálculos de ventas
✅ Node.js permite I/O no bloqueante para múltiples cajeros simultáneos
✅ PostgreSQL garantiza integridad de datos en transacciones financieras
✅ Stack conocido reduce tiempo de desarrollo

## Consecuencias Negativas
️ Angular tiene curva de aprendizaje más pronunciada que React/Vue
⚠️ Node.js no es ideal para CPU-intensive tasks (generación de PDFs podría requerir workers)
️ PostgreSQL requiere más recursos que SQLite para desarrollo local

## Estado
ACEPTADO

## Referencias
- TIOBE Index 2026
- Stack Overflow Developer Survey 2026
- Documentación oficial de Angular, Node.js, PostgreSQL