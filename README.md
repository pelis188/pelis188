<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Movie App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Movie App</h1>
    <div id="movies"></div>
    <script src="app.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    text-align: center;
}

#movies {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.movie {
    background: white;
    margin: 10px;
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 200px;
}

.movie img {
    width: 100%;
    border-radius: 5px;
}
document.addEventListener('DOMContentLoaded', () => {
    const moviesDiv = document.getElementById('movies');

    fetch('https://api.themoviedb.org/3/movie/popular?api_key=TU_API_KEY')
        .then(response => response.json())
        .then(data => {
            data.results.forEach(movie => {
                const movieElement = document.createElement('div');
                movieElement.classList.add('movie');
                movieElement.innerHTML = `
                    <img src="https://image.tmdb.org/t/p/w500${movie.poster_path}" alt="${movie.title}">
                    <h3>${movie.title}</h3>
                    <p>${movie.overview}</p>
                `;
                moviesDiv.appendChild(movieElement);
            });
        })
        .catch(error => console.error('Error fetching movies:', error));
});
document.addEventListener('DOMContentLoaded', () => {
    const moviesDiv = document.getElementById('movies');

    fetch('https://api.themoviedb.org/3/movie/popular?api_key=TU_API_KEY')
        .then(response => response.json())
        .then(data => {
            data.results.forEach(movie => {
                const movieElement = document.createElement('div');
                movieElement.classList.add('movie');
                movieElement.innerHTML = `
                    <img src="https://image.tmdb.org/t/p/w500${movie.poster_path}" alt="${movie.title}">
                    <h3>${movie.title}</h3>
                    <p>${movie.overview}</p>
                `;
                moviesDiv.appendChild(movieElement);
            });
        })
        .catch(error => console.error('Error fetching movies:', error));
});
