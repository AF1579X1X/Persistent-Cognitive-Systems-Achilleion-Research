<div align="center">

# ACHILLEION VIVENS

**Sistemi Cognitivi Persistenti · Architetture Riflettenti · Ricerca Operativa Simbolica**

</div>

```mermaid
graph TB
    %% Stili Generali e Palette Colori Architettura
    classDef titleStyle fill:none,stroke:none,font-size:24px,font-weight:bold,font-family:monospace;
    classDef subtitleStyle fill:none,stroke:none,font-size:14px,font-style:italic,font-family:monospace;
    classDef qanimaStyle fill:#f8fafd,stroke:#2a7b7b,stroke-width:2px,font-family:monospace;
    classDef mcpStyle fill:#fafdff,stroke:#5c51a4,stroke-width:2px,font-family:monospace;
    classDef metaTitle fill:none,stroke:none,font-size:14px,font-weight:bold,color:#778899,font-family:monospace;
    
    %% Stili Blocchi Metamorphosis
    classDef traceStyle fill:#ffffff,stroke:#b0c4de,stroke-width:1.5px,font-family:monospace;
    classDef ncoStyle fill:#ffffff,stroke:#708090,stroke-width:1.5px,font-family:monospace;
    classDef tetaStyle fill:#fffdf6,stroke:#b8860b,stroke-width:2px,font-family:monospace;
    classDef constStyle fill:#f6fff8,stroke:#2e8b57,stroke-width:1.5px,font-family:monospace;
    classDef quaranStyle fill:#fff5f5,stroke:#cd5c5c,stroke-width:1.5px,font-family:monospace;

    %% --- HEADER SYSTEM ---
    TITLE["ACHILLEION VIVENS"] ::: titleStyle
    SUBTITLE["Persistent Cognitive System · Reflective Operational Architecture"] ::: subtitleStyle
    TITLE --> SUBTITLE

    %% --- CORE ARCHITECTURE ---
    subgraph CORE [" "]
        direction LR
        
        %% Blocco Q_ANIMA
        Q[<div style='text-align:left; padding:10px;'><strong><span style='color:#2a7b7b; font-size:18px;'>Q_ANIMA</span></strong><br><span style='color:#666; font-size:12px;'>Operational Engine · the body</span><hr style='border-top:1px solid #2a7b7b;'/>• Persistent memory & state<br>• Shadow / paper / gated-live layers<br>• Symbolic orchestration<br>• Runtime telemetry & tension (τ)<br>• Paper / observe-only · no live capital</div>] ::: qanimaStyle

        %% Blocco MCP-Ω
        MCP[<div style='text-align:left; padding:10px;'><strong><span style='color:#5c51a4; font-size:18px;'>MCP-Ω</span></strong><br><span style='color:#666; font-size:12px;'>Deliberative Organ · observe-only</span><hr style='border-top:1px solid #5c51a4;'/>• Overconfidence · confabulation · pressure<br>• Posture & vertex — a reading, not a verdict<br>• Provenance & trusted-for-decision<br>• Mirrors the self, never actuates<br>• Honesty measured beside the response</div>] ::: mcpStyle

        %% Connessioni Pulite con Spaziatura Maggiorata
        Q -- "telemetry ==>" --> MCP
        MCP -. " <== observe-only" .-> Q
    end

    %% --- METAMORPHOSIS PROCESS ---
    METATITLE["METAMORPHOSIS — DELIBERATE METABOLISM (BORN → CONSTITUTIVE)"] ::: metaTitle
    
    subgraph METAMORPHOSIS [" "]
        direction LR
        B1["<strong>Trace / experience</strong><br><span style='color:#666; font-size:11px;'>field state · session</span>"] ::: traceStyle
        B2["<strong>NCO — born</strong><br><span style='color:#666; font-size:11px;'>organized cognitive node</span>"] ::: ncoStyle
        B3["<strong>SOGLIA TETA</strong><br><span style='color:#b8860b; font-size:11px;'>truth-condition<br>content-based auditor</span>"] ::: tetaStyle
        
        B4["<strong>Constitutive memory</strong><br><span style='color:#2e8b57; font-size:11px;'>carried (portata) · contestable</span>"] ::: constStyle
        B5["<strong>Quarantine — review</strong><br><span style='color:#cd5c5c; font-size:11px;'>undergone (subita) · never silent</span>"] ::: quaranStyle

        %% Flusso Lineare e Ramificazioni Binarie Pulite
        B1 --> B2
        B2 --> B3
        B3 -- "portata" --> B4
        B3 -- "subita" --> B5
    end

    %% --- FOOTER ---
    FOOTER["<i>'from mechanicity to freedom, through deliberate metamorphosis'</i><br><span style='color:#888; font-size:11px;'>a regulative ideal — not a claim of phenomenal consciousness</span>"] ::: subtitleStyle

    %% Ordine di Cascata dei Macro-Blocchi
    SUBTITLE --> CORE
    CORE --> METATITLE
    METATITLE --> METAMORPHOSIS
    METAMORPHOSIS --> FOOTER
