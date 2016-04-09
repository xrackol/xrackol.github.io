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
  {% highlight xml %}
  <chapter> - kapitola
  <section> - sekcia
  <para> - odstavec
  <emphasis role="bold"> - tucne pismo
  <itemizedlist> - neoznacene odrazky
  <orderedlist> - oznacene odrazky
  {% endhighlight %}
<br/>
- V texte sa nachádzajú odkazy na iné časti dokumentu, na obrázky, popis vzorcov v texte a podobne. Pri neznámych pojmoch a skratkách sú pridané poznámky pod čiarou.
  {% highlight xml %}
 <literallayout id="nazov" xreflabel="popis"> -  k vybranym elementom v texte su pridane taketo atributy
 <xref linkend="nazov"/> - referencia na dany element
 <footnote><para>Text pod ciarou</para></footnote> - poznamky pod ciarou
  {% endhighlight %}
- Na konci dokumentu je zoznam použitej literatúry. V texte sa nachádzajú citácie ktoré priamo odkazujú na konkrétny záznam v bibliografií.
  {% highlight xml %}
- Vytvorenie zaznamu v bibliografii:
<br/>
    <bibliomixed id="bib.orgonas">ORGONÁŠ, J.: <title>Všetko o Wi-Fi / 1. časť, PC Revue 07/2009</title>
      <bibliomisc>Dostupný na: 
        <ulink url="http://www.itnews.sk/tituly/pc-revue/clanky/2009-07-07/c1185-vsetko-o-wi-fi-1.-cast"></ulink>
      </bibliomisc>
    </bibliomixed>
  {% endhighlight %}
<br/>
- Citovanie na konkretne dielo v bibliografii:
  {% highlight xml %}
<xref linkend="bib.niso"/>
  {% endhighlight %}
- V dokumente sa nachádzajú viaceré obrázky a tabuľka, vrátane odkazov, ktoré odkazujú buď priamo na daný objekt, alebo mierne pred obrázok - aby bolo po kliknutí na odkaz vidno aj popis vzorca, ktorý je na obrázku.
- Pridanie obrazku do dokumentu:
  {% highlight xml %}
          <figure id="trilateracia" xreflabel="Trilaterácia"><title>Trilaterácia</title>
          <mediaobject>
            <imageobject>
              <imagedata fileref="trilateracia.png"/>
            </imageobject>
            <textobject><phrase></phrase></textobject>
          </mediaobject>
          </figure>
  {% endhighlight %}
- odkaz k obrazku: 
{% highlight xml %}
<xref linkend="trilateracia"/>
{% endhighlight %}
<br/>
- Vytvorenie trojstlpcovej tabulky s prehladom pojmov v zavere dokumentu:
<br/>
{% highlight xml %}
<table frame='all'  id="tabulka" xreflabel="tabuľke"><title>Prehľad</title>
<tgroup cols='3' align='left' colsep='1' rowsep='1'>
<colspec colname='colname 1'/>
<colspec colname='colname 2'/>
<colspec colname='colname 3'/>
<colspec colname='colname 4'/>

<thead>
<row>
  <entry>Metódy lokalizácie</entry>
  <entry>Knižničné protokoly</entry>
  <entry>Existujúce riešenia</entry>
</row>
</thead>
<tbody>
<row>
  <entry>WiFi Fingerprinting</entry>
  <entry>Z39.50</entry>
  <entry>COEX Soul, WiFi fingerprinting</entry>
</row>
<row>
  <entry>Trilaterácia</entry>
  <entry>SIP2</entry>
  <entry>WiFi Fingerprinting a PDR</entry>
</row>
<row>
  <entry>Bluetooth</entry>
  <entry>NCIP</entry>
  <entry>Spracovanie obrazu a trilaterácia</entry>
</row>
<row>
  <entry>PDR</entry>
  <entry></entry>
  <entry></entry>
</row>

</tbody>
</tgroup>
</table>
  {% endhighlight %}
<br/>
- Odkaz na tabulku v texte:
{% highlight xml %}
<xref linkend="tabulka"/>
  {% endhighlight %}
 - Na začiatku dokumentu bol vytvorený viacúrovňový register pojmov, ktorý obsahuje základné pojmy, ktoré sú bližšie rozobraté v texte
 - Na začiatku dokumentu je vložený automaticky generovaný register pojmov, obsahuje len názov:
 {% highlight xml %}
<index>
  <title>Register pojmov</title>
</index>
  {% endhighlight %}
- Samotné položky do registra pojmov"
{% highlight xml %}
<indexterm>
   <primary>Možnosti lokalizácie:</primary>
   <secondary>WiFi Fingerprinting</secondary>
   <tertiary>Metóda: Algoritmus najbližšieho suseda</tertiary>
</indexterm>
  {% endhighlight %}

- Okrem registra pojmov bol vytvorený aj slovník pojmov, kde sú neznáme pojmy vysvetlené, vloženie jedného záznamu do slovníka pojmov:
{% highlight xml %}
<glossary><title>Slovník pojmov</title>

<glossentry id="xml"><glossterm><emphasis role="bold">WiFi Fingerprinting</emphasis></glossterm>
<glossdef>
  <para>metóda používaná pri navigácií založená na porovnávaní intenzít signálov bezdrôtových sietí, nameraných v reálnom čase, s mapou signálov vytvorenou pred spustením navigácie.<?vskip 1pt?></para>
</glossdef>
</glossentry>
</glossary>
  {% endhighlight %}

<b>Odkaz na stiahnutie:</b> <a href="../data/Z1-xrackol.zip" target="_blank">{{ "LINK na subor Z1-xrackol.zip" | slugify: 'pretty' }}</a><br/>       
<hr class="post">
