# Congreso 2025 - Guía para Agentes de IA

## 🌍 Convención Principal: Contenido en Español
**CRÍTICO**: Todo el contenido del sitio, nombres de clases CSS, variables, comentarios y texto visible debe estar en español. Este es un proyecto para un congreso académico hispanohablante.

## 🏗️ Arquitectura del Proyecto
- **Framework**: Astro con TypeScript para máximo rendimiento estático
- **Estructura**: Componentes modulares reutilizables en `src/components/`
- **Estilos**: CSS nativo con variables globales en `:root` (sin framework CSS)
- **Diseño**: Inspirado en Apple con gradientes, glassmorphism y animaciones suaves

## 📂 Estructura de Archivos Clave
```
src/
├── pages/index.astro          # Página principal con todos los componentes
├── layouts/Layout.astro       # Layout base con SEO y variables CSS globales
├── components/
│   ├── Navigation.astro       # Navegación fija con hamburger menu
│   ├── HeroSimple.astro      # Sección hero principal
│   ├── Stats.astro           # Contadores animados
│   ├── Sedes.astro           # Grid de tarjetas de instituciones
│   └── Colaboradores.astro   # Grid de logos colaboradores
public/
└── SEDES Y COLABORADORES CONGRESO 2025/  # Imágenes organizadas por sede
```

## 🎨 Sistema de Diseño
### Variables CSS (en `:root`)
- **Colores**: `--primary-color: #007AFF`, `--secondary-color: #5856D6`
- **Grises**: `--gray-50` hasta `--gray-900` (escala Tailwind)
- **Espaciado**: `--spacing-xs` hasta `--spacing-3xl`
- **Transiciones**: `--transition-fast/normal/slow`

### Patrones de Componentes
- **Secciones**: Siempre usar `.container` para centrado con max-width: 1200px
- **Headers**: `.section-header` + `.section-title` + `.section-subtitle`
- **Grids**: CSS Grid con `auto-fit` y `minmax()` para responsividad
- **Tarjetas**: Hover effects con `transform` y `box-shadow` progression

## 🔧 Comandos de Desarrollo
```bash
npm run dev        # Servidor desarrollo (puerto 4321)
npm run build      # Build producción
npm run preview    # Preview del build
```

## 📱 Responsividad
- **Mobile**: < 768px (grid a 1 columna)
- **Tablet**: 768px - 1024px 
- **Desktop**: > 1024px
- Usar `clamp()` para tipografía escalable: `clamp(2.5rem, 5vw, 4rem)`

## 🎯 Patrones Específicos del Proyecto

### Animaciones
- **AOS**: Usar `data-aos="fade-up"` con `data-aos-delay` incremental
- **Hover effects**: `transform: translateY(-4px) scale(1.02)` en tarjetas
- **Contadores**: Stats con animación JavaScript usando Intersection Observer

### Imágenes de Sedes/Colaboradores
- Ruta: `SEDES Y COLABORADORES CONGRESO 2025/[NOMBRE SEDE]/`
- Usar `OptimizedImage.astro` componente con lazy loading
- Siempre incluir `alt` descriptivo en español

### Estructura de Datos
```typescript
interface Sede {
  id: string;
  title: string;        
  location: string;       
  description: string;  
  image: string;
  tags: string[];      
}
```

## 🚨 Errores Comunes a Evitar
- ❌ NO usar inglés en texto visible o clases CSS
- ❌ NO usar frameworks CSS externos (mantener CSS nativo)
- ❌ NO modificar la estructura de carpetas de imágenes
- ❌ NO omitir el componente `Layout.astro` en páginas

## ✅ Al Crear Nuevos Componentes
1. Usar extensión `.astro` con frontmatter TypeScript
2. Importar tipografías y variables desde layout global
3. Seguir patrón de responsive con CSS Grid/Flexbox
4. Incluir efectos hover sutiles con transiciones suaves
5. Mantener todas las strings y clases en español
6. Usar `OptimizedImage` para cualquier imagen externa

## 🎨 Efectos Visuales Característicos
- **Gradientes**: `linear-gradient(135deg, var(--primary-color), var(--secondary-color))`
- **Glassmorphism**: `backdrop-filter: blur(20px)` + `rgba(255,255,255,0.95)`
- **Shadows**: Escala desde `--shadow-sm` hasta `--shadow-2xl`
- **Border radius**: Usar `--border-radius-xl` (1rem) o `--border-radius-2xl` (1.5rem)