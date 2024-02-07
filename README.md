<h1 align="center">Generar un árbol de directorios.</h1>
<p align="center"><i>Este código permite a un usuario seleccionar archivos, generar un árbol de directorios y visualizarlo en formato de texto, mostrando la jerarquía de carpetas y archivos con este formato:</i></p>


```
Prueba
├── Carpeta01
│   ├── ArchivoCar01_A.txt
│   ├── ArchivoCar01_B.txt
│   └── ArchivoCar01_C.txt
├── Carpeta02
│   ├── ArchivoCar02_A.txt
│   ├── CarpetaB1
│   │   ├── ArchivoCarpetaB1_A.txt
│   │   └── ArchivoCarpetaB1_B.txt
│   └── CarpetaB2
│       └── ArchivoCarpetaB2_A.txt
└── Carpeta03
    └── CarpetaC1
        ├── Documento.txt
        └── CarpetaC1_Sub1
            ├── Documento.txt
            └── CarpetaC1_SubSub1
                └── Documento.txt
```
Función processFiles:
procesa la lista de archivos y los muestra en un formato de árbol de directorios.

Función fnGenerarArbol:
Toma una lista de archivos y crea un objeto que representa un árbol de directorios y devuelve el árbol generado.


Función fnConvertirAString:
La función fnConvertirAString toma un objeto que representa un árbol de directorios y lo convierte en una cadena de texto con sangría que representa la estructura del árbol.
Devuelve la cadena de salida con el árbol en formato de texto.

