# SQL-Notes-and-Examples
Video Link : [crash course by Web Dev Simplified ](https://youtu.be/p3qvj9hO_Bo)

Practice Workbook : [Practice Now ](https://github.com/WebDevSimplified/Learn-SQL)


### DB Commands :
- **CREATE** DATABASE *TESTING* ;
- **USE**  *TESTING* ;
- **DROP** DATABASE *TESTING* ;

### TABLE Commands :
- **CREATE** TABLE test (
 test_column INT
 );
 - **ALTER** TABLE test **ADD** another_column VARCHAR(255) ;
 - **DROP** TABLE test ;

### COLUMN Commands :

- CREATE TABLE
```
CREATE TABLE bands (
  id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL 
);
```

- FOREIGN KEY 
```
CREATE TABLE bands (
  id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL 
);

CREATE TABLE albums (
  id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  band_id INT NOT NULL,
  FOREIGN KEY (band_id) REFERENCES bands(id)
);

```

### ROW Commands :

- **INSERT** 
```
INSERT INTO bands (name) VALUES ('steve');
INSERT INTO bands (name) VALUES ('rog'), ('sweet');
```
- **DELETE** 
```
DELETE from bands WHERE name = 'sour';
```

- **SELECT** 
```
SELECT * FROM bands;
SELECT * FROM bands LIMIT 2; # limiting first 2 outputs
SELECT name FROM bands;
```

- **AS / ALIAS**
```
SELECT id as ID FROM bands; # displays id as ID
```

- **ORDER BY**
```
SELECT * FROM bands ORDER BY name; # Ascending Order
SELECT * FROM bands ORDER BY name DESC; # Descending Order
```

- **ONLY UNIQUE ROWS**
```
SELECT DISTINCT name FROM bands; # returns only unique rows
```

- **UPDATE**
```
UPDATE bands 
SET name = 'sour' 
WHERE name = 'sweet';
```

- **WHERE** 
```
SELECT * FROM albums 
WHERE year < 2000;
```

- **LIKE** 
```
SELECT * from bands WHERE name LIKE '%er%'
```

- **OR** 
```
SELECT * from bands WHERE name LIKE '%er%' OR name = 'sour'
```

- **AND** 
```
SELECT * from bands WHERE name LIKE '%er%' AND name = 'sour'
```

- **BETWEEN**
```
SELECT * from bands WHERE year BETWEEN 2000 AND name = 2010
```

- **IS** 
```
SELECT * from bands WHERE year IS NULL;
```

- **INNER JOIN / JOIN**
```
SELECT * from bands JOIN albums ON bands.id = albums.band_id ;

SELECT * from bands INNER JOIN albums ON bands.id = albums.band_id ;
```

- **LEFT JOIN** 
```
SELECT * from bands LEFT JOIN albums ON bands.id = albums.band_id ; 

# Joins the right one to the left one , it will list all of the Left side even it doesn't have a match on the right.
```

- **RIGHT JOIN** 
```
SELECT * from bands RIGHT JOIN albums ON bands.id = albums.band_id ; 

# Joins the left one to the right one , it will list all of the Right side even it doesn't have a match on the left.
```

- **AGGREGATE FUNCTIONS**
```
SELECT AVG(release_year) FROM albums;

SELECT SUM(release_year) FROM albums;
```

- **COUNT and GROUP BY**
```
SELECT band_id COUNT(band_id) from albums
GROUP BY band_id
```

- **HAVING**
```
SELECT band_id COUNT(band_id) from albums
GROUP BY band_id HAVING band_id = '1';
```

