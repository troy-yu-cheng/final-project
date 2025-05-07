# Intro2DS Final Proj: Crime Prediction in Washington DC

*Author: Troy Cheng, Ziqiao Shan, Minji Kang, Sarah Krause*

## Project Description

Using DC Open Data crime incidents (2008–2025) enriched with spatial features (liquor license moratorium zones, locations and proximity of liquor stores, grocery stores, and banks, public WiFi zones and vending zones, low food access areas, police sector boundaries and military base zones) and tract-level socioeconomic indicators from the ACS5, we build three different types of models to predict 

1) the likelihood of a crime being a felony (binary classification); 

2) which felony category a crime falls under (multi-classification); 

3) what felony severity score of a crime new reported in DC would be (regression task). 

We train and test on 2019–2022 data, implement on 2023, and the final merged dataset (crime_enriched_acs_nona.csv) is available via qmd file. 

**Note: Make sure you installed and loaded all the packadges in [Dependencies](https://github.com/troy-yu-cheng/final-project?tab=readme-ov-file#dependencies) before you run the code in index.qmd file.**

## Pull Request Workflow Quick Reference

### 1. Start a New Branch

- Move to the `main` branch:

  ```bash
  git checkout main
  ```

- Pull the latest changes:

  ```bash
  git pull origin main
  ```

- Create a new branch for your work:

  ```bash
  git checkout -b <your-branch-name>
  ```

eg. I can create a branch named `troy` by `git chechout -b troy`.

### 2. Do Your Work

- Edit, add, or delete files as needed.
- Save your changes:

  ```bash
  git add <the name of the modified file on your machine>
  git commit -m "Describe what you changed"
  ```

eg. I modified README.md file. I need use code `git add README.md`, `git commit -m "update README"`.

### 3. Push Your Branch

- Push your branch to GitHub:

  ```bash
  git push origin your-branch-name
  ```

eg. After add and commit, I push changes to branch `troy` using `git push origin troy`. 

### 4. Create a Pull Request

- Go to GitHub.
- GitHub will suggest creating a Pull Request (PR), or click `Pull requests` button which is in the same line of the `Code` button and then click `New pull request`.
- Set the `base` button as `main` branch and set the `compare` button as `<your-branch-name>` branch. Usually, you will see `√ Able to merge`.  
- Click the green button **"Create Pull Request."**  
- Write a simple title and short description.
- Submit your PR for review by clicking `Create pull request`.
- Review the PR to check if there's any code conflict.
- If there is no conflict:
  - GitHub will show a green message saying "This branch has no conflicts with the base branch."
  - You can directly click the `Merge pull request` button.
  - After that, click `Confirm merge` to complete the pull request.
  - After merging, GitHub will suggest `Delete branch`. Click it to delete the feature branch from GitHub.

- If there is a conflict:
  - GitHub will show a message saying "This branch has conflicts that must be resolved."
  - Click "Resolve conflicts" on the GitHub page.
  - You will see the files with conflicts. GitHub will show the conflicting parts like this:
    ```text
    <<<<<<< main
    (the code from the main branch)
    =======
    (the code from your branch)
    >>>>>>> your-branch-name
    ```
  - Choose which code you want to keep. You can keep the version from `main`, your version, or a mix of both.
  - Delete the `<<<<<<<`, `=======`, and `>>>>>>>` conflict markers after you fix the code.
  - After fixing, click "Mark as resolved" on GitHub.
  - Then click "Commit merge."
- After all conflicts are resolved and merged, the PR can be approved and completed.


### 5. After Your PR is Merged

- Switch back to the `main` branch:

  ```bash
  git checkout main
  ```

- Pull the latest version of `main`:

  ```bash
  git pull origin main
  ```

### 6. Clean Up Your Old Branch

- After the PR is merged, delete your local branch:

  ```bash
  git branch -d your-branch-name
  ```

eg. I need to use `git branch -d troy` to delete the branch I created.

- (If you see an error, use force delete:)

  ```bash
  git branch -D your-branch-name
  ```

---

### Important Notes

- **Never** work directly on the `main` branch.
- **Always** start a new branch for each feature or fix.
- **Always** pull the latest `main` before starting new work.
- **Don't** delete your branch until the PR is fully merged.

---

## Dependencies
- R (>= 4.0.0)
- Packages:
  - tidyverse
  - readr
  - haven
  - lubridate
  - tidymodels
  - tidycensus
  - janitor
  - sf
  - plotly
  - themis
  - vip
  - ranger
  - xgboost
  - rlang

## Data Sources

### Crime Incidents (2008–2025)
- [Crime Incident 2025 - DC Open Data](https://opendata.dc.gov/datasets/74d924ddc3374e3b977e6f002478cb9b_7/explore)
- [Crime Incident 2024 - DC Open Data](https://opendata.dc.gov/datasets/c5a9f33ffca546babbd91de1969e742d_6/explore)
- [Crime Incident 2023 - DC Open Data](https://opendata.dc.gov/datasets/89561a4f02ba46cca3c42333425d1b87_5/explore)
- [Crime Incident 2022 - DC Open Data](https://opendata.dc.gov/datasets/f9cc541fc8c04106a05a1a4f1e7e813c_4/explore)
- [Crime Incident 2021 - DC Open Data](https://opendata.dc.gov/datasets/619c5bd17ca2411db0689bb0a211783c_3/explore)
- [Crime Incident 2020 - DC Open Data](https://opendata.dc.gov/datasets/f516e0dd7b614b088ad781b0c4002331_2/explore)
- [Crime Incident 2019 - DC Open Data](https://opendata.dc.gov/datasets/f08294e5286141c293e9202fcd3e8b57_1/explore)
- [Crime Incident 2018 - DC Open Data](https://opendata.dc.gov/datasets/38ba41dd74354563bce28a359b59324e_0/explore)
- [Crime Incident 2017 - DC Open Data](https://opendata.dc.gov/datasets/crime-incidents-in-2017/explore)
- [Crime Incident 2016 - DC Open Data](https://opendata.dc.gov/datasets/bda20763840448b58f8383bae800a843_26/explore)
- [Crime Incident 2015 - DC Open Data](https://opendata.dc.gov/datasets/35034fcb3b36499c84c94c069ab1a966_27/explore)
- [Crime Incident 2014 - DC Open Data](https://opendata.dc.gov/datasets/6eaf3e9713de44d3aa103622d51053b5_9/explore)
- [Crime Incident 2013 - DC Open Data](https://opendata.dc.gov/datasets/5fa2e43557f7484d89aac9e1e76158c9_10/explore)
- [Crime Incident 2012 - DC Open Data](https://opendata.dc.gov/datasets/010ac88c55b1409bb67c9270c8fc18b5_11/explore)
- [Crime Incident 2011 - DC Open Data](https://opendata.dc.gov/datasets/9d5485ffae914c5f97047a7dd86e115b_35/explore)
- [Crime Incident 2010 - DC Open Data](https://opendata.dc.gov/datasets/fdacfbdda7654e06a161352247d3a2f0_34/explore)
- [Crime Incident 2009 - DC Open Data](https://opendata.dc.gov/datasets/73cd2f2858714cd1a7e2859f8e6e4de4_33/explore)
- [Crime Incident 2008 - DC Open Data](https://opendata.dc.gov/datasets/180d56a1551c4e76ac2175e63dc0dce9_32/explore)

### GIS features of Interest
- [Grocery Store Locations - DC Open Data](https://opendata.dc.gov/datasets/1d7c9d0e3aac49c1aa88d377a3bae430_4/explore)
- [Bank Location - DC Open Data](https://opendata.dc.gov/datasets/dfc51a5bd29347d0a2399743d3144d31_0/explore)
- [Alcohol License Businesses Locations- DC Open Data](https://opendata.dc.gov/datasets/cabe9dcef0b344518c7fae1a3def7de1_5/explore)
- [Alcohol License Moratorium Zones - DC Open Data](https://opendata.dc.gov/datasets/1092394719a44d72af2c9b6ddb269551_35/explore)
- [Low Food Access Zones- DC Open Data](https://opendata.dc.gov/datasets/9b4355a8e1e345ea8350b77516163dd4_61/explore)
- [Military Bases - DC Open Data](https://opendata.dc.gov/datasets/21ee426eddc14014b80535cd6b8316e7_11/explore)
- [Police Sectors- - DC Open Data](https://opendata.dc.gov/datasets/6ac17c2ff8cc4e20b3768dd1b98adf7a_23/explore)
- [Street Vending Zones - DC Open Data](https://opendata.dc.gov/datasets/e05b93650d0a47ab846db46d2ba08b05_159/explore)
- [Free WiFi Zones - DC Open Data](https://opendata.dc.gov/datasets/0a73011064ae4580a4a8539de03060d1_14/explore)

### ACS5 Data
- [American Community Survey 5-Year Data (2009-2023)](https://www.census.gov/data/developers/data-sets/acs-5year.html)

### DC Tract Boundaries
- [DC Census Tract Shapefiles (TIGER/Line 2023) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2023/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2020) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2020/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2019) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2019/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2018) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2018/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2017) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2017/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2016) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2016/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2015) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2015/TRACT/)
- [DC Census Tract Shapefiles (TIGER/Line 2010) - U.S. Census](https://www2.census.gov/geo/tiger/TIGER2010/TRACT/2010/)


## Comments

*by Prof. Alena Stern*

Nice work on the proposal! The topic meets the basic project requirements of articulating a policy-relevant question and using at least three of the data science tools covered in this class (listed in the assignment) - so I think you should feel free to move ahead!

Your proposal mentions predicting crime rates at the ward level. To train an effective ML model, you'll need far more observations than ward-level data would allow (8 observations). I'd recommend performing your analysis at the tract level. 

I also would recommend clarifying your exact predictive question. For example, are you trying to predict future crime rates? If so, how far in advance are you hoping to make that prediction? I would encourage you to think carefully about what data would be available to make a given prediction. For example, if you are trying to predict crime rates two years ahead, when predicting 2024 crime rates in 2022, you'd have to think about what ACS data would be available in 2022. Because ACS is published on a lag, this would be the 2016-2020 5-year ACS. 

This would also inform what years of crime data you'll use to create your outcome.

Another place to think about time is setting up your training and testing sets, as well as your resampling. I'd encourage you to check out these resources I shared on Slack:

Time-series resampling with tidymodels:

<https://www.tidymodels.org/learn/models/time-series/>

<https://rsample.tidymodels.org/reference/slide-resampling.html>

I'd note that the ACS demographic and economic variables are available at the tract level!

I would encourage you to think about opportunities for other spatial analysis. For example, you can look at crime rates within a given distance buffer around other points of interest, like metro stations. 

Finally, I'm excited about your interest in using methods we didn't cover in class like neural networks and geographically weighted regression. That isn't required, but it is definitely allowed!
