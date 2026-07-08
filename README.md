# SISMO - Sistema de Respuesta a Emergencias por Sismo

## Descripción
Sistema operativo comunal para la respuesta integral ante eventos sísmicos de alto impacto. Estructura tres líneas de acción coordinadas: estratégica, operacional y de recuperación.

## Diagrama del Sistema

```mermaid
flowchart TB
    %% Nodo de inicio - Percepción del sismo
    n4["PERCEPCIÓN DE SISMO<br>DE MAYOR INTENSIDAD"]:::percepcion
    
    %% Árbol de decisión binario (activación)
    d1{"¿Intensidad ≥ VII<br>Mercalli?"}:::decision
    d2{"¿Afectaciones requieren<br>respuesta institucional<br>extraordinaria?"}:::decision
    cierre["Equipo Comunal<br>monitorea, informa<br>y cierra el evento"]:::cierre
    
    %% Conexiones del árbol
    n4 --> d1
    d1 -->|SÍ| e1
    d1 -->|NO| d2
    d2 -->|SÍ| e1
    d2 -->|NO| cierre

    %% LÍNEA ESTRATÉGICA – PRIMER MOMENTO
    subgraph ESTRATEGICA["LÍNEA ESTRATÉGICA – PRIMER MOMENTO"]
        direction TB
        e1["1. Activación del Sistema<br>Operativo Comunal"]:::estrategica
        e2["2. Evaluación inicial de<br>daños y necesidades"]:::estrategica
        e3["3. Toma de decisiones<br>estratégicas"]:::estrategica
        e4["4. Elaboración del Informe<br>Preliminar ALFA<br><i>(posterior a decisiones)</i>"]:::estrategica
    end
  
    %% LÍNEA OPERACIONAL – SEGUNDO MOMENTO
    subgraph OPERACIONAL["LÍNEA OPERACIONAL – SEGUNDO MOMENTO"]
        direction TB
        o1["1. Despliegue territorial de<br>funcionarios municipales"]:::operacional
        o2["2. Acciones y reportes de<br>direcciones operativas"]:::operacional
        o3["3. Coordinación y respuesta<br>en terreno"]:::operacional
    end
  
    %% LÍNEA DE RECUPERACIÓN – TERCER MOMENTO
    subgraph RECUPERACION["LÍNEA DE RECUPERACIÓN Y REHABILITACIÓN – TERCER MOMENTO"]
        direction TB
        r1["1. Evaluación de impactos y<br>levantamiento de necesidades<br>de recuperación"]:::recuperacion
        r2["2. Implementación de medidas<br>de rehabilitación y<br>reconstrucción"]:::recuperacion
        r3["3. Restablecimiento de la<br>normalidad comunal"]:::recuperacion
    end

    %% Conexiones internas de cada momento
    e1 --> e2
    e2 --> e3
    e3 --> e4
    o1 --> o2
    o2 --> o3
    r1 --> r2
    r2 --> r3

    %% Conexiones entre momentos
    e4 -.->|Pasa a| o1
    o3 -.->|Pasa a| r1

    %% Bloques de información lateral
    mando["<b>MANDO ESTRATÉGICO</b><br>• Alcalde<br>• Administradora Municipal<br>• Directores de Social, Salud,<br>DIDECO, DOM, Medio Ambiente<br>• Jefa de Emergencia<br><i>(enlace entre momentos)</i>"]:::info
    
    prioridad["<b>PRIORIDADES PERMANENTES</b><br>• Estado de las personas<br>• Estado de las viviendas<br>• Servicios básicos y<br>servicios esenciales<br><i>Aplican a los tres niveles</i>"]:::info
    
    comunicaciones["<b>COMUNICACIONES MUNICIPALES</b><br><i>Apoyo transversal de<br>información y coordinación</i>"]:::info

    equipo["<b>EQUIPO ESTRATÉGICO<br>DE RESPUESTA</b><br><br>• Alcalde<br>• Administradora Municipal<br>• Director de Obras<br>• Director SECPLAN<br>• Director Desarrollo Social<br>• Director Desarrollo Comunitario<br>• Directora de Salud<br>• Director Medio Ambiente<br>• Jefe(a) Depto. Emergencia"]:::info

    %% Posicionamiento de los bloques laterales
    mando -.-> ESTRATEGICA
    prioridad -.-> ESTRATEGICA
    prioridad -.-> OPERACIONAL
    prioridad -.-> RECUPERACION
    comunicaciones -.-> ESTRATEGICA
    equipo -.-> e1

    %% Definición de estilos
    classDef decision fill:#f0f0f0,stroke:#333,stroke-width:1.5px
    classDef cierre fill:#f3f4f6,stroke:#6b7280,stroke-width:1px
    classDef percepcion fill:#fefce8,stroke:#ca8a04,stroke-width:2px
    classDef estrategica fill:#e0e7ff,stroke:#4f46e5,stroke-width:1.5px
    classDef operacional fill:#ecfdf5,stroke:#059669,stroke-width:1.5px
    classDef recuperacion fill:#fff7ed,stroke:#fb923c,stroke-width:1.5px
    classDef info fill:#fafafa,stroke:#666,stroke-dasharray: 5 5,stroke-width:1px
```

## Estructura del Sistema

### Criterios de Activación
- **Intensidad ≥ VII en Escala Mercalli**, O
- **Afectaciones que requieren respuesta institucional extraordinaria**

### Tres Líneas de Acción

#### 1️⃣ Línea Estratégica (Primer Momento)
- Activación del Sistema Operativo Comunal
- Evaluación inicial de daños y necesidades
- Toma de decisiones estratégicas
- Elaboración del Informe Preliminar ALFA

#### 2️⃣ Línea Operacional (Segundo Momento)
- Despliegue territorial de funcionarios municipales
- Acciones y reportes de direcciones operativas
- Coordinación y respuesta en terreno

#### 3️⃣ Línea de Recuperación (Tercer Momento)
- Evaluación de impactos y levantamiento de necesidades
- Implementación de medidas de rehabilitación y reconstrucción
- Restablecimiento de la normalidad comunal

### Prioridades Permanentes
1. **Estado de las personas**
2. **Estado de las viviendas**
3. **Servicios básicos y servicios esenciales**

*Aplican a los tres niveles del sistema*

### Mando y Coordinación
- **Mando Estratégico**: Alcalde, Administradora Municipal, Directores
- **Enlace entre Momentos**: Jefa de Emergencia
- **Apoyo Transversal**: Comunicaciones Municipales

