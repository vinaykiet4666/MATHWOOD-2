# MATHWOOD-2
🎬 MathsWood --- Movie Recommender Mini System
Math + Cinema: A cinematic web-based movie recommender that demonstrates how Singular Value Decomposition (SVD) can uncover hidden preference patterns and predict unrated movies.
✨ Overview
MathsWood --- Movie Recommender Mini System is an interactive single-page website built to demonstrate a mathematical movie-recommendation workflow using Singular Value Decomposition.
The project starts with a small 5-user × 8-movie rating matrix. Ratings are on a 1--5 scale, while 0 represents an unrated movie. The SVD model estimates the missing ratings and recommends the highest-scoring unrated movie for each user.
The website combines the mathematical explanation with a cinematic interface so that users can explore both the recommendation result and the mathematics behind it.
🎯 Project Goals
Demonstrate SVD in a practical recommendation-system example.
Explain the recommendation pipeline in an easy-to-follow visual format.
Show how missing ratings can be estimated from hidden preference patterns.
Connect matrix decomposition concepts with a real-world application.
Provide an interactive movie catalogue and recommendation experience.
🧠 How the Recommendation Works
The core mathematical model is:
A = UΣVᵀ
The implementation uses a rank-2 approximation, keeping the two strongest singular-value components.
Pipeline
Rating Matrix
     ↓
Fill missing values with each user's mean rating
     ↓
Find strongest singular direction
     ↓
Deflate the matrix
     ↓
Find the second strongest direction
     ↓
Reconstruct a rank-2 approximation
     ↓
Estimate unrated movies
     ↓
Recommend the highest predicted unrated movie
1. Input matrix
The project contains:
5 users
8 movies
40 total cells
29 existing ratings
11 unrated cells
A value of 0 means that the user has not rated that movie.
2. Mean filling
SVD needs a complete matrix, so each user's unrated cells are temporarily filled using that user's average existing rating.
3. Power iteration
The project finds the strongest singular component using power iteration.
The implementation repeats the matrix-vector update and normalization process for 200 iterations.
4. Deflation
After finding one singular component, its contribution is subtracted from the matrix. The process is repeated to obtain the second strongest component.
5. Rank-2 reconstruction
The two strongest components are combined to form the approximation:
A₂ = U₂Σ₂V₂ᵀ
This reconstructed matrix provides estimated ratings for movies that a user has not rated.
6. Recommendation
For a user, the system checks only the unrated movies and selects the one with the highest predicted rating.
The prediction is bounded to the 1--5 rating range and also displayed as a percentage-style score.
🎞️ Movies Included
The built-in movie catalogue contains:
Movie                           Year Category
Baahubali 2: The Conclusion     2017 Epic Action Magadheera                      2009 Fantasy Action RRR                             2022 Period Action Sita Ramam                      2022 Period Romance Arjun Reddy                     2017 Romantic Drama Eega                            2012 Fantasy Comedy Pushpa: The Rise                2021 Crime Action Ala Vaikunthapurramuloo         2020 Family Musical
🖥️ Website Features
Rating Matrix
Displays the 5 × 8 user--movie rating matrix and clearly distinguishes actual ratings from unrated cells.
SVD Explanation
A visual four-step explanation:
Decompose
Reduce
Reconstruct
Recommend
SVD Deep Dive
Explains the mathematical process, including:
The recommendation problem
SVD decomposition
Mean filling
Power iteration
Matrix deflation
Rank-2 reconstruction
Singular-value contribution
Reading the predicted result
Limitations and possible upgrades
Interactive Movie Details
Clicking a movie opens a detailed view containing information such as:
Story
Movie type
Cast
Director
Music
Runtime
Language
Average rating from the project data
User rating/prediction bars
SVD taste-layer values
Similar movies based on the model's taste representation
Personalized Recommendation
The recommendation section uses the SVD reconstruction to select the highest predicted unrated movie.
Light / Dark Theme
The interface supports both light and dark themes. The selected theme is stored in browser localStorage.
Reviews
Users can submit a star rating and written review. Reviews are stored locally in the browser using localStorage.
🛠️ Technologies Used
HTML5 --- page structure
CSS3 --- responsive layout, animations, themes, glass/cinematic styling
Vanilla JavaScript --- UI interactions and SVD/recommendation logic
Math / Linear Algebra --- SVD, singular values, vectors, low-rank approximation
Browser localStorage --- theme preference and reviews
Google Fonts (Inter) --- interface typography
No frontend framework or backend server is required.
📁 Project Structure
The project is designed as a self-contained single-page application:
movie-recommender/
└── index.html
The HTML file contains the page structure, styling, movie data, SVD implementation, recommendation logic, interactions, and review functionality.
🚀 How to Run
Option 1 --- Open directly
Download or copy the project HTML file.
Rename it to:
index.html
Open index.html in a modern web browser.
Option 2 --- Use VS Code
Open the project folder in VS Code.
Open index.html.
Use a browser or a Live Server extension to run the page.
No build process or package installation is required.
📊 Mathematical Core
The implementation uses a small custom SVD-style decomposition rather than relying on a machine-learning library.
Conceptually:
A ≈ U₂Σ₂V₂ᵀ
where:
A = original rating matrix
U₂ = user-side latent factors
Σ₂ = two strongest singular values
V₂ᵀ = movie-side latent factors
A₂ = rank-2 approximation
The project therefore demonstrates the connection between:
Linear Algebra
      ↓
Matrix Decomposition
      ↓
Latent Preference Patterns
      ↓
Predicted Ratings
      ↓
Movie Recommendation
⚠️ Limitations
This is an educational mini-system rather than a production-scale recommendation engine.
The dataset is intentionally very small.
The movie catalogue contains only eight movies.
The model uses a fixed rank of k = 2.
Missing values are filled using each user's mean rating.
The implementation is designed for demonstration and learning.
There is no backend database or multi-user persistence.
Reviews are stored locally in the browser.
A real recommendation platform would require a much larger dataset and more advanced evaluation/recommendation techniques.
🔮 Possible Future Improvements
Add a larger movie-rating dataset.
Allow users to enter their own ratings.
Add dynamic matrix creation.
Experiment with different values of k.
Add recommendation accuracy metrics.
Compare SVD with other recommendation approaches.
Add user accounts and a backend database.
Add real-time movie/poster APIs.
Add search and filtering.
Add recommendation history.
Deploy the project as a public web application.
🎓 Educational Value
This project is especially useful for demonstrating how a BTech-level linear algebra concept can be connected to a practical computing application.
Instead of treating SVD only as a matrix formula, the project shows how singular values and latent factors can be used to identify hidden patterns in user preferences and estimate unknown ratings.
👨‍💻 Project
MathsWood --- Movie Recommender Mini System
Core topic: Singular Value Decomposition (SVD)
Application: Movie Recommendation System
Implementation: HTML + CSS + Vanilla JavaScript
A small matrix. Hidden patterns. One next movie.