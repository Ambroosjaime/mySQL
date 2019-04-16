# mySQL


drill 1
    1. only cities
	SELECT * FROM `weather`

    2. all cities and their maximum temperature
       SELECT city, high FROM weather

    3. all cities and their minimum temperature
       SELECT city, low FROM weather

    4. Where cities whose maximum temperature exceeds 27 degrees
       SELECT city FROM weather WHERE High >= 27

    5. Where cities whose minimum temperature will be less than or equal to 15 degrees
       select city from weather where Low  <= 15

    6. Where cities with a minimum temperature of 15 degrees
	select city from weather where Low = 15

    7. Where cities whose minimum temperature will NOT be equal to 15 degrees
       select city from weather where Low <> 15

    8. Where cities whose name begins with "Br"
       select city from weather where city like 'br%'

    9. Where cities with a maximum temperature between 26 and 28 degrees
       select City from weather where High between 26 and 28

    10. Where cities with a minimum temperature of 14 or 16 degrees

       select City from weather where Low =  14 or Low= 16 
    11. Where cities with a maximum temperature of 26 or higher and a minimum temperature of less than 14
	select City from weather where High >= 26 or Low <= 14


Drill 2


Familiarize yourself first with this table. What does it contain? what are the columns? Then, same principle as above:
    • Find the syntax to perform each of the following queries:*

    1. Displays all weather and their data
       SELECT * FROM octocats

    2. Shows only the first names
       SELECT FirstName FROM octocats

    3. Display the first names, names and ages of each octocat
        SELECT FirstName, LastName, age FROM octocats

    4. Shows octocats whose name starts with 'N'
       SELECT FirstName, Age FROM octocats WHERE LastName LIKE 'n%'

    5. Display the first and last name of the octocats of promo promo-central
       SELECT firstname,lastname FROM octocats WHERE promo = 'promo1-central’

    6. Display the first name, last name and year of birth of the octocats of the promo "promo1-anderlecht"
       SELECT firstname,lastname,birthdate FROM octocats WHERE promo = 'promo1-anderlecht'

Drill 3

	1.Geef de voor- en achternaam van alle octocats weer, in oplopende 	alfabetische volgorde van de voornaam.

       		Select FirstName, LastName from octocats order by LastName desc

       2.Geef de voor- en achternaam van alle octocats weer, in aflopende alfabetische volgorde van de achternaam.

       		Select FirstName, LastName from octocats order by FirstName asc

       3.Geef de voornaam, achternaam en leeftijd van alle octocats weer, van de jongste tot de oudste.

      		 Select FirstName, LastName from octocats order by age asc

       4.Geef de voornaam, achternaam en leeftijd van alle octocats weer, van de oudste tot de jongste.

       		Select FirstName, LastName from octocats order by age desc

       5.Toon de voornaam, achternaam en leeftijd van alle octocats, van de jongste tot de oudste, van de promo1-centrale promo.

       		select FirstName, LastName, Age FROM octocats WHERE Promo = 'promo-central' ORDER BY Age ASC

       6.Toon de voornaam, achternaam en leeftijd van alle octocats, van de jongste tot de oudste, van de promo 1-centrale promo, waarvan de 		leeftijd tussen 23 en 28 ligt.

       		select FirstName, LastName, Age from octocats where Promo = 'promo-central' between 23 and 28 order by age asc

       7.Geeft de voornaam, achternaam, leeftijd en het geslacht van alle octocats weer, van de jongste tot de oudste, van de promo 1-centrale 		promo en tussen 25 en 35 jaar oud.

		select FirstName, LastName, Age from octocats where Promo = 'promo-central' and Age between 25 and 35 order by Age asc

       8.Geeft de voornaam, achternaam, leeftijd en het geslacht van alle octocats weer, van de jongste tot de oudste, van de promo 1-centrale 		promo, die tussen 25 en 35 jaar oud is en waarvan het geslacht mannelijk is.

       		select FirstName, LastName, Age, Sex FROM octocats WHERE Promo = 'promo-central' and Sex like 'M%' and Age between 25 and 35 			order by Age ASC

       9.Geef de voornaam, achternaam, leeftijd van de oudste octocate van Becode / Central weer.Je moet dus een tabel met een enkele rij 		krijgen.

		select FirstName, LastName, Max (Age) as Age from octocats where Promo = 'promo-central'

Drill 4

    1. How many boys are there in Becode?
       select count (*) from octocats where Sex = 'M'

    2. How many girls are there in Becode / Central?
       select count (*) from octocats where Sex = 'F'

    3. How many boys are there in Becode / Central?
       select count(*) from octocats where Sex = 'M' and Promo = 'promo-central'

    4. How many octocats are there whose first name is 'Nadia' at becode?
       select count(*) from octocats where FirstName ='Nadia'

    5. On this new SQLFiddle, finds the function to display only the year of the "birthdate" column and displays the first name of all octocts 		and their year of birth. (hint: how do you say "year" in English?)
	select extract (year From birtdate), FirstName from octocats
       

