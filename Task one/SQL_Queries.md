**Return the artist with the most number of albums**

```
SELECT Artist.Name, COUNT(Album.AlbumId) AS AlbumCount
FROM Artist
JOIN Album ON Artist.ArtistId = Album.ArtistId
GROUP BY Artist.Name
ORDER BY AlbumCount DESC
LIMIT 1;
```

**Return the top three genres found in the dataset in descending order**

```
SELECT Genre.Name, COUNT(Track.TrackId) AS TrackCount
FROM Genre
JOIN Track ON Genre.GenreId = Track.GenreId
GROUP BY Genre.Name
ORDER BY TrackCount DESC
LIMIT 3;
```

**Return the number of tracks and average run time for each media type**

```
SELECT MediaType.Name, COUNT(Track.TrackId) AS TrackCount, AVG(Track.Milliseconds) AS AverageRunTime
FROM MediaType
JOIN Track ON MediaType.MediaTypeId = Track.MediaTypeId
GROUP BY MediaType.Name;
```
