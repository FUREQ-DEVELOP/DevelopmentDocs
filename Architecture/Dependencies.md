# 依存関係

```mermaid
graph TD
 RL[RenderingLibrary] --> RW[RenderingWorkspace]
 DT[DevelopmentTools] --> RW
 RL --> GE[GameEngine]
 GE --> EW[EngineWorkspace]
 EE[EngineEditor] --> EW
 EH[EngineHub] --> EW
 DT --> EW
 GE --> G[Game-001]
 GC[Game-001-Code] --> G
 GA[Game-001-Art] --> G
 GD[Game-001-Design] --> G
 DT --> G
```

12 direct submodules plus nested `GameEngine/External/RenderingLibrary` registration. All URLs use HTTPS and all child repositories are public, so no public parent depends on private content. Nested sources remain pinned by gitlink SHA; recursive clone is required. `EngineHub` is included in EngineWorkspace for unified source development; standalone product dependency remains optional.
