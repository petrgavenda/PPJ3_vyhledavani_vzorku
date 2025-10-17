> Written with [StackEdit](https://stackedit.io/).
# Postup demonstrace vyhledávacího algoritmu
Cíl: Uživatel zadá nebo vygeneruje text a vzorek, poté bude mít možnost pomocí tlačítek postupovat dopředu i dozadu. Program mu postupně ukáže a vysvětlí jak najde (nebo nenajde) vzorek v textu

# Fáze po spuštění

## Krok 0

**Výzva k vložení textu**

Uživatel bude vyzván k vložení vlastního textu, bude mu také nabídnuto tlačítko na jeho automatické vygenerování. Vyskakovací textové pole, tlačítka Generuj a OK.
Kontrola textu, nesmí být prázdný. 
Pokračuje na Krok 0.1.

## Krok 0.1

**Výzva k vložení vzorku**

Uživatel bude vyzván k vložení hledaného vzorku. Bude mu také nabídnuto tlačítko na jeho automatické vygenerování, v tomto případě se najde krátký (cca. 4 znaky) string, která se v textu objevuje. Vyskakovací textové pole, tlačítka Generuj a OK.
Kontrola vzorku, nesmí být prázdný.
Pokračuje na Krok 0.2.

## Krok 0.2

**Vysvětlení práce s programem**

Vyskakovací okno které sdělí zkráceně cíl programu, také vysvětlí ovládání.
Pokračuje na Krok 1.

# Fáze manuální ovládání

## Krok 1

**Kontrola zda je možné vzorek najít**

Zkontroluje zda délka zbívajícího textu je větší nebo rovná délce vzorku. Vrací true nebo false.
Pokud *true* program sdělí, že vzorek je možné najít a bude pokračovat na Krok 2. 
Pokud *false* program sdělí, že vzorek není možné najít a bude pokračovat na Krok 5.

## Krok 2

**Porovnání prvního znaku**

Program zjistí znak vzorku a porovná ho s znakem vloženého textu. Vrací *true* nebo *false*.
Pokud *true* program sdělí, že znak se shoduje a bude pokračovat na Krok 3. 
Pokud *false* program sdělí, že znak se neshoduje, posune se o jeden znak textu dále a opakuje Krok 1.

## Krok 3

**Kontrola zda byl vzorek nalezen**

Zkontroluje zda pozice znaku ze vzorku není rovná délce vzorku. Vrací *true* nebo *false*.
Pokud *true* program sdělí, že vzorek byl nalezen a bude pokračovat na Krok 5 (true). 
Pokud *false* program sdělí, že vzorek nebyl zatím nebyl nalezen a pokračuje na krok 4.

## Krok 4

**Hledání zbytku vzorku**

Zkontroluje následující znak vzorku s následujím znakem textu. Vrací *true* nebo *false*.
Pokud *true* program sdělí, že *X*té  (= pořadí aktuálně porovnávaného písmena) z *Y* (= délka vzorku) bylo nalezeno, následuje Krok 3.
Pokud *false* program sdělí, že další znak se neshoduje a vrací se na Krok 1.

## Krok 5

**Nalezeno/nenalezeno**

Má boolean *nalezeno*.
Pokud *nalazeno* = *true*, vzorek byl nalezen. Počet nalezených vzorků zvýší o jeden. Pokračovat na Krok 1.
Pokud *nalezeno* = *false*, pokračovat na krok 6 (počet nalezených vzorků).

## Krok 6

**Hledání ukončeno**

Má int *počet nalezencých vzorků*
Pokud *počet nalezencých vzorků*, je roven nule, vypíše: „Vzorek se v textu nevyskytuje. Pro pokračování zadejde jiný vzorek a/nebo text.“ Tlačítko Pokračovat vrátí na krok 0. Tlačítko Opakovat umožňěje znovu si prohlédnout  všechny kroky.
Pokud *počet nalezencých vzorků*, je vyšší jak nula, vypíše: „Vzorek se v textu vyskytuje Nkrát. Pro pokračování zadejde jiný vzorek a/nebo text.“ Tlačítko Pokračovat vrátí na krok 0. Tlačítko Opakovat umožňěje znovu si prohlédnout všechny kroky.
