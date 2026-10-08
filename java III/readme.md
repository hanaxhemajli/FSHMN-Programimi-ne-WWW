
# Java III - Klinika e CSS: shpëto afishen

## Përshkrimi i Projektit
Ky projekt është zhvilluar në kuadër të lëndës Programimi në WWW. Qëllimi i detyrës ishte transformimi i një afisheje të pakuptueshme të klubit të debatit në një ftesë të qartë, të strukturuar dhe të qasshme duke përdorur HTML dhe CSS të jashtëm[cite: 2].

## Karakteristikat e Zbatuara
* **Stilimi i jashtëm:** Përdorimi i një skedari të jashtëm CSS për të ndarë përmbajtjen nga prezantimi[cite: 2].
* **Etiketat (Badges):** Krijimi i etiketave për "Falas", "Vende të kufizuara: 20" dhe "Edhe online", duke përdorur dallime vizuale përtej ngjyrës (p.sh. kufij dhe ikona) për qëllime aksesueshmërie[cite: 1, 2].
* **Modeli i kutisë (Box Model):** Përdorimi i `box-sizing: border-box;` për të parandaluar tejkalimin e gjerësisë në ekrane të vogla (nën 360 px)[cite: 2, 3].
* **Aksesueshmëria dhe Fokusi:** Përdorimi i `:focus-visible` për të siguruar lundrim të qartë me tastierë (`Tab`)[cite: 2].

## Reflektim Individual (Kaskada)
* **Cili rregull fitoi në kaskadë dhe pse?** 
  Rregulli që përdor ID selector (`#poster`) fitoi mbi rregullin e klasës (`.poster`) sepse ID selektorët kanë një peshë (specifikë) më të lartë në algoritmin e kaskadës së CSS-së[cite: 2, 5].
