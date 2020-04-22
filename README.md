# Git intro

Git je verzovaci nastroj - ukladame i ruzne verze projektu, muzeme pracovat ve vice vetvich a lepe tak kolaborovat v tymu aniz, by moje prace ovlinila prace nekoho jineho, pracujiciho klidne na stejnych souborech jako ja. Zmeny pak "zmergujeme" do jedne hlavni vetve - vesinou se nazyva Master nebo Develop.

Kdyz prijdu k projektu na kterem nepracuji sama tak vzdy udelam `git pull` v terminalu ve spravnem souboru/projektu. Takzvane si pullnu, stahnu zmeny.

Pak muzu zacit pracovat na svem projektu. Pak se rozhodnu ze uz jsem v nejake fazi kdy mi projekt funguje a treba chci zkusit neco experimentalniho, v tu chvili si ulozit danou verzi projektu. Udelam proto 4 nasledujici kroky, bud primo ve VS CODE, nebo terminalu:

1. v terminalu zavolam

```
git status
```

```
zuz@zuz-mac:~/Projects/tmp (master)$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	aa
	bb
	cc

nothing added to commit but untracked files present (use "git add" to track)
```

Zjistim tedy status naseho projektu, jake soubory jsem upravila a pak podle toho napisu smysluplny commit.

2. pridam soubory, nemusim vsechny. Tecka znamena vse, nebo ve VS CODU promoci +

```
   git add .
   <!-- nebo -->
   git add aa bb
```

, pridavam tedy pouze soubory aa a bb kdyz znovu provedu git status melo by se pak zobrazit toto:

```
zuz@zuz-mac:~/Projects/tmp (master)$ st
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   aa
	new file:   bb

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	cc
```

3. pokud jsem spokojena s tim co jsem pridala, chci to i nejak okomnetovat, aby kdyz se k tomu vracim davalo smysl proc jsem treba vybrala jen tyto dva.
   Provedu tedy prikaz:

```
git commit
```

a otevre se mi Vim. Zmacknu i, jako instert - vlozit. Ted uz muzu psat, dam ENTER a na prvni radku napisu commit `add new file aa and bb`. Pokud jsem spokojena kliknu na ESC klavesnici a tim se dostanuna posledni radek a napisi `:wq` - write quit a ENTER. Tim se vratim do normalniho terminalu. A posledni krok.

Ted pokud mi to trvalo dlouho muzu znovy pullnout zmeny, abych si stahla nejnovejsi verzi, pokud nekdo pushnul behem toho kdyz jsem tam neco upravovala. 

4. Nahraju svoje zmeny do repozitare. 
```
git push
```