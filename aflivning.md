id | navn | farve | vægt (g) | smags-surhed | smags-styrke | smags-type | råvarepris (øre)
:---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: 
1 | Jordbær | Rød | 11 | Sødt | Mild | Jordbær | 16
2 | Appelsin | Orange | 12 | Sødt | Mild | Appelsin | 13
3 | Citron | Gul | 10 | Bittert | Mild | Citron | 14
4 | Salmiaktop | Sort | 6 | Sødt | Stærk | Salmial | 12
5 | Blå Haj	 | Lyseblå | 22 | Let bittert | Medium | Anis | 19
6 | Rød Perle | Rød | 8 | Sødt | Medium | Jordbær | 9
7 | Gul Perle | Gul | 8 | Bittert | Medium | Citron | 10
8 | Blå Perle | Blå | 8 | Let bittert | Stærk | Anis | 11


## 2.1 Udskriv alle informationer om alle bolcher.

> ``SELECT * FROM `bolcher` WHERE 1``

## 2.2 Find og udskriv navnene på alle de røde bolcher.

> ``SELECT * FROM `bolcher` WHERE `bolcher_farve`= "Rød"``

> ###  `` SELECT `bolcher_navn` FROM `bolcher` INNER JOIN `bolcher_farve` ON bolcher.FK_bolcher_farve_id = bolcher_farve.bolcher_farve_id WHERE `bolcher_farve_beskrivelse` = "Rød" ``

## 2.3 Find og udskriv navnene på alle de røde og de blå bolcher, i samme SQL udtræk.

> ``SELECT * FROM `bolcher` WHERE `bolcher_farve` = "rød" OR `bolcher_farve` = "blå"``

> ###  `` SELECT `bolcher_navn` FROM `bolcher` INNER JOIN `bolcher_farve` ON bolcher.FK_bolcher_farve_id = bolcher_farve.bolcher_farve_id WHERE `bolcher_farve_beskrivelse` = "Rød" OR `bolcher_farve_beskrivelse` = "Blå" ``

## 2.4 Find og udskriv navnene på alle bolcher, der ikke er røde, sorteret alfabetisk. 

> ``SELECT * FROM `bolcher` WHERE NOT `bolcher_farve` = "rød" ORDER BY `bolcher_farve` ASC``

> `` SELECT `bolcher_navn` FROM `bolcher` INNER JOIN `bolcher_farve` ON bolcher.FK_bolcher_farve_id = bolcher_farve.bolcher_farve_id WHERE NOT `bolcher_farve_beskrivelse` = "Rød" ``

## 2.5 Find og udskriv navnene på alle bolcher som starter med et “B”.

> ``SELECT * FROM `bolcher` WHERE `bolcher_navn` like 'b%'``

## 2.6 Find og udskriv navene på alle bolcher, hvor der i navnet findes mindst ét “e”.

> ``SELECT * FROM `bolcher` WHERE `bolcher_navn` like '%e%'``

## 2.7 Find og udskriv navn og vægt på alle bolcher der vejer mindre end 10 gram, sorter stigende efter vægt.

> ``SELECT `bolcher_navn`, `bolcher_vaegt` FROM `bolcher` WHERE `bolcher_vaegt` < 10 ORDER BY `bolcher_vaegt` ASC``

## 2.8 Find og udskriv navne på alle bolcher, der vejer mellem 10 og 12 gram (begge tal inklusiv), sorteret alfabetisk og derefter vægt.

> ``SELECT `bolcher_navn` FROM `bolcher` WHERE `bolcher_vaegt` BETWEEN 10 AND 12 ORDER BY `bolcher_navn` ASC``

## 2.9 Find og udskriv de tre største (tungeste) bolcher.

> ``SELECT * FROM `bolcher` ORDER BY `bolcher_vaegt` DESC LIMIT 3``

## 2.10 Udskriv alle informationer om et tilfældigt bolche, udvalgt af systemet (sql).

> ``SELECT * FROM `bolcher` ORDER BY RAND() LIMIT 1``