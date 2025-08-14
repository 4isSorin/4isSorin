# Házi Feladat
## 1. Feladat
### A `*` és `?` joker karakterek használata miben különbözik  a Windows cmd-ben és a bash-ben?

Az említett karakterek fájlnevek megadására használatosak ún. "pattern matching"-hez.
Windows cmd-ben és bash-ben is ezek a joker karakterek:

 - `*`: Nulla vagy több karaktert helyettesít
 - `?`: Pontosan egy karaktert helyettesít
 
Viszont bash-ben ennél több segítség van a kereséshez:

 - `[]`: Karakter halmazok (bracket expressions): Egy karakter halmazt vagy felsorolást helyettesít be egy karakter helyére és visszaadja a megfelelő fájlokat pl.:
 ```sh
 ls valami[123].txt
 ls valami[a-c].txt
 ls valami[!123]
 ```
1. esetben visszadja a `valami1.txt``valami2.txt``valami3.txt`fájlokat
2. esetben a `valamia.txt``valamib.txt``valamic.txt`fájlokat
3. estben minden `valamiX.txt` fájlt ahol X nem egyenlő 1,2 vagy 3-al.

- `{}`: Alternatívák (brace expansion): Egy vagy több karaktert, felsorolást vagy karakterláncot helyettesít be a megjelelöt helyre és az ennek megfelelő fájlokat adja vissza
```sh
ls file{1,2,3}.txt
ls {A..C}.txt
ls {jan,feb,mar}_report.txt
```

1. esetben: `file1.txt`,`file2.txt`,`file3.txt`
2. esetben `fileA.txt`,`fileB.txt`,`fileC.txt` 
3. esetben `jan_report.txt`,`feb_report.txt`,`mar_report.txt`

- `.` Rejtett fájlok: A rejtett fájlok alapból nem kerülnek kilistázásra, de ez is megoldható:
```sh
ls .*    # Kilistázza a rejtett fájlokat
ls * .*  # Minden fájlt kilistáz, beleértve a rejtetteket 
shopt -s dotglob   # A * automatikusan ki fogja listázni a rejtett fájlokat
```
- Rekurzív keresés `**`
```sh
-shopt -s globstar #Bekapcsolja a globstar-t
ls **/*.txt
```
Ez eredmény képpen minden `.txt` fájlt listáz mappán belül is, bármilyen mélységben.

[további érdekességek a témáról itt érhetőek el](https://www.linuxjournal.com/content/pattern-matching-bash)



