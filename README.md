# README
% Time-stamp: <2023-07-12 19:22:33 banbara>

### OUTLINE

This package includes a collection of ASP encodings for solving the Curriculum-Based Course
Timetabling (CB-CTT) Problem.
The CB-CTT problem has been used in the second International Timetabling
Competition (ITC-2007).

### REQUIREMENTS
- [clingo](https://potassco.org/clingo/) (version 5 or higher)

### OPTIONAL REQUIREMENTS
- Perl 3 for decoding answer sets to solutions of ITC competition format
- C++ for validating solutions of ITC competition format

### USAGE

```
% clingo teaspoon.lp ud1.lp bench/Test_asp/toy.lp  > toy.log
% ./bin/decode.perl toy.log > toy.sol
% cat toy.sol
SceCosC rA 0 1
SceCosC rB 2 1
SceCosC rB 1 3
ArcTec rB 1 0
ArcTec rB 2 0
ArcTec rB 1 1
TecCos rB 4 1
TecCos rC 0 2
TecCos rC 1 2
TecCos rB 2 2
TecCos rB 4 2
Geotec rC 3 0
Geotec rB 0 1
Geotec rA 1 1
Geotec rC 3 1
Geotec rB 2 3
```

```
% ./bin/validator UD1 bench/Test_ectt/toy.ectt toy.sol

Violations of Lectures (hard) : 0
Violations of Conflicts (hard) : 0
Violations of Availability (hard) : 0
Violations of RoomOccupation (hard) : 0
Cost of RoomCapacity (soft) : 0
Cost of MinWorkingDays (soft) : 0
Cost of IsolatedLectures (soft) : 0

Summary: Total Cost = 0
```

### NOTE
This package includes the program `bin/validator.cc` that validates a
solution for a CB-CTT instance for all the five formulations. This
program was developed by Andrea Schaerf and Luca Di Gaspero.

### LICENSE

This software is distributed under [the BSD 3-Clause License](https://opensource.org/license/bsd-3-clause/).

### Citing

- Mutsunori Banbara, Takehide Soh, Naoyuki Tamura, Katsumi Inoue and Torsten Schaub. 
  Answer Set Programming as a Modeling Language for Course Timetabling. 
  Theory and Practice of Logic Programming, 13(4-5):783-798, Cambridge Journals, 2013. 
  DOI: [10.1017/S1471068413000495](http://doi.org/10.1017/S1471068413000495)

- Mutsunori Banbara, Katsumi Inoue, Benjamin Kaufmann, Tenda Okimoto, Torsten Schaub, Takehide Soh, Naoyuki Tamura, and Philipp Wanko.
  teaspoon: Solving the Curriculum-Based Course Timetabling Problems with Answer Set Programming. 
  Annals of Operations Research, Vol.275, Issue.1, pp.3–37, April 2019, Springer.
  DOI: [10.1007/s10479-018-2757-7](http://doi.org/10.1007/s10479-018-2757-7)

### AUTHORS
- Mutsunori Banbara
- banbara@nagoya-u.jp
- Graduate School of Informatics, Nagoya University

Enjoy!
