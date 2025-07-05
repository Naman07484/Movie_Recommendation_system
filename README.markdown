# Movie Recommendation System

## Project Overview

This project implements a **Movie Recommendation System** using Python in a Jupyter Notebook environment. The system recommends movies based on user input by leveraging content-based filtering. It analyzes movie attributes such as genres, keywords, tagline, cast, and director to suggest similar movies using cosine similarity.

## Dataset

The project uses the `movies.csv` dataset, which contains details about 4,803 movies, including:

- **Columns**: `index`, `budget`, `genres`, `homepage`, `id`, `keywords`, `original_language`, `original_title`, `overview`, `popularity`, `runtime`, `spoken_languages`, `status`, `tagline`, `title`, `vote_average`, `vote_count`, `cast`, `crew`, `director`, and more.
- **Source**: The dataset is assumed to be available in the project directory as `movies.csv`.

## Features

- **Input**: Users provide a movie title.
- **Processing**: The system finds the closest matching movie title using `difflib` and computes similarity scores based on selected features (`genres`, `keywords`, `tagline`, `cast`, `director`).
- **Output**: Returns a list of up to 29 recommended movies similar to the input, ranked by cosine similarity.

## Dependencies

The project requires the following Python libraries:

- `numpy`
- `pandas`
- `scikit-learn` (for `TfidfVectorizer` and `cosine_similarity`)
- `difflib`

Install the dependencies using:

```bash
pip install numpy pandas scikit-learn
```

## How It Works

1. **Data Loading**: The dataset (`movies.csv`) is loaded into a pandas DataFrame.
2. **Preprocessing**:
   - Selected features (`genres`, `keywords`, `tagline`, `cast`, `director`) are cleaned by replacing null values with empty strings.
   - Features are combined into a single text column for each movie.
3. **Feature Extraction**: Text data is converted to numerical feature vectors using `TfidfVectorizer`.
4. **Similarity Computation**: Cosine similarity is calculated between all movies based on feature vectors.
5. **Recommendation**:
   - The user inputs a movie title.
   - The closest matching title is found using `difflib.get_close_matches`.
   - Movies are ranked by similarity score, and the top 29 are displayed.

## Usage

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```
2. Ensure `movies.csv` is in the project directory.
3. Open the `Movie_recommendation_project.ipynb` in Jupyter Notebook:

   ```bash
   jupyter notebook Movie_recommendation_project.ipynb
   ```
4. Run all cells in the notebook.
5. Enter a movie title when prompted to receive recommendations.

## Example

**Input**: `avatar`\
**Output**:

```
Movies suggested for you :
1. Avatar
2. Alien
3. Aliens
4. Guardians of the Galaxy
...
29. Wing Commander
```

## File Structure

- `Movie_recommendation_project.ipynb`: Jupyter Notebook containing the recommendation system code.
- `movies.csv`: Dataset file 
- `README.md`: This file, providing an overview and instructions.

## Future Improvements

- Incorporate additional features like `overview` or `vote_average` for enhanced recommendations.
- Implement a user interface for easier interaction.
- Add collaborative filtering to include user preferences or ratings.