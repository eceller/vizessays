# vizessays
Data Visualization Essays for HIST697-001
Viz Essay 1
---
title: "Celler-Viz-Essay-1"
author: "Eric Celler"
date: "3/26/2017"
output: html_document
---

```{r, echo=FALSE}
library(readr)
nnv <- read_tsv("all-votes.tsv")
library(tidyverse)
```

```{r, echo=FALSE}
ga <- nnv %>%
  filter(Type == "General",
         Office == "U.S. House of Representatives",
         State == "Georgia",
         !is.na(County))
```

The period from 1789-1824 saw a new nation discovering the meaning of governance and democracy; this manifested itself in many ways, however one of the more concrete and examinable ways this surfaced was through voting behavior.  The United States saw in its early years an effort to establish and organize itself both on the national and local levels through the ballot box.  When one is attempting to look back at the record of this behavior, one discovers that a great deal of data has already been compiled and transcribed -- an immense help to any historian working in these efforts.  The dataset "A New Nation Votes" helpfully (if imperfectly) provides rather comprehensive data on voting patters spanning from the U.S. House of Representatives all the way down to sheriff and other local offices.  And, while this large dataset does indeed offer fascinating insights and questions into early American voting patterns, this author is interested in the voting patterns for the election for the U.S. House of Representatives of one particular state.

The state of Georgia -- one of the first 13 colonies -- faced similar challenges as the rest of the early republic.  The New Nation Votes dataset reveals that, while there were prominent political parties emerging in the United States during this period, there were also a number of smaller political competitors.  Georgia was no different than the rest of the nation in this regard.  When one narrows down the dataset to focus solely on Georgia -- specifically when looking at votes by affiliation within Georgia -- we can see a story emerge about the succes of particular parties over time in the state of Georgia.  As is seen in the data, from the period of 1789 - 1824, we see a broad success story in the trajectory of the Jeffersonian party, specifically with regard to the Jeffersonian Party.  Over the period covered, the Jeffersonian party garnered, on average, roughly 1800 votes per U.S. House of Representatives election.  This should not be particularly surprising as the south is largely agrarian during this time and thus would be sympathetic to the rural ideals of the Jeffersonian party.  Figure 1 below highlights this claim.

```{r, echo=FALSE}
ggplot(ga, aes(x = Affiliation, y = Vote,
               color = Affiliation)) +
  geom_line() +
  labs (title = "Fig 1
U.S. House of Representatives Vote count by Party 
Affiliation") +
  labs (subtitle = "Georgia, 1789 - 1824") +
  coord_flip()
```

If one takes a look specifically at the Jeffersonian party for the time frame in question, one will see that it is indeed the case that the party grew in popularity over time.  Figure 2 shows the voting trend for the Jeffersonian party in Georgia from the period 1789 - 1824; here we can see clearly that the party continued to grow in popularity from the time of the signing of the United States Constitution.  There are a few instances where we can see a diminishment of popularity for the party, but the overall trend suggests increasing strength in the state of Georgia.
```{r, echo=FALSE}
ggplot(ga, aes(x = Date, y = Vote)) +
  geom_col() +
  labs(title="Fig 2
U.S. House of Representatives Votes for the Jeffersonian Party in 
Georgia") +
  labs(subtitle="1789-1824") +
  coord_flip()
```

As can be seen here, the Jeffersonian Party grew in popularity over the time period of 1789 - 1824 in the state of Georgia during elections for the U.S. House of Representatives.  There are a variety of explanatory factors for this, however, here it will suffice to simply observe the trend that emerges from the data provided by the New Nation Votes dataset when the data is cut down to examining the election trend in the state of Georgia for the U.S. House of Representatives in the first 35 years of the United States' history.
