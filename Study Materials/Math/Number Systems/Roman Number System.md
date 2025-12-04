---
aliases:
  - Roman System
  - roman number system
  - roman system
---
Roman number system is a Non-positional [[Number Systems|number system]] that allows for non sequential description of numbers. 
## Symbols
Unlike modern system using the Arabic number symbols, the Roman's used their own symbols that have been adapted from the Greek system and the resemble modern character.

| Roman Symbol  | I   | V   | X   | L   | C   | D   | M    |
| ------------- | --- | --- | --- | --- | --- | --- | ---- |
| Decadic Value | 1   | 5   | 10  | 50  | 10  | 500 | 1000 |
Originally numbers such as **4** were writen as **IIII** and 40 as **XXXX**, which allowed for the symbols to be in any order. The more commonly used system of subtracting numbers, such as **4** represented as **IV**, was started to be used later during medieval age and it complicates the position of symbols within the number [[Study Materials/Automata/Terms/Word|string]].
By this rule any lower number to the left of a greater number is subtracting from the higher number. So in the original system this number **IX** is **11**, but in the subtracting system it is **9**, while **XI** is in both systems **11**.
## Conversion
For both direction of conversion it is important to know the roman equivalent symbols.
### Roman to Decadic
In the original version the only needed steps are to convert the symbols into their equivalent decadic values and sum them up.
$$ DVLII \to 500+5+50+1+1 =557$$
In the more modern medieval system there needs to be taken into account the subtracting rule, but otherwise the process is similar.
$$DVLII\to 500+45+1+1=547$$
### Decadic to Roman
In both versions of system the conversion from decadic to roman is more complicated then the other way around. The best way to do so is to first find the biggest possible number that can be described by one of the symbols, so for 557 that number would be D. Then continue down until there are no decadic numbers left, so for 57 that is L, for 7 it is V, for 2 it is II, ending up in DLVII.
In the modern medieval system there are certain shortcuts you can take like for example 490 can be represented by XD.