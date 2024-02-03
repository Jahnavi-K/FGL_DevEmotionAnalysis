"What Do Developers Feel About Fast-Growing Programming Languages? An Exploratory Study" is a mixed study conducted in year 2023. It quantitatively analyzes 1.8M comments from Issues, Commits and Pull Requests of top 10 repository for each language. The languages analyzed are HCL, TypeScript, Rust, Lua, Go, Shell, Makefile, C, Kotlin, Python, which are fast-growing these langauges have comparaatively seen increase in GitHUb community users compared to previous year.

ARTIFACTS:
Following describes the artifacts(Artifacts folder) mined and processed as part of ths study. Each fast-growing language has its artifacts in its own folder. In further lines, Language names will be represented by `<Language>` tag.


Inside each langauge folder:

* 10 Top starred repositories of the language are chosen from 1_TopRepos_`<Language>`.csv
* Issues, Commits, PullRequests folders have (In further lines, Issues, Commits, PullRequests will be reprseented by `<Artifact>` tag.):
  + `<Language>`_10.csv are the artifacts mined from top 10 Github repositories.
  + `<Language>`_`<Artifact>`_split.csv has only the comments column from `<Language>`_10.csv.
  + `<Language>`_`<Artifact>`_split.csv is the input file to ML model which produces `<Language>`_`<Artifact>`_RoBERTaAnnotated.csv.

RQ3 folder has artifacts used for RQ3 in the study "Do emotions evolve over various phases of the project?".

* Initial, Intermediary and Mature are the sub-folders which covers the respective phase of project.
* `<Language>`.csv is the input file to ML model which produces `<Language>`_RoBERTaAnnotated.csv.

CODE:
Following describes the scripts(Code folder) used to mine and analyze the data as part of ths study. In code scripts, replace <add_token_here> with your developer tokens. In further lines, Issues, Commits, PullRequests will be reprseented by `<Artifact>` tag.

1) 1_FetchLanguageTopRepos.ipynb is used to fetch top respsoitories for each language.
2) 2_`<Artifact>`_Scraper.ipynb is the script used to mine the respective artifact details from top GitHub respositories. To avoid pasue of fetch afterrate limit of a token completes, the script switches to next developer token. REST API exceptions are handled using github library.
3) 3_Retrain_emo_distilroberta.ipynb trains the ML model.
4) 4_Retrain_emo_distilroberta_inference.ipynb runs inferences using trained ML model

Additional Notes:

+ GitHub REST API is used to interact with GitHub. Refer official website for understanding codes. A good website to start with: https://www.softwaretestinghelp.com/github-rest-api-tutorial/
+ The fast-growing languages selected are as per GitHub yearly octoverse survey of year 2022.
