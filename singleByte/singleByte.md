# CTF Name: singleByte

![date](https://img.shields.io/badge/date-05.24.1970-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![cryptography category](https://img.shields.io/badge/category-cryptography-lightgrey.svg)
![score](https://img.shields.io/badge/score-25-blue.svg)
![solves](https://img.shields.io/badge/solves-47-brightgreen.svg)

## Description
Yup!!!! You know it!!! The very simple encryption technique that has the perfect secrecy.

## Author
pakkunandy

## Attached files
ciphertext.txt

## Summary
use CyberChef

## Flag
```
HCMUS-CTF{we_know_that_you_can_do_simple_XOR_54313154abcfe54af2ecab}
```

## Detailed solution
I use ```cat ciphertext.txt``` to check the content of the file:
```
r4SJmJOanoOFhMqDmcqLyp2Lk8qFjMqZiZiLh4iGg4SNyo6LnovKmYXKnoKLnsqFhIaTyoufnoKFmIOQj47KmouYnoOPmcqJi4TKn4SOj5iZnouEjsqego/Kg4SMhZiHi56DhYTEyqOEyp6PiYKEg4mLhsqej5iHmcbKg57Kg5nKnoKPypqYhYmPmZnKhYzKiYWEnI+YnoOEjcqCn4eLhMeYj4uOi4iGj8qahouDhJ6Pkp7KnoXKg4SJhYeamI+Cj4SZg4iGj8qej5KexsqLhpmFyoGEhZ2EyouZyomDmoKPmJ6Pkp6iqae/ucepvqyRnY+1gYSFnbWegouetZOFn7WJi4S1joW1mYOHmoaPtbKluLXf3tnb2dvf3ouIiYyP396LjNiPiYuIlw==
```
The use of characters A-Z a-z 0-9 +/ with paddding = suggested this to be a base64 encryption, however, running it through [a base64 to ascii decoder](https://www.dcode.fr/base-64-encoding) returned unprintable characters:
```
¯���������Ê��Ê�Ê���Ê��Ê����������Ê����Ê��Ê����Ê����Ê����������Ê�������Ê���Ê����������Ê���Ê�����������ÄÊ£�Ê���������Ê�����ÆÊ��Ê��Ê���Ê�������Ê��Ê����������Ê�����Ç��������Ê���������Ê��Ê����������������Ê����ÆÊ����Ê�����Ê��Ê����������¢©§¿¹Ç©¾¬���µ����µ����µ���µ���µ��µ������µ²¥¸µßÞÙÛÙÛßÞ�����ßÞ��Ø�����
```
I failed to pick up the clue "simple ecryption" in the description and "singleByte" in the name, so I ran the original ciphertext through [CyberChef's Magic function with intensive mode](https://gchq.github.io/CyberChef/#recipe=Magic(3,true,false,'')). CyberChef will automatically detect the encryption and return the best results. The first one is base64 decoded XOR with key "ea" in hexadecimal. This returns:
```
Encryption is a way of scrambling data so that only authorized parties can understand the information. In technical terms, it is the process of converting human-readable plaintext to incomprehensible text, also known as ciphertextHCMUS-CTF{we_know_that_you_can_do_simple_XOR_54313154abcfe54af2ecab}
```
