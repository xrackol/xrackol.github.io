---
layout: page
title: Webove publikovanie
permalink: /wp/
---
<b>Zadanie 1:</b> Osobná webová prezentácia na GitHub pages<br/>
<b>Dátum:</b> 13.3.2016<br/>
<b>Popis:</b> Vytvorte webovú prezentáciu (webové sídlo) o sebe. Zamerajte sa jednak na vaše profesné záujmy (napr. projekty, ktoré riešite/riešili ste, čo vás v informatike najviac baví, fascinuje = váš developerský profil) a jednak vaše osobné záujmy, hobby..<br/>
<b>Odkaz na stiahnutie:</b> <a href="../data/Z1-xrackol.zip" target="_blank">{{ "LINK na subor Z1-xrackol.zip" | slugify: 'pretty' }}</a><br/>       
<hr class="post">
<b>Zadanie 2:</b> Transformácia vybraného dokumentu do formátu DocBook<br/>
<b>Dátum:</b> 9.4.2016<br/>
<b>Popis:</b> Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.<br/>
<b>Správa o zadaní:</b> Zadanie bolo vypracované v DocBooku na základe poskytnutého vzorového riešenia od Jiřího Koska. Predlohou pre tento projekt bola moja bakalárska práca, z ktorej boli vybrané okrem úvodných strán kapitoly Úvod a časť Analýzy. <br/>
- Text bol organizovaný do kapitol, sekcií a niekoľkých stupňov podsekcií tak, aby výsledný dokument korešpondoval s predlohou. V rámci sekcií bol text rozdelený do paragrafov. Na zvýraznenie textu sa používali atribúty umožnujúce tučné písmo, číslované aj nečíslované odrážky. <br/>Použité elementy:
  {% highlight java %}
  <chapter> - kapitola
  <section> - sekcia
  <para> - odstavec
  <emphasis role="bold"> - tucne pismo
  <itemizedlist> - neoznacene odrazky
  <orderedlist> - oznacene odrazky
  {% endhighlight %}
<br/>
- V texte sa nachádzajú odkazy na iné časti dokumentu, na obrázky, popis vzorcov v texte a podobne. Pri neznámych pojmoch a skratkách sú pridané poznámky pod čiarou.
  {% highlight java %}
  K vybranym elementom v texte su pridane atributy - <literallayout id="nazov" xreflabel="popis">, a referencia na dany element: <xref linkend="nazov"/>
 Poznamky pod ciarou - <footnote><para>Text pod ciarou</para></footnote>
  {% endhighlight %}
<br/>
<b>Odkaz na stiahnutie:</b> <a href="../data/Z1-xrackol.zip" target="_blank">{{ "LINK na subor Z1-xrackol.zip" | slugify: 'pretty' }}</a><br/>       
<hr class="post">
