# Project Architecture & Technical Blueprint: Human (2D + 3D Experience)

## 1. Executive Vision: The 2D + 3D Hybrid Web Platform
The **Human** project is designed as an interactive **2D + 3D hybrid web experience** that merges rich 2D typography, data visualizations, and interactive UI dashboards with real-time 3D WebGL scenes featuring human anatomy, biomechanics, and animal biology.

```mermaid
graph TD
    subgraph UI_Layer["2D UI & HUD Layer"]
        Hero[2D Cinematic Hero & Storytelling]
        HUD[Glassmorphic 3D Control HUD]
        DataCards[Interactive Anatomical & Biological Data Cards]
        LayerToggle[Layer Selectors: Skin / Muscular / Skeletal / Neural]
        ModeSwitch[2D Guided Reading Mode <--> 3D Interactive Inspection Mode]
    end

    subgraph Three_Layer["3D WebGL Canvas Engine"]
        Canvas[React Three Fiber Canvas]
        Camera[Cinematic Camera & Smooth OrbitControls]
        Lighting[Dynamic HDR Studio Lighting & Soft Shadows]
        Models[3D Human & Animal Meshes, GLTF/GLB Loaders]
        PostProcess[Bloom, Vignette, Depth of Field Shaders]
    end

    UI_Layer <-->|Bidirectional State Synchronizer (Zustand)| Three_Layer
```

---

## 2. 2D + 3D Interaction Paradigm

### 2.1 Coordinated 2D/3D Scrollytelling
- **Scroll-Driven Camera**: As the user scrolls through 2D narrative sections (e.g., *Skeletal Framework*, *Cardiovascular Dynamics*, *Comparative Animal Physiology*), the 3D camera smoothly moves, zooms, and focuses on the corresponding anatomical sub-mesh or organ in 3D space.
- **Pinpoint Hotspots & 3D Annotations**: Clicking 2D data points highlights 3D coordinate pins on the mesh; clicking a 3D organ opens a rich 2D detail card with metrics and biological insights.

### 2.2 Dual Viewport Modes
1. **Interactive 3D Stage Mode**: Full-screen 3D canvas with floating glassmorphic 2D HUD tools (rotation, zoom, wireframe/x-ray toggle, animation speeds, anatomical layers).
2. **Split 2D + 3D Inspector Mode**: 
   - *Left Column (2D)*: High-density data, anatomical breakdown, comparative metrics, historical and biological text.
   - *Right Column (3D)*: Real-time interactive model with mouse tracking, shader glow effects, and layer disassembly (explode view).

---

## 3. Technology Stack & Packages

### 3.1 Frontend & Core Framework
- **Framework**: [Next.js](https://nextjs.org/) 16.3.4 (App Router & Turbopack)
- **Runtime**: React 19.2.8 & TypeScript 5
- **Styling**: Tailwind CSS v4 & custom glassmorphism design tokens

### 3.2 3D Graphics & Animation Stack
- **Core 3D Engine**: `three` & `@types/three`
- **Declarative 3D Canvas**: `@react-three/fiber`
- **3D Ecosystem & Helpers**: `@react-three/drei` (OrbitControls, Stage, Float, MeshDistort, GLTF loaders)
- **Icons & UI Utilities**: `lucide-react`, `clsx`, `tailwind-merge`

---

## 4. Frontend Component Structure

```text
src/
├── app/
│   ├── globals.css                # Custom glassmorphism, glowing shaders, animations
│   ├── layout.tsx                 # App layout & font loading
│   └── page.tsx                   # Main 2D + 3D hybrid portal
├── components/
│   ├── 2d/
│   │   ├── Navigation.tsx         # Sleek glassmorphic navbar with view toggles
│   │   ├── HeroSection.tsx        # 2D typography hero with dynamic 3D background
│   │   ├── LayerController.tsx    # Layer switches (Skin / Muscle / Bone / Organs)
│   │   ├── AnatomyMetrics.tsx     # 2D data cards and vital statistics
│   │   └── ScrollySection.tsx     # Scroll-triggered narrative cards
│   ├── 3d/
│   │   ├── SceneContainer.tsx     # Responsive R3F Canvas wrapper
│   │   ├── HumanModelViewer.tsx   # Interactive 3D Human anatomy model
│   │   ├── AnimalModelViewer.tsx  # Interactive 3D Animal biology model
│   │   ├── StudioLighting.tsx     # Cinematic ambient, directional, and point lights
│   │   ├── Annotations.tsx        # 3D clickable pins linked to 2D UI
│   │   └── ViewportHUD.tsx        # In-canvas camera, wireframe, and lighting controls
│   └── ui/
│       ├── Button.tsx
│       ├── Card.tsx
│       └── Slider.tsx
├── hooks/
│   ├── use3DStore.ts              # Zustand/React state for active model, layers, and camera
│   └── useScrollPosition.ts       # Scroll listener for camera choreography
└── lib/
    └── utils.ts                   # Class name merging and 3D math helpers
```

---

## 5. Development Roadmap: 2D + 3D Hybrid Experience

| Phase | Focus Area | Deliverables |
| :--- | :--- | :--- |
| **Phase 1** | **2D + 3D Design System** | Glassmorphic HUDs, dark space aesthetics, typography tokens, glowing neon accent states |
| **Phase 2** | **3D Viewport Foundation** | R3F Canvas, studio lighting, orbit controls, procedural fallback models, responsive resizing |
| **Phase 3** | **Interactive 2D Controls** | Layer selector (Skin/Muscle/Skeletal), rotation toggles, camera position presets, wireframe modes |
| **Phase 4** | **Human & Animal System** | Human anatomy model inspection + Animal comparative biology models with smooth transitions |
| **Phase 5** | **Scrollytelling & Data UI** | Coordinated scroll animations linking 2D story sections with 3D camera sweeps |
| **Phase 6** | **Performance & Mobile** | WebGL context loss handling, touch gesture optimization, dynamic LOD, 60fps responsiveness |

---

## 6. Ready for Implementation
The dependencies (`three`, `@react-three/fiber`, `@react-three/drei`, `lucide-react`) are installed and verified. We are ready to begin creating the 2D + 3D hybrid components!
