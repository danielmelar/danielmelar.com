+++
date = '2025-03-28T04:03:47-03:00'
draft = false
title = 'Base64 Cheatseet'
tags = ['cheatsheet', 'base64', 'programming']
+++

#cheatsheet #base64 #programming

## O que é base64?

Base64 é uma forma de escrever código binário.
É constituído por 64 caracteres: A-Z a-z 0-9 + /

Um exemplo de texto reescrito em base64:
texto -> abc
binário -> 01100001 01100010 01100011
base64 -> YWJj

em base64, o binário é dividido em grupos de 6 bits para representar cada caractere, e então:
ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/

011000 -> Y
010110 -> W
001001 -> J
100011 - j

algoritmo:
1. Converter para binário
2. Dividir binário em grupo de 6 bits
3. Converter cada grupo em um número decimal
4. Linkar número de cada grupo a seu equivalente na tabela base64

## O que são os == no final do base64?
São padding, ou, preenchimento. Como o base64 exige grupos de 6 bits, o múltiplo comum de 6 e 8(bits) é 24(3 bytes), logo, quando a o binário possui bytes faltantes para a conversão, adiciona o preenchimento
ABC -> 3 bytes -> sem =
AB -> 2 bytes -> 1 =
A -> 1 byte -> 2 ==

## Pra que serve o base64
Serve principalmente para a transferência de dados através da Internet.

Referências:
- https://www.tabnews.com.br/SamuelMayer/explicando-base64
- https://www.writesoftwarewell.com/base64-encoding-explained/
- https://lioncoding.com/calculate-a-file-size-from-base64-string/


## Verificando tamanho de arquivo em base64

```csharp

    var length = data.Length;  
    var sizeInByte = Math.Ceiling((double)length / 4) * 3;

    if (length >= 2)  
    {  
        var padding = data[^2..];  
        sizeInByte = padding.Equals("==") ? sizeInByte - 2 : padding[1].Equals("=") ? sizeInByte - 1 : sizeInByte;  
    }

    return sizeInByte;  
```
