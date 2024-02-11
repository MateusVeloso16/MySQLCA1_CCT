CREATE database IF NOT EXISTS ireflix;

USE ireflix;

CREATE TABLE Users (
	Username_user VARCHAR(35),
    Name_user VARCHAR(35),
    Surname_user VARCHAR(35),
    Password_user VARCHAR(15)
);

CREATE TABLE Movies (
	Movie_id INT(6),
    Name_of_the_movie CHAR(35),
    Genre CHAR(20),
    Duration_movie INT(3),
    Qualification_from_users INT(1),
    Protagonist_actor VARCHAR(35)
);

CREATE TABLE Series (
	Serie_id INT(6),
    Genre CHAR(20),
    User_qualification INT(1),
    Protagonist_name VARCHAR(35),
    Protagonist_surname VARCHAR(35),
    Number_of_seasons INT(3)
);

CREATE TABLE Actors (
	Actors_name VARCHAR(35),
    Actors_surname VARCHAR(35),
    Actors_nationality CHAR(20)
);

CREATE TABLE Directors (
	Directors_name VARCHAR(35),
    Directors_surname VARCHAR(35),
    Directors_nationality CHAR(20)
);
    
CREATE TABLE Users_activity_movies (
	Username_movie VARCHAR(35),
	Id_of_the_movie VARCHAR(35),
	Genre_of_the_movie CHAR(20)
);
        
CREATE TABLE Users_activity_series (
	Username_serie VARCHAR(35),
	Id_of_the_serie VARCHAR(35),
	Genre_of_the_serie CHAR(20)
);


USE ireflix;

INSERT INTO Users (Username_user, Name_user, Surname_user, Password_user) 
VALUES 
('ShadowFlame', 'Olivia', 'Richardson', 'R3bT9mN6'),
('CrystalDawn', 'Logan', 'Lewis', 'K6vH3nM9'),
('SunfirePhoenix', 'Sophia', 'Watson', 'V9bS3nR7'),
('WhisperingWillow', 'Noah', 'Thompson', 'J8vR3mS6'),
('MidnightStalker', 'Mia', 'Morales', 'T9vM3bN7');

INSERT INTO movies (Movie_id, Name_of_the_movie, Genre, Duration_movie, Qualification_from_users, Protagonist_actor) 
VALUES 
(1, 'The Lost Treasure', 'Adventure', 120, 4, 'John Smith'),
(2, 'Midnight Mystery', 'Thriller', 105, 3, 'Emily Johnson'),
(3, 'Space Odyssey', 'Sci-Fi', 150, 5, 'Mark Roberts'),
(4, 'Love in Paris', 'Romance', 90, 4, 'Sophia Lee'),
(5, 'The Dark Forest', 'Horror', 110, 3, 'Jack Thompson');

INSERT INTO Series (Serie_id, Genre, User_qualification, Protagonist_name, Protagonist_surname, Number_of_seasons) 
VALUES 
(1, 'Drama', 4, 'Sarah', 'Johnson', 5),
(2, 'Comedy', 3, 'Michael', 'Smith', 8),
(3, 'Thriller', 5, 'Emily', 'Jones', 4),
(4, 'Sci-Fi', 4, 'David', 'Brown', 6),
(5, 'Crime', 4, 'Sophia', 'Davis', 3);

INSERT INTO Actors (Actors_name, Actors_surname, Actors_nationality) 
VALUES 
('Emma', 'Watson', 'British'),
('Ryan', 'Reynolds', 'Canadian'),
('Lupita', 'Nyong\'o', 'Kenyan'),
('Pedro', 'Pascal', 'Chilean'),
('Zendaya', 'Coleman', 'American');

INSERT INTO Directors (Directors_name, Directors_surname, Directors_nationality) 
VALUES 
('Christopher', 'Nolan', 'British'),
('Ava', 'DuVernay', 'American'),
('Bong', 'Joon-ho', 'South Korean'),
('Greta', 'Gerwig', 'American'),
('Denis', 'Villeneuve', 'Canadian');

INSERT INTO Users_activity_movies (Username_movie, Id_of_the_movie, Genre_of_the_movie) 
VALUES 
('moviebuff123', 'tt4154796', 'Action'),
('cinemafanatic', 'tt7286456', 'Drama'),
('filmlover22', 'tt6751668', 'Comedy'),
('moviemaniac99', 'tt8579674', 'Thriller'),
('hollywoodfan', 'tt4154664', 'Sci-Fi');

INSERT INTO Users_activity_series (Username_serie, Id_of_the_serie, Genre_of_the_serie) 
VALUES 
('serieslover123', 'tt0944947', 'Fantasy'),
('bingewatcher22', 'tt1520211', 'Crime'),
('tvaddict99', 'tt4574334', 'Drama'),
('netflixjunkie', 'tt6468322', 'Comedy'),
('showtimefanatic', 'tt1831164', 'Mystery');

ALTER TABLE directors CHANGE COLUMN Directors_nationality Nationality CHAR(20);
ALTER TABLE actors CHANGE COLUMN Actors_nationality Nationality CHAR(20);
ALTER TABLE actors CHANGE COLUMN Actors_name Name VARCHAR(35);
ALTER TABLE directors CHANGE COLUMN Directors_name Name VARCHAR(35);
ALTER TABLE actors CHANGE COLUMN Actors_surname Surname VARCHAR(35);
ALTER TABLE directors CHANGE COLUMN Directors_surname Surname VARCHAR(35);
ALTER TABLE series CHANGE COLUMN User_qualification Qualification_from_users INT(1);

