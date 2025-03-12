# 2. Gestión avanzada de conflictos en Unity

## Índice

- [¿Por qué ocurren conflictos en Unity?](#por-qué-ocurren-conflictos-en-unity)
- [Unity Smart Merge](#unity-smart-merge)
- [Resolución manual con herramientas externas](#resolución-manual-con-herramientas-externas)
- [Buenas prácticas para evitar conflictos](#buenas-prácticas-para-evitar-conflictos)

## ¿Por qué ocurren conflictos en Unity?

Los conflictos en Unity suelen ocurrir debido a la estructura YAML o binaria de sus archivos, que son difíciles de fusionar automáticamente por Git, particularmente cuando dos o más desarrolladores modifican simultáneamente escenas (`.unity`), prefabs (`.prefab`) o assets (`.asset`).

## Unity Smart Merge

Unity ofrece una herramienta integrada llamada **Smart Merge**, que facilita el proceso de combinación automática de archivos YAML.

### Configuración de Smart Merge

#### Git

1. Localizar el archivo `UnityYAMLMerge.exe` en la carpeta de instalación de Unity:
   - Windows: `C:\Program Files\Unity\Hub\Editor\[version]\Editor\Data\Tools\UnityYAMLMerge.exe`
   - macOS: `/Applications/Unity/Hub/Editor/[version]/Unity.app/Contents/Tools/UnityYAMLMerge`
   - Linux: `/opt/Unity/Hub/Editor/[version]/Editor/Data/Tools/UnityYAMLMerge`

2. Configurar la herramienta de merge en el archivo `.gitconfig`:

    ```
    [merge]
        tool = unityyamlmerge

    [mergetool "unityyamlmerge"]
        trustExitCode = false
        cmd = '[path-to-UnityYAMLMerge]' merge -p "$BASE" "$REMOTE" "$LOCAL" "$MERGED"
    ```

Se debe revisar la ruta completa al ejecutable `UnityYAMLMerge` dependiendo del sistema operativo así como reemplazar la `[version]` con la que corresponda.

Para usar el merge tool cuando hay conflictos, ejecutar:
```bash
git mergetool
```

#### SourceTree

1. Ir a `Tools > Options > Diff`.
2. Seleccionar `Custom` en el desplegable `Merge Tool`.
3. Introducir la ruta completa al ejecutable `UnityYAMLMerge` en el campo `Merge Command`.
4. Introducir `merge -p $BASE $REMOTE $LOCAL $MERGED` en el campo `Arguments`.

## Resolución manual con herramientas externas

En casos donde Smart Merge no sea suficiente, se recomienda usar herramientas externas especializadas como **Beyond Compare**, **KDiff3** o **Meld**.

### Configuración con SourceTree

1. Ir a `Tools > Options > Diff`.
2. Seleccionar la herramienta deseada (Beyond Compare, KDiff3, Meld, etc.).
3. Aplicar y guardar la configuración.

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
