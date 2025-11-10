# Taller Linux

## 1. Listar directorio actual

```bash
pwd
```

**Salida esperada:**
```
/home/vagrant
```

---

## 2. Volver al directorio home desde cualquier ubicación

```bash
cd ~
pwd
```

**Salida esperada:**
```
/home/vagrant
```

---

## 3. Crear un nuevo directorio

```bash
mkdir -p temp/stuff/things/orange/apple/pear/grape
ls
tree
```

**Estructura creada:**
```
.
└── temp
    └── stuff
        └── things
            └── orange
                └── apple
                    └── pear
                        └── grape

7 directorios, 0 archivos
```

---

## 4. Cambiar de un directorio a otro usando cd

```bash
cd temp/stuff/things/orange/apple/pear/grape
pwd
cd ../../../../../../..
pwd
```

**Salida esperada:**
```
/home/vagrant/temp/stuff/things/orange/apple/pear/grape
/home/vagrant
```

---

## 5. Listar los contenidos de un directorio usando ls

```bash
cd temp
ls
cd stuff
ls
cd things
ls
cd orange
ls
cd apple
ls
cd pear
ls
```

**Navegación a través de directorios:**
```
vagrant@servidorUbuntu:~/temp$ ls
stuff
vagrant@servidorUbuntu:~/temp/stuff$ ls
things
vagrant@servidorUbuntu:~/temp/stuff/things$ ls
orange
vagrant@servidorUbuntu:~/temp/stuff/things/orange$ ls
apple
vagrant@servidorUbuntu:~/temp/stuff/things/orange/apple$ ls
pear
vagrant@servidorUbuntu:~/temp/stuff/things/orange/apple/pear$ ls
grape
```

---

## 6. Eliminar un directorio vacío

```bash
cd ~/temp/stuff/things/orange/apple/pear/grape
cd ..
rmdir grape
cd ..
rmdir pear
cd ..
rmdir apple
cd ..
rmdir orange
cd ..
rmdir things
cd ..
rmdir stuff
cd ..
rmdir temp
tree
```

**Resultado final:**
```
0 directorios, 0 archivos
```

---

## 7. Guardar su localización actual, ir a una nueva localización con pushd y retornar a la localización guardada con popd

```bash
cd ~/temp
mkdir -p i/like/icecream
pushd i/like/icecream
popd
pushd i/like
pushd icecream
popd
popd
```

**Ejemplo de uso:**
```
vagrant@servidorUbuntu:~/temp$ pushd i/like/icecream
~/temp/i/like/icecream ~/temp
vagrant@servidorUbuntu:~/temp/i/like/icecream$ popd
~/temp
vagrant@servidorUbuntu:~/temp$ pushd i/like
~/temp/i/like ~/temp
vagrant@servidorUbuntu:~/temp/i/like$ pushd icecream
~/temp/i/like/icecream ~/temp/i/like ~/temp
vagrant@servidorUbuntu:~/temp/i/like/icecream$ popd
~/temp/i/like ~/temp
vagrant@servidorUbuntu:~/temp/i/like$ popd
~/temp
```

---

## 8. Crear archivos vacíos con touch

```bash
cd ~/temp
touch iamcool.txt
ls
```

**Salida:**
```
i  iamcool.txt
```

---

## 9. Copiar un archivo desde una localización a otra con cp

```bash
cp iamcool.txt neat.txt
cp neat.txt awesome.txt
cp awesome.txt thefourthfile.txt
mkdir something
cp awesome.txt something/
cp -r something newplace
tree
```

**Estructura resultante:**
```
.
├── awesome.txt
├── i
│   └── like
│       └── icecream
├── iamcool.txt
├── neat.txt
├── newplace
│   └── awesome.txt
├── something
│   └── awesome.txt
└── thefourthfile.txt

5 directorios, 6 archivos
```

---

## 10. Mover un archivo de una localización a otra usando mv

```bash
mv awesome.txt uncool.txt
mv newplace oldplace
mv oldplace newplace
tree
```

**Estructura resultante:**
```
.
├── i
│   └── like
│       └── icecream
├── iamcool.txt
├── neat.txt
├── newplace
│   └── awesome.txt
├── something
│   └── awesome.txt
├── thefourthfile.txt
└── uncool.txt

5 directorios, 6 archivos
```

---

## 11. Crear un archivo con contenido de texto llamado test.txt y abrirlo con less o con more

```bash
echo "Este es un archivo de prueba para less y more" > test.txt
less test.txt
more test.txt
```

**Contenido del archivo:**
```
Este es un archivo de prueba para less y more
```

**Nota:** Presiona `q` para salir de `less` o `more`.

---

## 12. Abrir el archivo usando cat

```bash
echo -e "Soy un archivo divertido\nque hace reimar la vida" > test2.txt
cat test2.txt
```

**Salida:**
```
Soy un archivo divertido
que hace reimar la vida
```

---

## 13. Eliminar un archivo usando rm

```bash
rm uncool.txt
ls
rm iamcool.txt neat.txt thefourthfile.txt
rm something/awesome.txt
rmdir something
rm -rf newplace
ls
tree
```

**Resultado final:**
```
.
├── i
│   └── like
│       └── icecream
├── test2.txt
└── test.txt

3 directorios, 2 archivos
```

---

## 14. Salir del terminal

```bash
exit
```

**Resultado:**
```
logout
```

---

## Notas adicionales

- **`pwd`**: Muestra el directorio de trabajo actual (Print Working Directory)
- **`cd`**: Cambia de directorio (Change Directory)
- **`mkdir`**: Crea directorios (Make Directory)
- **`ls`**: Lista contenidos de un directorio (List)
- **`tree`**: Muestra estructura de directorios en forma de árbol
- **`rmdir`**: Elimina directorios vacíos (Remove Directory)
- **`pushd`**: Guarda el directorio actual y cambia a uno nuevo
- **`popd`**: Regresa al directorio guardado anteriormente
- **`touch`**: Crea archivos vacíos
- **`cp`**: Copia archivos o directorios (Copy)
- **`mv`**: Mueve o renombra archivos/directorios (Move)
- **`cat`**: Muestra el contenido de archivos (Concatenate)
- **`less/more`**: Visualizadores de texto página por página
- **`rm`**: Elimina archivos o directorios (Remove)
- **`exit`**: Sale del terminal
