
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

- [Función prProcessFiles](#prProcessFiles)
- [Función fnGenerateTree](#fnGenerateTree)
- [Función fnConvertToString](#fnConvertToString)
- [Contributing](#contributing)


## prProcessFiles

procesa la lista de archivos y los muestra en un formato de árbol de directorios.

```
  function prProcessFiles(searchTerm = "") {
            resultBox.value = "";
            var noListFiles = "";
            var contar = 0;
            let currentFolder = "";

            for (i = 0; i < inp.files.length; i++) {
                let file = inp.files[i];
                let filePath = file.webkitRelativePath;
                let folder = filePath.split("/")[0];

                if (folder !== currentFolder) {
                    currentFolder = folder;
                    //resultBox.value += "\n" + folder + "\n";
                }
                //Solo si usa filtro
                if (searchTerm && !filePath.toLowerCase().includes(searchTerm)) {
                    continue;
                }
                resultBox.value += filePath + "\n";
                noListFiles = filePath + "?" + noListFiles;
            }
            noListFiles += "listar";
            console.log(noListFiles);
            ListFiles = noListFiles.split("?");// Convertir la cadena a un array
            ListFiles.pop();// Eliminar el último elemento vacío
        }
```

## fnGenerateTree

Toma una lista de archivos y crea un objeto que representa un árbol de directorios y devuelve el árbol generado.

```
 function fnGenerateTree(lista) {
            const arbol = {};
            lista.forEach((archivo) => {
                const ruta = archivo.split("/");
                let nodoActual = arbol;
                for (let i = 0; i < ruta.length; i++) {
                    if (!nodoActual.hasOwnProperty(ruta[i])) {
                        nodoActual[ruta[i]] = i === ruta.length - 1 ? { archivo: ruta[i] } : {};
                    }
                    nodoActual = nodoActual[ruta[i]];
                }
            });
            return arbol;
        }
```

## fnConvertToString

La función fnConvertirAString toma un objeto que representa un árbol de directorios y lo convierte en una cadena de texto con sangría que representa la estructura del árbol.
Devuelve la cadena de salida con el árbol en formato de texto.

```
function fnConvertToString(arbol, nivel = 0) {
            let salida = "";
            for (const key in arbol) {
                if (arbol[key].hasOwnProperty("archivo")) {
                    salida += `${" ".repeat(nivel * 2)}├── ${arbol[key].archivo}\n`;
                } else {
                    salida += `${" ".repeat(nivel * 2)}├── ${key}\n`;
                    salida += fnConvertToString(arbol[key], nivel + 1);
                }
            }
            return salida;
        }

```

## contributing
