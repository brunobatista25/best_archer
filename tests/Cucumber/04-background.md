# Background(Contexto)

O Background permite que você adicione algum contexto aos cenários em um único recurso. A Background é muito parecido com um cenário contendo uma série de etapas. A diferença é quando é executado. O plano de fundo é executado antes de cada um dos seus cenários, mas após qualquer um dos antes de hooks .

Exemplo:

```
#language: pt

Funcionalidade: Suporte de vários sites 

  Como um dono do site Mephisto Eu quero hospedar blogs para diferentes pessoas 
  Para fazer gigantescas pilhas de dinheiro 
  
  Contexto:
     Dado um administrador global chamado "Greg" E um blog chamado "Greg's anti-tax Rants" 
     E um cliente chamado "Dr. Bill" 
     E um blog chamado "Terapia Caro" de propriedade de "Dr. Bill" 
     
     Cenário : o Dr. Bill publica seu próprio blog 
     Dado que estou logado como Dr. Bill
     Quando tento publicar no "Terapia cara"
     Então eu deveria ver "Seu artigo foi publicado". 

     Cenário : o Dr. Bill tenta publicar no blog de outra pessoa, e falha. 
     Dado que estou logado como Dr. Bill.
     Quando eu tento publicar em "revistas anti-impostos de Greg"
     Então eu deveria ver "Ei, esse não é o seu blog!" 

     Cenário : Greg publica no blog de um cliente 
     Dado que estou logado como Greg
     Quando eu tento publicar em "Terapia Caro" 
     Então eu deveria ver "Seu artigo foi publicado".
```

Para uma alternativa menos explícita ao background, verifique os ganchos com Tagged [Hooks](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/05-hooks.md);

# Boas práticas para usar Background

Não use "Background" para configurar o estado complicado, a menos que esse estado seja realmente algo que o cliente precisa saber.

Por exemplo, se o usuário e o nome do site não importarem para o cliente, você deve usar uma etapa de alto nível, como "Dado que eu estou logado como proprietário do site".

Mantenha sua seção "Background" curta .
Você está esperando que o usuário realmente se lembre dessas coisas ao ler seus cenários. Se o plano de fundo tiver mais de 4 linhas, você pode mover alguns dos detalhes irrelevantes em etapas de alto nível? Veja Passos de Chamada das Definições de Etapas .

Faça sua seção "Background" vívida .
Você deve usar nomes coloridos e tentar contar uma história, porque o cérebro humano pode acompanhar as histórias muito melhor do que pode acompanhar nomes como "Usuário A", "Usuário B", "Site 1", e assim por diante.

Mantenha seus cenários curtos e não tenha muitos.
Se a seção de fundo tiver escorregado na tela, você deve pensar em usar etapas de nível superior ou dividir o arquivo * .features em dois.


Vamos para o próximo post [Hooks](https://github.com/brunobatista25/best_archer/blob/master/tests/Cucumber/05-hooks.md); 

# Referências:
	
https://github.com/cucumber/cucumber