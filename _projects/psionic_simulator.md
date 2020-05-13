---
title: Psionic Simulator
link: https://github.com/Wigsinator/PsionicSimulator
img: /assets/img/d20.png
---
A simulator that counts the number of dice rolls when a particular roll changes the size of the next die roll.

<!--more-->

This is a project I made pretty much entirely for fun. In the Dungeons and Dragons 5e Unearthed Arcana "Psionic Options Revisited", there is a new game mechanic implemented known as the "Psionic Talent Die". What makes it remarkable is that, while the starting die size is determined by your level, the size of die you use on subsequent rolls is determined by what you rolled on the previous roll's die. On a 1, the die increases in size, up to the starting size, and if the maximum value is rolled, the die decreases in size, becoming unusable for the rest of the day if a 4 is rolled on a 4 sided die.  
This code counts how many times a given die can be used before becoming unusable 10,000 times, then takes the average number of uses, as well as the median. It does this for each possible starting die size.