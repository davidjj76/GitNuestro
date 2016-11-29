# GitNuestro

- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

```git
git reset --hard HEAD~1
```
Con *reset HEAD~1*, **HEAD** y **styled** se mueven al commit inmediatamente anterior. Se pone el modificador *--hard* para que working copy se quede en la situación del commit anterior, por lo que se pierden los cambios.

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

```git
git reflog
git reset --hard 0b30370
```
Con *reflog* se busca el identificador del commit que se acaba de deshacer (0b30370).
Con *reset 0b30370*, **HEAD** y **styled** se mueven a ese commit. Se pone el modificador *--hard* para que working copy se quede en la situación de ese commit, recuperándose el trabajo realizado.

También se podría haber hecho con *reset --hard HEAD@{1}*.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

La rama **styled** ya contiene el trabajo de **master** por lo que no hay merge que hacer (already up-to-date), y por tanto no puede haber conflicto.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

La rama **styled** y la rama **htmlify** han modificado de manera distinta el archivo en las mismas líneas, por lo que al absorber **styled** a **htmlify** se produce el conflicto.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

Para que **master** incluya el trabajo de **styled** basta con adelantar la posición de **master** al commit donde está **styled**, ya que está directamente por delante de **master**, por lo que no se puede producir conflicto (se puede hacer un *merge fast-forward*).

- ¿Qué comando o comandos utilizaste en el paso 25?

```git
git log --graph --decorate --pretty=oneline
```

Se puede configurar el comando en un alias *graph* de la siguiente manera:

```git
git config alias.graph "log --graph --decorate --pretty=oneline"
```

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

El commit donde se encuentra **title** se encuentra directamente por delante del commit donde está **master** por lo que el *merge* podría haber sido *fast-forward*. 

- ¿Qué comando o comandos utilizaste en el paso 27?

```git
git reset HEAD~1
```

- ¿Qué comando o comandos utilizaste en el paso 28?

```git
git checkout -- git-nuestro.md
```

- ¿Qué comando o comandos utilizaste en el paso 29?

```git
git branch -D title
```

Se ha de forzar el borrado con la opción -D ya que la rama **title** contiene trabajo que no ha sido incluido todavía en ninguna otra rama.

- ¿Qué comando o comandos utilizaste en el paso 30?

```git
git reflog
git reset --hard 8e8eaff
```

- ¿Qué comando o comandos usaste en el paso 32?

```git
git reflog
git reset --hard 4dbb01d
```

- ¿Qué comando o comandos usaste en el punto 33?

```git
git reflog
git reset --hard 8e8eaff
```

También se puede hacer *git reset --hard HEAD@{1}*, ya que basta con volver al commit en el que estábamos en el paso anterior.
