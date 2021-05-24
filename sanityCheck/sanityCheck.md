# CTF Name: Challenge name

![date](https://img.shields.io/badge/date-05.24.1970-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![cryptography category](https://img.shields.io/badge/category-cryptography-lightgrey.svg)
![score](https://img.shields.io/badge/score-25-blue.svg)
![solves](https://img.shields.io/badge/solves-53-brightgreen.svg)

## Description
Welcome to HCMUS_-CTF 2021. We're Blackpinker.

## Author
pakkunandy

## Attached files
encoded

## Summary
run it through base32 decoder -> base64 decoder -> caesar decoder

## Flag
```
HCMUS-CTF{You_know_some_command_line_stuff}
```

## Detailed solution
I checked the content of encoded using ```cat encoded```
```
MQZGQ3K2PFBDMYTONB4USR3YNFQUGQTJLEZUU2CJI5UGUSKHPBUWCR2VM5RW26DZLJTW6S2WKZBGCU2FLF2FKRLEKRSTA4DZLAZDK3DDNQ4VAZKXGV3WKR2OGJMVQ2DZLJLDS4LDNZWHOWLOOB4VQMTENFMDGVTXMVWWQ3KYGNBG4YZRHB4U2RCJPBTFCPJ5
```
The file only contained characters A-Z and 2-6 which lead me to believe it might have been base32 encrypted, as base32 use characters from A-Z and 2-7. So I ran it through a base32 decoder on [this website](https://www.dcode.fr/base-32-encoding), which yielded:
```
d2hmZyB6bnhyIGxiaCBiY3JhIGhjIGxiaGUgcmxyZgoKVVBaSEYtUEdTe0pyX25lcl9PeW5weGN2YXhyZV9qcnlwYnpyX2diX3VwemhmX3Bnc18yMDIxfQ==
```
The two equal signs padding at the end and the use of characters A-Z a-z 0-9 indicated this code might have been encrypted with base64 encryption, which uses A-Z a-z 0-9 +/ and = as padding, I ran it through a base64 decoder on the same website:
```
UPZHF-PGS{Jr_ner_Oynpxcvaxre_jrypbzr_gb_upzhf_pgs_2021}
```
It's clearly a Caesar cipher, and so I ran it through the caesar decoder on that website, which gave the flag:
```
HCMUS-CTF{We_are_Blackpinker_welcome_to_hcmus_ctf_2021}
```
