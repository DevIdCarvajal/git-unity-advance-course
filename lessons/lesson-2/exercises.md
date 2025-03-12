# Ejercicios prácticos de Git avanzado con Unity

## Requisitos previos
- Unity instalado (versión 2020.3 o superior)
- Git y Git LFS instalados
- Cuenta en GitHub
- Editor de código (e.g., VSCode)
- Alguna herramienta de merge (e.g., Beyond Compare, KDiff3 o Meld)

## Ejercicios

### 1. Configuración de Smart Merge

1. Crea un nuevo proyecto de Unity
2. Inicializa Git y Git LFS
3. Configura Smart Merge según la documentación oficial
4. Verifica la configuración provocando un conflicto simple

### 2. Trabajo con Git LFS

1. Añade los siguientes archivos de ejemplo al proyecto:
   - Una textura de 50MB
   - Un modelo 3D en formato FBX
   - Un archivo de audio WAV
2. Configura Git LFS para estos tipos de archivos
3. Realiza commits y verifica que LFS los está gestionando correctamente
4. Simula un cambio en la textura y comprueba el comportamiento de LFS

### 3. Resolución de conflictos en Unity

1. Crea una escena simple con:
   - Un cubo en (0,0,0)
   - Una esfera en (2,0,0)
   - Una luz direccional
2. Crea dos ramas: `feature-A` y `feature-B`
3. En `feature-A`: Mueve el cubo a (1,1,1) y cambia su color
4. En `feature-B`: Mueve el cubo a (-1,2,1) y cambia su escala
5. Intenta hacer merge de ambas ramas y resuelve el conflicto

### 4. Flujo de trabajo con Pull Requests

1. Crea un repositorio en GitHub
2. Configura dos ramas protegidas: `main` y `develop`
3. Crea una nueva funcionalidad en una rama `feature`
4. Realiza un pull request a `develop`
5. Simula una revisión de código añadiendo comentarios
6. Aplica cambios solicitados y completa el merge

### 5. Gestión avanzada de historial

1. Crea una serie de commits con mensajes poco descriptivos
2. Utiliza rebase interactivo para:
   - Combinar commits relacionados
   - Reescribir mensajes de commit
   - Reordenar commits
3. Aplica cherry-pick para mover un cambio específico a otra rama

### 6. Recuperación de errores

1. Simula un error grave:
   - Realiza un cambio importante
   - Haz commit
   - "Accidentalmente" elimina la rama
2. Utiliza reflog para recuperar el trabajo
3. Practica diferentes tipos de reset:
   - soft
   - mixed
   - hard
4. Revierte un commit ya pusheado usando revert

## Entrega (opcional pero recomendable)

- Documenta los pasos seguidos en cada ejercicio
- Incluye capturas de pantalla de los momentos clave
- Anota los problemas encontrados y cómo los resolviste
