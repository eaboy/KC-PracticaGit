
- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

`git reset --hard HEAD~1`

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Primero git reflog para averiguar el hash del commit (aunque también lo podemos sacar de el resultado de la instrucción 
del paso 10, al hacer el commit nos sale en el terminal el hash del commit recién creado) y luego usando 
`git reset --hard 3dad027`, no especifica el enunciado si hay que mantener los cambio o no en el working area, yo he
preferido que no me los mantenga ya que no tendría sentido rehacer el commit con los cambios del commit padre.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

No, porque la rama styled está por delante de la rama master y todos los commits de la rama master están en la rama styled,
la rama styled ya contiene a la rama master, no ha ocurrido nada.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Si, porque en ambas ramas el archivo git-nuestro.md está modificado en las mismas líneas.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

No, porque la rama master y la rama styled están en una lista, todos los commits de la rama master están en la rama styled
por lo que simplemente el puntero de la rama master se mueve al commit donde está la rama styled, es un merge fast-forward.

- ¿Qué comando o comandos utilizaste en el paso 25?

`git log --graph --decorate --pretty=oneline`

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Si, porque la rama title contiene todos los commits de la rama master.

- ¿Qué comando o comandos utilizaste en el paso 27?

`git reset HEAD~1`, porque hay que volver al commit de donde partíamos para dehacer el reset, también se podría haber
buscado el commit por git log y haber hecho un git reset al commit directamente, en ambos casos sin el modificador --hard
para no perder lo que tenemos en el working copy.

- ¿Qué comando o comandos utilizaste en el paso 28?

Primero un git status para ver los archivos modificados, aunque en este caso no hubiera sido necesario porque solo estamos
trabajando con un archivo y además al hacer el git reset del paso anterior ya nos dice que archivo está unstaged, y luego
hacemos `git checkout -- git-nuestro.md`

- ¿Qué comando o comandos utilizaste en el paso 29?

`git branch -D title`, porque la rama al eliminar la rama title el commit donde añadimos el título se queda inaccesible y
hay que usar el modificador -D en vez de -d.

- ¿Qué comando o comandos utilizaste en el paso 30?

`git reset --hard HEAD@{1}`, he llevado el HEAD y la rama master de vuelta al commit donde el merge se acaba de hacer, justo
lo contrario que al deshacerlo.

- ¿Qué comando o comandos usaste en el paso 32?

Primero un git log para localizar el primer commit y luego un git checkout con el hash del commit.

- ¿Qué comando o comandos usaste en el punto 33?

`git heckout master` aunque podría haber hecho también git reflog y haber encontrado el hash del commit. En mi caso el
estado final no es cuando pusimos título al poema sino un commit después cuando hicimos el merge no-fastforward que crea un
commit donde se unen las dos ramas, por supuesto contiene el archivo con el título.
