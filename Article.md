# A Statistical Analysis of the Work of Bob Ross
## Background
Bob Ross is a famous artist who painted a variety of paintings in his time of painting. He made a tv series were he would paint but at the sametime he would talk you through how he paints the art for each episode. through his time of painting is his series he made 31 seasons of him painting. Each season had 13 episodes to them, which would equal a total 403 episode also being the number of paintings he painted with in the series.

Bob Ross had a painting style where he would be painting at a fast pace which made him sometimes hard to follow during his series. The style was called "alla prima" which he learned with a man named Bill Alexander. he was in the military for some time and after he retired he started his art career. His career blossomed to more than his series.

## Introduction
This project uses computer science techniques to explore artistic patterns in The Joy of Painting, the long-running television series hosted by Bob Ross. Although Ross is known for his calm tone, soothing instructions, and “happy little trees,” his show also provides a large, structured dataset that is perfect for computational analysis. Inspired by FiveThirtyEight’s article “A Statistical Analysis of the Work of Bob Ross,” I analyzed several aspects of the show’s episodes, including the wording of their titles and the frequency of visual elements Ross painted. Using Python, Pandas, regular expressions, and Matplotlib, I transformed raw CSV files into visual insights that reveal consistencies in Ross’s creative style across more than a decade of television.
## Most Common Elements in his Work
The start of the analysis focused on the physical elements Ross painted. The dataset includes counts of dozens of elements—such as trees, mountains, lakes, clouds, and cabins—for every episode. Using Pandas groupby and sum, I calculated the total number of times each element appeared across all seasons.

The resulting bar chart of the top five most common elements reveals that:

- TREE and TREES dominate the dataset, appearing well over 300 times each.

- DECIDUOUS and CONIFER trees also rank high.

- CLOUDS round out the top five.

This visualization directly reinforces Ross’s reputation for painting trees. According to FiveThirtyEight, Ross painted at least one tree in 91% of all episodes. My chart mirrors that conclusion: trees (in various forms) appear far more often than any other element. Even when broken down into specific types—conifer, deciduous, pine—the frequency stays extremely high. This is strong evidence that trees were not just an occasional subject; they were a fundamental part of Ross’s painting formula.

![alt text](Screenshot_5-12-2025_103552_localhost.jpeg)

## Amount of Trees in Each Season of his Show
To understand how Ross’s style evolved (or stayed the same) over time, I created a graph of total trees per season.
This involved several computational steps:

1. Extract the season number from episode IDs using a regular expression (str.extract(r"S(\d+)")).

1. Convert the extracted season values to integers.

1. Filter the dataset so only tree-related elements were included (TREE, TREES, DECIDUOUS, CONIFER, etc.).

1. Group the filtered data by season.

1. Sum all tree counts within each season
1. Plot the totals using Matplotlib.

The resulting bar chart shows a striking pattern:
Tree counts stay consistently high across all 31 seasons. They typically range between 20 and 26 trees per season, with very little variation. This stability shows that Ross’s artistic style did not drastically change over time—even as the show progressed, his reliance on trees stayed strong. Unlike many artists whose style shifts dramatically throughout their career, Ross maintained a consistent approach focused on forests, mountains, and peaceful natural scenes.

This finding also aligns with FiveThirtyEight’s observation that Ross followed a recognizable “painting formula” repeatedly throughout the show. My seasonal analysis confirms the structural consistency of that formula.
![alt text](Screenshot_5-12-2025_103532_localhost.jpeg)

## Most Common Words Used in his Titles
I studied the language Ross used in his episode titles. I cleaned the text by converting titles to lowercase, removing punctuation, and splitting them into individual words. Using Python’s string operations and Pandas’ value_counts function, I identified the most common words.
The bar chart of the five most frequent title words shows a clear pattern:

- “the” is the most common word,

- followed closely by “mountain”,

- with “of”, “winter”, and “oval” also appearing frequently.

These results highlight the natural themes Ross gravitated toward. Titles repeatedly reference mountains, winter scenes, and landscape shapes. This matches the nature-focused topics Ross painted on the show. FiveThirtyEight’s research also found that mountains appeared in nearly 40% of episodes, which supports the high frequency of the word “mountain” in the titles. Episode titles therefore act as a short summary of what viewers can expect in each painting, and analyzing them computationally confirms Ross’s consistent artistic preferences.
![alt text](Screenshot_5-12-2025_103610_localhost.jpeg)
## Conclusion
This project demonstrates how computer science can uncover hidden patterns in creative works. By analyzing episode titles, element frequencies, and seasonal trends, I confirmed that Bob Ross’s paintings follow consistent themes centered around forests, mountains, and calm natural scenes. The results strongly match the findings published by FiveThirtyEight, strengthening the reliability of the analysis.

Through this assignment, I gained experience in Python programming, data cleaning, string processing, statistical grouping, and visualization. More importantly, it showed how computation can be applied beyond technical fields—even something as artistic as painting becomes measurable and analyzable with the right tools. Bob Ross said, “Everyone needs a friend,” and in this project, Python became the friend that helped uncover the structure hidden inside hundreds of peaceful landscapes.