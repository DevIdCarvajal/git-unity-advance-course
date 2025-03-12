# 2. Gestión avanzada de conflictos en Unity

Este documento explica técnicas específicas para manejar y resolver conflictos comunes en proyectos Unity al usar Git, especialmente aquellos relacionados con archivos sensibles como escenas (`.unity`), prefabs (`.prefab`) y assets (`.asset`).

## Índice

- [¿Por qué ocurren conflictos en Unity?](#por-qué-ocurren-conflictos-en-unity)
- [Unity Smart Merge](#unity-smart-merge)
- [Resolución manual con herramientas externas](#resolución-manual-con-herramientas-externas)
- [Buenas prácticas para evitar conflictos](#buenas-prácticas-para-evitar-conflictos)

## ¿Por qué ocurren conflictos en Unity?

Los conflictos en Unity suelen ocurrir debido a la estructura YAML o binaria de sus archivos, que son difíciles de fusionar automáticamente por Git, particularmente cuando dos o más desarrolladores modifican simultáneamente escenas o prefabs.

## Unity Smart Merge

Unity ofrece una herramienta integrada llamada **Smart Merge**, que facilita el proceso de combinación automática de archivos YAML.

### Configuración de Smart Merge

1. Ir a `Edit > Preferences` en Unity.
2. Seleccionar `External Tools`.
3. Configurar Smart Merge en la sección `Version Control`:

```
UnityYAMLMerge merge -p "%b" "%o" "%t" "%r"
```

Esta configuración permite que Unity resuelva muchos conflictos de manera automática.

## Resolución manual con herramientas externas

En casos donde Smart Merge no sea suficiente, se recomienda usar herramientas externas especializadas como **Beyond Compare** o **KDiff3**.

### Configuración con SourceTree

Para configurar una herramienta externa en SourceTree:

- Ir a `Herramientas > Opciones > Diff`.
- Seleccionar la herramienta deseada (Beyond Compare, KDiff3).
- Aplicar y guardar la configuración.

### Uso práctico

Al ocurrir un conflicto:

1. SourceTree indicará el conflicto en la interfaz.
2. Abrir la herramienta externa configurada directamente desde SourceTree.
3. Resolver manualmente el conflicto revisando visualmente los cambios.
4. Guardar y confirmar el merge en SourceTree.

## Buenas prácticas para evitar conflictos

- Mantener comunicación clara dentro del equipo sobre qué escenas o prefabs se están editando.
- Usar ramas específicas para grandes cambios en escenas y prefabs.
- Dividir escenas grandes en escenas más pequeñas para reducir la probabilidad de conflictos simultáneos.

Siguiendo estas técnicas avanzadas, los desarrolladores podrán gestionar eficazmente los conflictos en Unity, reduciendo el estrés y aumentando la productividad del equipo.
