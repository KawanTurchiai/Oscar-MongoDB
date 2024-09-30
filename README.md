# Oscar-MongoDB
Atividades para trabalhar com o Oscar

1- Quantas vezes Natalie Portman foi indicada ao Oscar? 
>3 vezes<
> db.registros.countDocuments({nome_do_indicado: "Natalie Portman"})

2- Quantos Oscars Natalie Portman ganhou? 1 vez
> db.registros.countDocuments({nome_do_indicado: "Natalie Portman", vencedor: "true"})

3- Amy Adams já ganhou algum Oscar? Não, não há nenhum registro de que ele tenha ganhado.
> db.registros.countDocuments({nome_do_indicado: "Amy Adams", vencedor: "true"})

4- A série de filmes Toy Story ganhou um Oscar em quais anos? 2 premios em 2011 para o filme "Toy Story 3" e 1 em 2020 para o filme "Toy Story 4"
> db.registros.find({nome_do_filme: /Toy Story/i, vencedor: "true"}, {ano_cerimonia: 1,nome_do_filme: 1, vencedor: 1})

5- A partir de que ano que a categoria "Actress" deixa de existir? A partir de 1931
> db.registros.find({categoria: /Actress/i}, {categoria: 1, ano_cerimonia: 1})

6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano? Foi Janet Gaynor no ano de 1928
> db.registros.find({categoria: "ACTRESS", vencedor: "true"}).sort({ano_filmagem: 1}).limit(1)

7- Na campo "Vencedor", altere todos os valores com "Sim" para 1 e todos os valores "Não" para 0.
> db.registros.updateMany({vencedor: "true", vencedor: "false"}, {$set: {vencedor: 1, vencedor: 0}})

8- Em qual edição do Oscar "Crash" concorreu ao Oscar? Concorreu 5 vezes na 78.ª edição do Oscar.
> db.registros.find ({nome_do_filme: "Crash"}, {nome_do_filme: 1, cerimonia: 1, _id:0})

9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou.

10- O filme Central do Brasil aparece no Oscar?

11- Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 

14 - Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?
