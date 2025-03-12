# 3. Git LFS para gestión eficiente de archivos binarios

Este documento explica el uso avanzado de **Git Large File Storage (LFS)**, una extensión de Git diseñada para manejar eficazmente archivos grandes o binarios en proyectos como los desarrollados en Unity.

## Índice

- [¿Qué es Git LFS y por qué usarlo en Unity?](#qué-es-git-lfs-y-por-qué-usarlo-en-unity)
- [Instalación y configuración de Git LFS](#instalación-y-configuración-de-git-lfs)
- [Uso diario de Git LFS](#uso-diario-de-git-lfs)
- [Beneficios de usar Git LFS](#beneficios-de-usar-git-lfs)

## ¿Qué es Git LFS y por qué usarlo en Unity?

Git no gestiona de forma eficiente archivos binarios grandes como modelos 3D, texturas, audios y vídeos, comunes en proyectos de Unity. Git LFS resuelve este problema almacenando estos archivos fuera del repositorio principal, facilitando su manejo y mejorando la velocidad del repositorio.

## Instalación y configuración de Git LFS

Para usar Git LFS, primero se debe instalar y configurar:

### Instalación

Descargar desde [git-lfs.com](https://git-lfs.com/) e instalar siguiendo las instrucciones según el sistema operativo.

### Configuración inicial

Desde el terminal, ejecutar:

```bash
git lfs install
```

### Configuración de archivos a gestionar

Especificar qué archivos gestionará Git LFS usando patrones en `.gitattributes`:

```bash
git lfs track "*.psd"
git lfs track "*.fbx"
git lfs track "*.png"
git lfs track "*.wav"
```

Confirmar la configuración:

```bash
git add .gitattributes
git commit -m "Configurar Git LFS para archivos binarios"
```

## Uso diario de Git LFS

El flujo de trabajo es similar al de Git estándar:

```bash
git add Assets/modelo.fbx
git commit -m "Añadir nuevo modelo 3D"
git push origin main
```

Git LFS se encarga automáticamente de gestionar eficientemente estos archivos.

## Uso de Git LFS con SourceTree

SourceTree soporta Git LFS automáticamente. Para utilizarlo desde SourceTree:

1. Asegurarse de tener Git LFS instalado previamente.
2. Añadir archivos gestionados por Git LFS al repositorio desde SourceTree.
3. SourceTree detectará automáticamente los archivos configurados en `.gitattributes` y los gestionará correctamente usando LFS al realizar commits y push.

Esto facilita enormemente el manejo gráfico de archivos grandes sin tener que utilizar comandos desde la terminal.

## Beneficios de usar Git LFS

- Menor tamaño del repositorio local y remoto.
- Descargas y subidas más rápidas.
- Menor probabilidad de conflictos y corrupción en archivos binarios.
- Mayor claridad en el historial de cambios.

Integrar Git LFS mejora notablemente la experiencia al trabajar con archivos pesados y binarios en Unity, facilitando una colaboración efectiva y optimizando el rendimiento del repositorio.
