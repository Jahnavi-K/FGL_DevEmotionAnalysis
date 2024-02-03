# FGL_DevEmotionAnalysis
What Do Developers Feel About Fast-Growing Programming Languages? An Exploratory Study. The corresponding paper has been accepted in ICPC'24, for further details on the dataset, methodology, and results, please refer https://doi.org/10.1145/3643916.3644422. 

# **FGL_DevEmotionAnalysis**

## **What Do Developers Feel About Fast-Growing Programming Languages? An Exploratory Study**

"What Do Developers Feel About Fast-Growing Programming Languages? An Exploratory Study" is a mixed study conducted in 2023. It quantitatively analyzes 1.8M comments from Issues, Commits, and Pull Requests of the top 10 repositories for each language. The languages analyzed are HCL, TypeScript, Rust, Lua, Go, Shell, Makefile, C, Kotlin, Python. These languages have seen a comparatively larger increase in GitHub community users compared to the previous year.

## **MODEL**
Trained model is available at [hugging face](https://huggingface.co/JahnaviKumar/FGL_DevEmotionAnalysis/tree/main)

## **ARTIFACTS**
Input, intermediate, output artifacts are available at [OSF](https://osf.io/g5xmw/?view_only=f7bd67ba59e54b4a98a77eef936421ec)

## **CODE**
This section describes the scripts (located in the `Code` folder) used to mine and analyze the data as part of this study. Replace `<add_token_here>` with your developer tokens. The term `<Artifact>` will represent Issues, Commits, Pull Requests.

- `1_FetchLanguageTopRepos.ipynb`: Fetches the top repositories for each language.
- `2_<Artifact>_Scraper.ipynb`: Scripts to mine details of the respective artifact from top GitHub repositories. To avoid pauses after the rate limit of a token is reached, the script switches to the next developer token. REST API exceptions are handled using the GitHub library.
- `3_Retrain_emo_distilroberta.ipynb`: Trains the ML model.
- `4_Retrain_emo_distilroberta_inference.ipynb`: Runs inferences using the trained ML model.

## **Additional Notes**
- GitHub REST API is used for interactions with GitHub. For code understanding, refer to the official website. A good starting point is [GitHub REST API Tutorial](https://www.softwaretestinghelp.com/github-rest-api-tutorial/).
- The fast-growing languages selected for this study are based on the GitHub yearly Octoverse survey of 2022.

