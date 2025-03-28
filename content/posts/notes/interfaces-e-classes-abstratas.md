+++
date = '2025-03-28T04:34:06-03:00'
draft = false
title = 'Interfaces E Classes Abstratas'
tags = ['cheatsheet', 'POO', 'C#']
+++

# Interfaces
As interfaces são um "contrato" para as classes seguirem, por exemplo:

```c#
interface IVeiculo
{
	public string Tipo {get; set;}
	int Potencia {get; set;}
}
class Carro : IVeiculo
{
	public string Tipo {get; set;}
	public int Potencia {get; set;}
}
class Moto : IVeiculo
{
	public string Tipo {get; set;}
	public int Potencia {get; set;}
}
    }
```

Neste exemplo, a interface "obriga" as classes que a herdam a terem suas propriedades e métodos.

# Classes Abstratas
Já as classes abstratas, são as classes criadas que server para outras classes herdarem, mas não sendo necessariamente um contrato, mas sim um conceito abstrato que não pode ser instanciada.

```c#
public abstract class Veiculo
{
	public string Tipo {get; set;}
	int Potencia {get; set;}
}
class Carro : Veiculo
{
	public string Tipo {get; set;}
	public int Potencia {get; set;}
}
class Moto : Veiculo
{
	public string Tipo {get; set;}
	public int Potencia {get; set;}
}
```

Aqui, podemos notar que não faz sentido instanciarmos Veiculo, pois o que é um veiculo? logo, ele precisa ser um carro ou uma moto(exemplo), mas não só um veiculo. A keyword 'abstract' impede o instanciamento.