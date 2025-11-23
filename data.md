# MovieLens Dataset Documentation

## Summary

This dataset (ml-25m) describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service.

### Dataset Statistics

- **25,000,095** ratings
- **1,093,360** tag applications
- **62,423** movies
- **162,541** users
- **Date Range**: January 09, 1995 to November 21, 2019
- **Generated**: November 21, 2019

### User Selection Criteria

- Users were selected at random
- All selected users had rated at least 20 movies
- No demographic information is included
- Each user is represented by an ID only

## Files Included

- `genome-scores.csv` - Tag relevance scores for movies
- `genome-tags.csv` - Tag descriptions
- `links.csv` - External identifiers (IMDB, TMDB)
- `movies.csv` - Movie titles and genres
- `ratings.csv` - User ratings
- `tags.csv` - User-generated tags

## Usage License

### Conditions

- ✗ No endorsement may be stated or implied from the University of Minnesota or GroupLens Research Group
- ✓ Must acknowledge the dataset in publications
- ✗ May not redistribute the data without separate permission
- ✗ May not use for commercial or revenue-bearing purposes without permission
- ⚠ Software provided "as is" without warranty

### Citation

```
F. Maxwell Harper and Joseph A. Konstan. 2015.
The MovieLens Datasets: History and Context.
ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19.
https://doi.org/10.1145/2827872
```

## File Structures

### ratings.csv

Each line represents one rating of one movie by one user.

**Format**: `userId,movieId,rating,timestamp`

- **Ratings**: 5-star scale with half-star increments (0.5 - 5.0 stars)
- **Timestamps**: Seconds since midnight UTC, January 1, 1970
- **Ordering**: First by userId, then by movieId

### movies.csv

Each line represents one movie.

**Format**: `movieId,title,genres`

- **Titles**: Include year of release in parentheses
- **Source**: Manually entered or imported from [TheMovieDB](https://www.themoviedb.org/)
- **Genres**: Pipe-separated list

#### Available Genres

Action, Adventure, Animation, Children's, Comedy, Crime, Documentary, Drama, Fantasy, Film-Noir, Horror, Musical, Mystery, Romance, Sci-Fi, Thriller, War, Western, (no genres listed)

### tags.csv

Each line represents one tag applied to one movie by one user.

**Format**: `userId,movieId,tag,timestamp`

- **Tags**: User-generated metadata (typically single words or short phrases)
- **Timestamps**: Seconds since midnight UTC, January 1, 1970
- **Ordering**: First by userId, then by movieId

### links.csv

External identifiers for linking to other movie databases.

**Format**: `movieId,imdbId,tmdbId`

- **MovieLens**: https://movielens.org/movies/1
- **IMDB**: http://www.imdb.com/title/tt0114709/
- **TMDB**: https://www.themoviedb.org/movie/862

### Tag Genome (genome-scores.csv & genome-tags.csv)

A dense matrix containing tag relevance scores for movies, encoding how strongly movies exhibit particular properties.

**genome-scores.csv Format**: `movieId,tagId,relevance`

**genome-tags.csv Format**: `tagId,tag`

#### Tag Genome Citation

```
Jesse Vig, Shilad Sen, and John Riedl. 2012.
The Tag Genome: Encoding Community Knowledge to Support Novel Interaction.
ACM Trans. Interact. Intell. Syst. 2, 3: 13:1–13:44.
https://doi.org/10.1145/2362394.2362395
```

## Data Format

- **Encoding**: UTF-8
- **Format**: Comma-separated values (CSV) with single header row
- **Escaping**: Columns containing commas are escaped using double-quotes (`"`)

## About GroupLens

GroupLens is a research group in the Department of Computer Science and Engineering at the University of Minnesota (since 1992).

### Research Areas

- Recommender systems
- Online communities
- Mobile and ubiquitous technologies
- Digital libraries
- Local geographic information systems

### Contact

- **Website**: http://movielens.org
- **Email**: grouplens-info@umn.edu
- **Dataset Download**: http://grouplens.org/datasets/

## Verifying Dataset Integrity

Use MD5 checksum to verify dataset authenticity:

```bash
# Linux
md5sum ml-25m.zip; cat ml-25m.zip.md5

# macOS
md5 ml-25m.zip; cat ml-25m.zip.md5
```

Check that both hash values match.

## Additional Resources

For cross-validation and evaluation tools, see [LensKit](http://lenskit.org) for documentation and open-source code examples.
