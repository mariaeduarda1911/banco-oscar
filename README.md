# Oscar - Exercícios SQL
 
Bem-vindo à base de dados do **Oscar**!
 
O Oscar é a premiação mais prestigiada do cinema mundial, realizada anualmente desde 1929 pela Academia de Artes e Ciências Cinematográficas. Nesta base de dados, você encontrará registros históricos de indicados e vencedores de diversas categorias ao longo de quase 100 anos de história do cinema.
 
Nestes exercícios, você vai explorar o banco de dados SQL do Oscar e responder perguntas que revelam insights fascinantes sobre a história do cinema, tendências de premiação, e momentos marcantes da indústria cinematográfica.
---
 
## Nível 1: Primeiros Passos
 
### Conhecendo a Base de Dados
 
**1.1** Quantos registros existem na tabela de indicados ao Oscar?
 
R: 10889 registros
 
```sql
SELECT COUNT(*) FROM indicados_ao_oscar;
```
 
**1.2.1** Quais são as diferentes categorias de premiação que existem no banco de dados? Liste todas as categorias únicas.
 
R:
```ACTOR
ACTRESS
ART DIRECTION
CINEMATOGRAPHY
DIRECTING (Comedy Picture)
DIRECTING (Dramatic Picture)
ENGINEERING EFFECTS
OUTSTANDING PICTURE
UNIQUE AND ARTISTIC PICTURE
WRITING (Adaptation)
WRITING (Original Story)
WRITING (Title Writing)
SPECIAL AWARD
DIRECTING
WRITING
OUTSTANDING PRODUCTION
SOUND RECORDING
SHORT SUBJECT (Cartoon)
SHORT SUBJECT (Comedy)
SHORT SUBJECT (Novelty)
ASSISTANT DIRECTOR
FILM EDITING
MUSIC (Scoring)
...
```
 
```sql
SELECT DISTINCT categoria FROM indicados_ao_oscar;
```
 
**1.2.2** **Quantas** categorias únicas existem?
 
R: 115 registros
 
```sql
SELECT COUNT(DISTINCT categoria) FROM indicados_ao_oscar;
```
 
**1.3** Qual foi o primeiro ano de cerimônia do Oscar registrado na base?
 
R: 1928
 
```sql
SELECT MIN(ano_cerimonia) FROM indicados_ao_oscar;
```
 
**1.4** Qual foi o último ano de cerimônia registrado na base?
 
R: 2024
 
```sql
SELECT MAX(ano_cerimonia) FROM indicados_ao_oscar;
```
 
**1.5** Quantas cerimônias do Oscar estão registradas no total?
 
 R: 96
 
 ```sql
SELECT COUNT(DISTINCT edicao_cerimonia) FROM indicados_ao_oscar;
```
 
**1.6** Atualize os registros da tabela com os dados do Oscar 2025 e 2026 (pesquise os vencedores e adicione-os).
 
R:
 
 ```sql
INSERT INTO indicados_ao_oscar
    (ano_filmagem, ano_cerimonia, edicao_cerimonia,
     categoria, nome_indicado, nome_filme, vencedor)
VALUES
(2024, 2025, 97, 'Melhor Ator', 'Adrien Brody', 'The Brutalist', TRUE),
(2024, 2025, 97, 'Melhor Ator Coadjuvante', 'Kieran Culkin', 'A Real Pain', TRUE),
(2024, 2025, 97, 'Melhor Atriz', 'Mikey Madison', 'Anora', TRUE),
(2024, 2025, 97, 'Melhor Atriz Coadjuvante', 'Zoe Saldaña', 'Emilia Pérez', TRUE),
(2024, 2025, 97, 'Melhor Filme de Animação', 'Flow', 'Flow', TRUE),
(2024, 2025, 97, 'Melhor Curta-Metragem de Animação', 'Shirin Sohani e Hossein Molayemi', 'In the Shadow of the Cypress', TRUE),
(2024, 2025, 97, 'Melhor Fotografia', 'Lol Crawley', 'The Brutalist', TRUE),
(2024, 2025, 97, 'Melhor Figurino', 'Paul Tazewell', 'Wicked', TRUE),
(2024, 2025, 97, 'Melhor Direção', 'Sean Baker', 'Anora', TRUE),
(2024, 2025, 97, 'Melhor Documentário', 'Basel Adra, Rachel Szor, Hamdan Ballal e Yuval Abraham', 'No Other Land', TRUE),
(2024, 2025, 97, 'Melhor Documentário em Curta-Metragem', 'Molly O’Brien e Lisa Remington', 'The Only Girl in the Orchestra', TRUE),
(2024, 2025, 97, 'Melhor Montagem', 'Sean Baker', 'Anora', TRUE),
(2024, 2025, 97, 'Melhor Filme Internacional', 'Brasil', 'Ainda Estou Aqui', TRUE),
(2024, 2025, 97, 'Melhor Maquiagem e Cabelo', 'Pierre-Olivier Persin, Stéphanie Guillon e Marilyne Scarselli', 'The Substance', TRUE),
(2024, 2025, 97, 'Melhor Trilha Sonora Original', 'Daniel Blumberg', 'The Brutalist', TRUE),
(2024, 2025, 97, 'Melhor Canção Original', 'Clément Ducol, Camille e Jacques Audiard', 'El Mal - Emilia Pérez', TRUE),
(2024, 2025, 97, 'Melhor Filme', 'Alex Coco, Samantha Quan e Sean Baker', 'Anora', TRUE),
(2024, 2025, 97, 'Melhor Design de Produção', 'Nathan Crowley e Lee Sandales', 'Wicked', TRUE),
(2024, 2025, 97, 'Melhor Curta-Metragem em Live Action', 'Victoria Warmerdam e Trent', 'I’m Not a Robot', TRUE),
(2024, 2025, 97, 'Melhor Som', 'Gareth John, Richard King, Ron Bartlett e Doug Hemphill', 'Dune: Part Two', TRUE),
(2024, 2025, 97, 'Melhores Efeitos Visuais', 'Paul Lambert, Stephen James, Rhys Salcombe e Gerd Nefzer', 'Dune: Part Two', TRUE),
(2024, 2025, 97, 'Melhor Roteiro Adaptado', 'Peter Straughan', 'Conclave', TRUE),
(2024, 2025, 97, 'Melhor Roteiro Original', 'Sean Baker', 'Anora', TRUE),
 
(2025, 2026, 98, 'Melhor Ator', 'Michael B. Jordan', 'Sinners', TRUE),
(2025, 2026, 98, 'Melhor Ator Coadjuvante', 'Sean Penn', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Atriz', 'Jessie Buckley', 'Hamnet', TRUE),
(2025, 2026, 98, 'Melhor Atriz Coadjuvante', 'Amy Madigan', 'Weapons', TRUE),
(2025, 2026, 98, 'Melhor Filme de Animação', 'Maggie Kang, Chris Appelhans e Michelle L. M. Wong', 'KPop Demon Hunters', TRUE),
(2025, 2026, 98, 'Melhor Curta-Metragem de Animação', 'Chris Lavis e Maciek Szczerbowski', 'The Girl Who Cried Pearls', TRUE),
(2025, 2026, 98, 'Melhor Elenco', 'Cassandra Kulukundis', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Fotografia', 'Autumn Durald Arkapaw', 'Sinners', TRUE),
(2025, 2026, 98, 'Melhor Figurino', 'Kate Hawley', 'Frankenstein', TRUE),
(2025, 2026, 98, 'Melhor Direção', 'Paul Thomas Anderson', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Documentário', 'David Borenstein, Pavel Talankin, Helle Faber e Alžběta Karásková', 'Mr. Nobody Against Putin', TRUE),
(2025, 2026, 98, 'Melhor Documentário em Curta-Metragem', 'Joshua Seftel e Conall Jones', 'All the Empty Rooms', TRUE),
(2025, 2026, 98, 'Melhor Montagem', 'Andy Jurgensen', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Filme Internacional', 'Noruega', 'Sentimental Value', TRUE),
(2025, 2026, 98, 'Melhor Curta-Metragem em Live Action', 'Sam A. Davis e Jack Piatt', 'The Singers', TRUE),
(2025, 2026, 98, 'Melhor Curta-Metragem em Live Action', 'Alexandre Singh e Natalie Musteata', 'Two People Exchanging Saliva', TRUE),
(2025, 2026, 98, 'Melhor Maquiagem e Cabelo', 'Mike Hill, Jordan Samuel e Cliona Furey', 'Frankenstein', TRUE),
(2025, 2026, 98, 'Melhor Trilha Sonora Original', 'Ludwig Göransson', 'Sinners', TRUE),
(2025, 2026, 98, 'Melhor Canção Original', 'EJAE, Mark Sonnenblick, Joong Gyu Kwak, Yu Han Lee, Hee Dong Nam, Jeong Hoon Seo e Teddy Park', 'Golden - KPop Demon Hunters', TRUE),
(2025, 2026, 98, 'Melhor Filme', 'Adam Somner, Sara Murphy e Paul Thomas Anderson', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Design de Produção', 'Tamara Deverell e Shane Vieau', 'Frankenstein', TRUE),
(2025, 2026, 98, 'Melhor Som', 'Gareth John, Al Nelson, Gwendolyn Yates Whittle, Gary A. Rizzo e Juan Peralta', 'F1', TRUE),
(2025, 2026, 98, 'Melhores Efeitos Visuais', 'Joe Letteri, Richard Baneham, Eric Saindon e Daniel Barrett', 'Avatar: Fire and Ash', TRUE),
(2025, 2026, 98, 'Melhor Roteiro Adaptado', 'Paul Thomas Anderson', 'One Battle After Another', TRUE),
(2025, 2026, 98, 'Melhor Roteiro Original', 'Ryan Coogler', 'Sinners', TRUE);
```
 
---
 
## Nível 2: Explorando Categorias
 
**2.1** Quantas indicações existem para cada categoria? Agrupe por categoria e ordene da mais frequente para a menos frequente.
 
R:
DIRECTING	469
FILM EDITING	450
ACTOR IN A SUPPORTING ROLE	440
ACTRESS IN A SUPPORTING ROLE	440
DOCUMENTARY (Short Subject)	378
BEST PICTURE	371
DOCUMENTARY (Feature)	345
CINEMATOGRAPHY	338
FOREIGN LANGUAGE FILM	315
ART DIRECTION	307
COSTUME DESIGN	295
MUSIC (Original Score)	270
SOUND	245
ACTOR IN A LEADING ROLE	240
ACTRESS IN A LEADING ROLE	240
ACTRESS	236
MUSIC (Original Song)	235
ACTOR	232
SHORT FILM (Live Action)	226
SHORT FILM (Animated)	215
MUSIC (Song)	215
SOUND RECORDING	195
SHORT SUBJECT (Cartoon)	169
CINEMATOGRAPHY (Black-and-White)	161
WRITING (Original Screenplay)	160
VISUAL EFFECTS	155
MUSIC (Music Score of a Dramatic or Comedy Picture)	148
ART DIRECTION (Black-and-White)	138
CINEMATOGRAPHY (Color)	135
HONORARY AWARD	133
MUSIC (Scoring of a Musical Picture)	127
WRITING (Screenplay Written Directly for the Screen)	120
ART DIRECTION (Color)	112
WRITING (Adapted Screenplay)	110
WRITING (Screenplay)	104
OUTSTANDING PRODUCTION	102
ANIMATED FEATURE FILM	99
WRITING (Screenplay--based on material from another medium)	95
SPECIAL EFFECTS	93
BEST MOTION PICTURE	90
SHORT SUBJECT (One-reel)	90
MAKEUP	87
SOUND EDITING	86
SOUND MIXING	85
SHORT SUBJECT (Two-reel)	81
COSTUME DESIGN (Black-and-White)	77
COSTUME DESIGN (Color)	77
SHORT SUBJECT (Live Action)	68
WRITING (Screenplay Based on Material from Another Medium)	65
MUSIC (Scoring)	64
PRODUCTION DESIGN	60
WRITING (Story and Screenplay--written directly for the screen)	60
SPECIAL AWARD	56
WRITING (Screenplay Based on Material Previously Produced or Published)	55
WRITING (Original Story)	52
WRITING (Motion Picture Story)	50
SOUND EFFECTS EDITING	47
MAKEUP AND HAIRSTYLING	46
IRVING G. THALBERG MEMORIAL AWARD	45
JEAN HERSHOLT HUMANITARIAN AWARD	44
MUSIC (Original Dramatic Score)	41
WRITING (Story and Screenplay)	35
ASSISTANT DIRECTOR	35
OUTSTANDING MOTION PICTURE	30
MUSIC (Scoring of Music--adaptation or treatment)	30
MUSIC (Song--Original for the Picture)	25
DOCUMENTARY	25
WRITING (Original Motion Picture Story)	25
INTERNATIONAL FEATURE FILM	25
DANCE DIRECTION	21
MUSIC (Original Musical or Comedy Score)	20
MUSIC (Music Score of a Dramatic Picture)	20
WRITING (Story and Screenplay--based on factual material or material not previously published or produced)	20
MUSIC (Music Score--substantially original)	20
WRITING (Adaptation)	17
SPECIAL VISUAL EFFECTS	16
SHORT SUBJECT (Comedy)	13
SHORT SUBJECT (Novelty)	12
WRITING	11
SOUND EFFECTS	10
MUSIC (Original Music Score)	10
MUSIC (Original Score--for a motion picture [not a musical])	10
MUSIC (Score of a Musical Picture--original or adaptation)	10
DOCUMENTARY FEATURE FILM	10
DOCUMENTARY SHORT FILM	10
WRITING (Screenplay Adapted from Other Material)	10
WRITING (Screenplay Written Directly for the Screen--based on factual material or on story material not previously published or produced)	10
SHORT SUBJECT (Animated)	9
SPECIAL ACHIEVEMENT AWARD (Visual Effects)	9
MUSIC (Scoring: Original Song Score and Adaptation -or- Scoring: Adaptation)	9
OUTSTANDING PICTURE	8
MUSIC (Original Song Score)	8
MUSIC (Scoring: Adaptation and Original Song Score)	8
MUSIC (Original Song Score and Its Adaptation or Adaptation Score)	6
SHORT SUBJECT (Color)	6
MUSIC (Original Song Score and Its Adaptation -or- Adaptation Score)	6
WRITING (Story and Screenplay--based on material not previously published or produced)	5
HONORARY FOREIGN LANGUAGE FILM AWARD	5
WRITING (Screenplay--Adapted)	5
WRITING (Screenplay--Original)	5
SPECIAL ACHIEVEMENT AWARD (Sound Effects Editing)	4
DIRECTING (Dramatic Picture)	3
MUSIC (Original Song Score or Adaptation Score)	3
ENGINEERING EFFECTS	3
UNIQUE AND ARTISTIC PICTURE	3
WRITING (Title Writing)	3
SPECIAL ACHIEVEMENT AWARD	3
MUSIC (Adaptation Score)	3
SHORT FILM (Dramatic Live Action)	3
DIRECTING (Comedy Picture)	2
SPECIAL FOREIGN LANGUAGE FILM AWARD	2
GORDON E. SAWYER AWARD	1
AWARD OF COMMENDATION	1
SPECIAL ACHIEVEMENT AWARD (Sound Effects)	1
SPECIAL ACHIEVEMENT AWARD (Sound Editing)	
 
```sql
 SELECT categoria, COUNT(*) AS total_indicacoes FROM indicados_ao_oscar GROUP BY categoria ORDER BY total_indicacoes DESC;
```
 
**2.2** Qual categoria teve mais indicações ao longo da história do Oscar?
R: 'DIRECTING', '469'

```sql
SELECT categoria, COUNT(*) AS total FROM indicados_ao_oscar GROUP BY categoria ORDER BY total DESC LIMIT 1;
```
 
**2.3** Qual categoria teve menos indicações ao longo da história?
R:'GORDON E. SAWYER AWARD', '1'

```sql
SELECT categoria, COUNT(*) AS total FROM indicados_ao_oscar GROUP BY categoria ORDER BY total ASC LIMIT 1;
```
 
**2.4** A partir de que ano a categoria "ACTRESS" deixou de existir? (Dica: procure a última cerimônia com essa categoria)
R: 1976

```sql
SELECT MAX(ano_cerimonia) FROM indicados_ao_oscar WHERE categoria = 'ACTRESS';
```
 
**2.5** Quais categorias existiam na primeira cerimônia (1928) e não existem mais hoje?
R: ACTOR
ACTRESS
ART DIRECTION
OUTSTANDING PICTURE
WRITING

```sql
SELECT DISTINCT categoria FROM indicados_ao_oscar WHERE ano_filmagem = 1928 AND categoria NOT IN (
      SELECT DISTINCT categoria 
      FROM indicados_ao_oscar 
      WHERE ano_cerimonia = (SELECT MAX(ano_cerimonia) FROM indicados_ao_oscar)
  );
```
 
**2.6** Liste todas as categorias que contêm a palavra "DIRECTING" no nome.
R: DIRECTING
DIRECTING (Comedy Picture)
DIRECTING (Dramatic Picture)

```sql
SELECT DISTINCT categoria FROM indicados_ao_oscar WHERE categoria LIKE '%DIRECTING%'
ORDER BY categoria;
```
---
 
## Nível 3: Atores e Atrizes Famosos
 
### Natalie Portman
 
**3.1** Quantas vezes Natalie Portman foi indicada ao Oscar?
R: 3

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Natalie Portman%';
```
 
**3.2** Quantos Oscars Natalie Portman ganhou?
R: 1

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Natalie Portman%'
AND vencedor = TRUE;
```
 
**3.3** Em quais anos e por quais filmes Natalie Portman foi indicada?
R:  2005	Closer
2011	Black Swan
2017	Jackie

```sql
SELECT ano_cerimonia, nome filme FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Natalie Portman%'
ORDER BY ano_cerimonia;
```
 
**3.4** Liste todas as indicações de Natalie Portman mostrando: ano, categoria, filme e se venceu.
R:2005	ACTRESS IN A SUPPORTING ROLE	Closer	0
2011	ACTRESS IN A LEADING ROLE	Black Swan	1
2017	ACTRESS IN A LEADING ROLE	Jackie	0

```sql
SELECT ano_cerimonia, categoria, nome_filme, vencedor FROM indicados_ao_oscar
WHERE nome_indicado LIKE '%Natalie Portman%'ORDER BY ano_cerimonia;
```
 
### Viola Davis
 
**3.5** Quantas vezes Viola Davis foi indicada ao Oscar?
 
R: 4
 
```sql
SELECT COUNT(*) FROM indicados_ao_oscar
WHERE nome_indicado LIKE "%Viola Davis%"
```
 
**3.6** Quantos Oscars Viola Davis ganhou?
 
R: 1
 
```sql
SELECT COUNT(*) FROM indicados_ao_oscar
WHERE nome_indicado LIKE "%Viola Davis%"
AND
vencedor = true;
```
 
**3.7** Por quais filmes Viola Davis foi indicada?
R: Doubt
The Help
Fences
Ma Rainey's Black Bottom

```sql
SELECT nome filme FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Viola Davis%';
```
 
### Amy Adams
 
**3.8** Amy Adams já ganhou algum Oscar?
R: Não

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Amy Adams%' AND vencedor = TRUE;
```
 
**3.9** Quantas vezes Amy Adams foi indicada sem ganhar?
R: 6

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Amy Adams%' AND vencedor = FALSE;
```
 
### Denzel Washington
 
**3.10** Denzel Washington já ganhou algum Oscar?
R: Sim

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Denzel Washington%'
AND vencedor = TRUE;
```

 
**3.11** Quantas vezes Denzel Washington foi indicado ao Oscar?
R: 10

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Denzel Washington%';
```
 
**3.12** Liste todos os Oscars que Denzel Washington ganhou (ano, categoria, filme).
R: 1990	ACTOR IN A SUPPORTING ROLE	Glory
2002	ACTOR IN A LEADING ROLE	Training Day

```sql
SELECT ano_cerimonia, categoria, nome filme FROM indicados_ao_oscar WHERE nome_indicado LIKE '%Denzel Washington%'
AND vencedor = TRUE ORDER BY ano_cerimonia;
```
 
---
 
## Nível 4: Vencedores Históricos
 
**4.1** Quem ganhou o primeiro Oscar para Melhor Atriz (ACTRESS)? Em que ano e por qual filme?
R: 1928	Janet Gaynor	7th Heaven

```sql
SELECT ano_cerimonia, nome_indicado, nome filme FROM indicados_ao_oscar WHERE categoria = 'ACTRESS'
AND vencedor = TRUE ORDER BY ano_cerimonia LIMIT 1;
```
 
**4.2** Quem ganhou o primeiro Oscar para Melhor Ator (ACTOR)? Em que ano e por qual filme?
R: 1928	Emil Jannings	The Last Command

```sql
SELECT ano_cerimonia, nome_indicado, nome filme FROM indicados_ao_oscar WHERE categoria = 'ACTOR'
AND vencedor = TRUE ORDER BY ano_cerimonia LIMIT 1;
```
 
**4.3** Quantos vencedores existem ao todo na base de dados?
R: 2465

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE vencedor = TRUE;
```
 
**4.4** Liste todos os filmes que ganharam o Oscar de Melhor Filme (categoria "OUTSTANDING PICTURE" ou "BEST PICTURE").
R: 1928	Wings
1929	The Broadway Melody
1963	Lawrence of Arabia
1964	Tom Jones
1965	My Fair Lady
1966	The Sound of Music
1967	A Man for All Seasons
1968	In the Heat of the Night
1969	Oliver!
1970	Midnight Cowboy
1971	Patton
1972	The French Connection
1973	The Godfather
1974	The Sting
1975	The Godfather Part II
1976	One Flew over the Cuckoo's Nest
1977	Rocky
1978	Annie Hall
1979	The Deer Hunter
1980	Kramer vs. Kramer
1981	Ordinary People
1982	Chariots of Fire
1983	Gandhi
1984	Terms of Endearment
1985	Amadeus
1986	Out of Africa
1987	Platoon
1988	The Last Emperor
1989	Rain Man
1990	Driving Miss Daisy
1991	Dances With Wolves
1992	The Silence of the Lambs
1993	Unforgiven
1994	Schindler's List
1995	Forrest Gump
1996	Braveheart
1997	The English Patient
1998	Titanic
1999	Shakespeare in Love
2000	American Beauty
2001	Gladiator
2002	A Beautiful Mind
2003	Chicago
2004	The Lord of the Rings: The Return of the King
2005	Million Dollar Baby
2006	Crash
2007	The Departed
2008	No Country for Old Men
2009	Slumdog Millionaire
2010	The Hurt Locker
2011	The King's Speech
2012	The Artist
2013	Argo
2014	12 Years a Slave
2015	Birdman or (The Unexpected Virtue of Ignorance)
2016	Spotlight
2017	Moonlight
2018	The Shape of Water
2019	Green Book
2020	Parasite
2021	Nomadland
2022	CODA
2023	Everything Everywhere All at Once
2024	Oppenheimer

```sql
SELECT DISTINCT ano_cerimonia, nome filme FROM indicados_ao_oscar WHERE categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE') AND vencedor = TRUE ORDER BY ano_cerimonia;
```
 
**4.5** Quantos filmes diferentes já ganharam o Oscar?
R: 1328

```sql
SELECT COUNT(DISTINCT nome_filme) FROM indicados_ao_oscar WHERE vencedor = TRUE AND nome_filme IS NOT NULL;
```
 
---
 
## Nível 5: Análise de Indicações
 
**5.1** Quais atores/atrizes foram indicados mais de uma vez? Liste o nome e o número de indicações.
R:

```sql
SELECT nome_indicado, COUNT(*) AS total indicações FROM indicados_ao_oscar WHERE nome_indicado IS NOT NULL
GROUP BY nome indicado HAVING COUNT(*) > 1 ORDER BY total_indicacoes DESC;
```
 
**5.2** Qual ator ou atriz tem o maior número de indicações na história do Oscar?
R: Metro-Goldwyn-Mayer	64

```sql
SELECT nome_indicado, COUNT(*) AS total indicações FROM indicados_ao_oscar WHERE nome_indicado IS NOT NULL
GROUP BY nome indicado ORDER BY total_indicacoes DESC LIMIT 1;
```
 
**5.3** Quais atores foram indicados mais de 3 vezes, mas nunca ganharam?
R: Peter O'Toole	8
Richard Burton	7
Bradley Cooper	5
Arthur Kennedy	5
Albert Finney	5
Montgomery Clift	4
Warren Beatty	4
Charles Boyer	4
Ed Harris	4
Claude Rains	4
Mark Ruffalo	4
Mickey Rooney	4
Willem Dafoe	4

```sql
SELECT nome_indicado, COUNT(*) AS total indicações FROM indicados_ao_oscar WHERE categoria LIKE '%ACTOR%'
AND nome_indicado IS NOT NULL GROUP BY nome indicado HAVING COUNT(*) > 3 AND SUM(CASE WHEN vencedor = TRUE THEN 1 ELSE 0 END) = 0 ORDER BY total_indicacoes DESC;
```
 
**5.4** Encontre todos os artistas que foram indicados em categorias diferentes (ex: ator e diretor).
R:

```sql
SELECT nome_indicado, COUNT(DISTINCT categoria) AS total categorias FROM indicados_ao_oscar WHERE nome_indicado IS NOT NULL GROUP BY nome indicado HAVING COUNT(DISTINCT categoria) > 1 ORDER BY total_categorias DESC;
```
 
**5.5** Quantos indicados têm exatamente 1 indicação na história?
R: 5584

```sql
SELECT COUNT(*) FROM (
    SELECT nome_indicado
    FROM indicados_ao_oscar
    WHERE nome_indicado IS NOT NULL
    GROUP BY nome_indicado
    HAVING COUNT(*) = 1
) AS indicados_unicos;
```
 
**5.6** Qual o maior números de indicados em um único ano? Essa é uma pergunta franca.  
R: 1943	186

```sql
SELECT ano_cerimonia, COUNT(*) AS total indicações FROM indicados_ao_oscar GROUP BY ano_cerimonia
ORDER BY total_indicacoes DESC LIMIT 1;
```
 
---
 
## Nível 6: Análise de Filmes
 
### Toy Story
 
**6.1** A série de filmes Toy Story ganhou Oscars em quais anos?
R: 2011	Toy Story 3	ANIMATED FEATURE FILM
2011	Toy Story 3	MUSIC (Original Song)
2020	Toy Story 4	ANIMATED FEATURE FILM

```sql
SELECT DISTINCT ano_cerimonia, nome_filme, categoria FROM indicados_ao_oscar WHERE nome_filme LIKE '%Toy Story%'
AND vencedor = TRUE ORDER BY ano_cerimonia;
```
 
**6.2** Quantas indicações a franquia Toy Story recebeu no total?
R: 11

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_filme LIKE '%Toy Story%';
```
 
**6.3** Em quais categorias os filmes Toy Story foram indicados?
R: ANIMATED FEATURE FILM
BEST PICTURE
MUSIC (Original Musical or Comedy Score)
MUSIC (Original Song)
SOUND EDITING
WRITING (Adapted Screenplay)
WRITING (Screenplay Written Directly for the Screen)

```sql
SELECT DISTINCT categoria FROM indicados_ao_oscar WHERE nome_filme LIKE '%Toy Story%' ORDER BY categoria;
```
 
### Crash
 
**6.4** Em qual edição do Oscar o filme "Crash" concorreu?
R: 78

```sql
SELECT DISTINCT edicao_cerimonia FROM indicados_ao_oscar WHERE nome_filme = 'Crash';
```
 
**6.5** Quantas indicações o filme "Crash" recebeu?
R: 6

```sql
SELECT COUNT(*) FROM indicados_ao_oscar
WHERE nome_filme = 'Crash';
```
 
**6.6** "Crash" ganhou o Oscar de Melhor Filme?
R: Sim
2006	Crash	BEST PICTURE	1

```sql
SELECT ano_cerimonia, nome_filme, categoria, vencedor FROM indicados_ao_oscar WHERE nome_filme = 'Crash'
AND categoria IN ('OUTSTANDING PICTURE', 'BEST PICTURE');
```
 
### Central do Brasil
 
**6.7** O filme "Central do Brasil" aparece no banco de dados?
R: Não

```sql
SELECT DISTINCT nome_filme FROM indicados_ao_oscar WHERE nome_filme LIKE '%Central do Brasil%';
```
 
**6.8** Se sim, quantas indicações "Central do Brasil" recebeu?
R: 0

```sql
SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_filme LIKE '%Central do Brasil%';
```
 
