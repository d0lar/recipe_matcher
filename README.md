# Recipe matcher
**System rekomendacyjny przepisów kucharskich bazujący na matrycy podobieństw składników**

This repository consists of an algorithm that finds ingredients alternatives and best-match recipe propositions.

There are many examples of recipe data usage in classification. Mainly, based on ingredients, data scientists try to predict cuisine style (eg. Italian, Indian, Korean, etc.). But this kind of classification is not useful for the end-user. Everyday problems are simpler - what can I cook today? So we're looking for recipes that can be used based on available ingredients. Here where the problem appears - recipes consist of a limited list of ingredients. They don't give you clues which ingredients can be replaced by others. 

The main goal of this project is to create a similarity matrix for products. The second goal is to prepare an algorithm that would take a list of products available in the kitchen and return a list of potential recipes. This algorithm will take into account potential replacement. So assume, that in the recipes catalog, there is a recipe for a tomato sandwich. You have all the necessary ingredients apart from the tomato. But you have paprika. You pass the list of available ingredients and the program will check not only potential recipes for tomato based recipes. It will also take into account those where paprika is used. In the end, you'll have a list of alternatives for your ingredients and a list of recipes that can be prepared based on your ingredients. One additional feature of this script will be the fact, that your input (list of products) can include different kinds of products, eg. chicken, flour, eggs, oil, pasta, chocolate. Because the program will check different combinations of products, it will check among others "chicken, eggs, oil, pasta" and "flour, eggs, oil, chocolate". So in the final list of proposed recipes, you'll find both chicken pasta and choco cookies.

# Dataset
For the analysis, I've used recipes from kuchnialidla.pl because they are prepared by professional chefs. I wanted to avoid popular websites where recipes are prepared by amateur home cooks without proper knowledge of cooking. There is a downside of that choice - a limited number of recipes.

# Approach
This program should be considered as a playground. Taking into account the lack of data purity (different forms used, additional words, etc.), dataset preparation and cleaning is a non-trivial task to perform. Same with finding the best classifier for recipes propositions. Therefore, this notebook will give proper guidance for further development. 

# Reading guidance
There are 3 notebooks. Follow the number-based order. In those notebooks, some of the data frames, lists, jsons, etc. are saved in pickles. It's due to the fact that computation time is very long (scrapping took ~7h, calculating product similarities ~12h). Those parts of the code are commented. 

# Requirements
To run all notebooks on your own you need to have Spacy package for NLP configured on your machine.
Besides that, internet connection, if you want to scrap database.
