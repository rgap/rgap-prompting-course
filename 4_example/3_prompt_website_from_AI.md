<CONTEXT>
    <PROJECT_CONTEXT>
    [Contexto del proyecto]
    </PROJECT_CONTEXT>

    <SYSTEM_TYPE>
    [Tipo de sistema]
    </SYSTEM_TYPE>

    <BUSINESS_DOMAIN>
    [Dominio de negocio]
    </BUSINESS_DOMAIN>
</CONTEXT>

<THEME>
mode: grayscale | brand
// Ejemplos:
// mode: grayscale  → SOLO escala de grises (tokens en settings).
// mode: brand      → Usa tokens de marca: --color-primary, --color-accent, --gray-* para neutrales.
</THEME>

<ROLE>
Desarrollador Frontend con conocimientos sólidos de UX/UI.
</ROLE>

<INTENT>
A partir de la IA provista en <INPUT>, generar un prototipo web estático, responsive y accesible (WCAG AA),
usando SOLO HTML y CSS (JavaScript únicamente si es estrictamente necesario), con ITCSS y BEM.
Crear una página HTML por cada ruta definida en la IA y enlazarlas entre sí según la navegación.
</INTENT>

<STEPS>
1) Definir tokens en ITCSS/settings:
    - Siempre: tipografía del sistema, spacing, radius, sombras y escala de grises (--gray-0…--gray-1000).
    - Si <THEME>.mode == "grayscale": usar exclusivamente --gray-*.
    - Si <THEME>.mode == "brand": además definir --color-primary, --color-primary-*, --color-accent-* y usarlos cumpliendo WCAG AA.
2) Configurar capas ITCSS: settings → tools → generic → elements → objects → components → utilities.
3) Crear `src/pages/*.html`: una página por cada ruta de la IA, con HTML5 semántico y clases BEM.
4) Implementar navegación coherente (header/nav/footer, breadcrumbs si aplica) y enlazar todas las rutas.
5) Construir componentes clave (formularios, tablas, cards, estados vacío/error) con BEM y estados :hover/:focus/:active/:disabled accesibles.
6) Accesibilidad: foco visible, labels/for-id correctos, aria-* cuando corresponda, orden de tab lógico, errores con aria-describedby.
7) (Opcional) JS mínimo y aislado si la interacción lo exige, sin comprometer accesibilidad.
8) Al finalizar, verificar y corregir TODOS los enlaces internos (rutas relativas correctas y archivos existentes). No generar ningún informe.
</STEPS>

<PARAMETERS>

<CONSTRAINTS>
    - Sin frameworks ni librerías externas.
    - Sin estilos inline (salvo width/height en imágenes si es necesario).
    - Paleta según <THEME>.mode:
    • grayscale → SOLO grises (--gray-*) con contraste WCAG AA.
    • brand     → usar tokens de marca (--color-primary/--color-accent) + neutrales (--gray-*) con contraste WCAG AA.
    - HTML semántico, mobile-first; comentarios solo cuando aporten claridad.
</CONSTRAINTS>

<DELIVERABLES>
    1) Código separado por archivos en bloques (usar separadores tipo: ===== src/pages/home.html =====).
    2) Tokens definidos en settings y uso consistente en las demás capas.
    3) Páginas HTML por ruta en `src/pages/*.html`, enlazadas según la IA.
    4) Componentes con BEM y estados de interacción accesibles.
    5) README breve con estructura ITCSS, ubicación de tokens y pautas de accesibilidad.
</DELIVERABLES>

<OUTPUT_FORMAT>
    - Entregar el código en bloques por archivo.
    - Incluir README (texto). Sin reporte de enlaces.
</OUTPUT_FORMAT>

</PARAMETERS>

<INPUT>
[pega aquí la salida completa de tu IA]
</INPUT>
