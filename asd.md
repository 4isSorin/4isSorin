# Házi Feladat
## 1. Feladat
### A `*` és `?` joker karakterek használata miben különbözik  a Windows cmd-ben és a bash-ben?

Az említett karakterek fájlnevek megadására használatosak ún. "pattern matching"-hez.
Windows cmd-ben és bash-ben is ezek a joker karakterek:

 - `*`: Nulla vagy több karaktert helyettesít
 - `?`: Pontosan egy karaktert helyettesít
 
Viszont bash-ben több lehetőség van pattern matchinre:

 - `[]`: Karakter halmazok (bracket expressions): Egy karakter halmazt helyettesít pl.:
 ```sh
 ls valami[123].txt
 ls valami[a-c].txt
 ls valami[!123]
 ```
1. esetben visszadja a `valami1.txt``valami2.txt``valami3.txt`fájlokat
2. esetben a `valamia.txt``valamib.txt``valamic.txt`fájlokat
3. estben minden `valamiX.txt` fájlt ahol X nem egyenlő 1,2 vagy 3-al.
- `[]`
