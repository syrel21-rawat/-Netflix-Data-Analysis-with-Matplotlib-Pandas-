```python
#import the libraries
import matplotlib.pyplot as plt
import pandas as pd

#load data
df=pd.read_csv("netflix_titles.csv")

#cleaning data
df=df.dropna()

type_counts=df["type"].value_counts()
plt.figure()
plt.bar(type_counts.index,type_counts.values,color=["skyblue","orange"])
plt.title("Numbers of Movies VS TV Shows on Netflix")
plt.xlabel("Type")
plt.ylabel("Count")
plt.tight_layout()
plt.savefig("movies_vs_tvshows.png")
plt.show()

rating_counts=df["rating"].value_counts()
plt.figure()
plt.pie(rating_counts,labels=rating_counts.index,autopct="%1.2f%%")
plt.title("Percentage of Content Ratings")
plt.tight_layout()
plt.savefig("ratings.png")
plt.show()



movie_df=df[df["type"]=="Movie"].copy()
movie_df["duration_int"]=movie_df["duration"].str.replace("min"," ").astype(int)
plt.figure()
plt.hist(movie_df["duration_int"],bins=20,color="pink",edgecolor="black")
plt.title("Distribution of Movie Duration")
plt.xlabel("Duration")
plt.ylabel("Movie")
plt.tight_layout()
plt.savefig("duration&movie.png")
plt.show()


release_counts=df["release_year"].value_counts().sort_index()
plt.figure()
plt.scatter(release_counts.index,release_counts.values,color="red")
plt.title("Release Year VS Number of Shows")
plt.xlabel("Release Year")
plt.ylabel("Number of Shows")
plt.tight_layout()
plt.savefig("release_yer_scatter.png")
plt.show()

country_counts=df["country"].value_counts().head(10)
plt.figure()
plt.barh(country_counts.index,country_counts.values,color="green")
plt.title("Top 10 Countries by Number of Shows")
plt.xlabel("Number of Shows")
plt.ylabel("Country")
plt.tight_layout()
plt.savefig("top10countries.png")
plt.show()



```


    
![png](output_0_0.png)
    



    
![png](output_0_1.png)
    



    
![png](output_0_2.png)
    



    
![png](output_0_3.png)
    



    
![png](output_0_4.png)
    



```python

```
