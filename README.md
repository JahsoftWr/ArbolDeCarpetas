
<a href="https://jahsoftwr.github.io/ArbolDeCarpetas/Index.html">PROBAR</a>:bookmark_tabs:

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

## CODE

- [Función prProcessFiles](#fnconverttostring)
- [Función fnGenerateTree](#fngeneratetree)
- [Función fnConvertToString](#fnconverttostring)
- [Contributing](#contributing)


## fnconverttostring

<h1>Función prProcessFiles:</h1>

procesa la lista de archivos y los muestra en un formato de árbol de directorios.

## fngeneratetree</h1>

<h1>Función fnGenerateTree:</h1>

Toma una lista de archivos y crea un objeto que representa un árbol de directorios y devuelve el árbol generado.

## fnconverttostring</h1>

<h1>Función fnConvertToString:</h1>

La función fnConvertirAString toma un objeto que representa un árbol de directorios y lo convierte en una cadena de texto con sangría que representa la estructura del árbol.
Devuelve la cadena de salida con el árbol en formato de texto.

