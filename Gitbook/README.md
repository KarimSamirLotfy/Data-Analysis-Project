# readme

## Dataset Source \(Scrapped\)

the Dataset consists of 3 scrapped ecommerce websites that were all scraped on the same day 1/5/2020.

each of the websites is it's own format and structure.

1- website 1: [Jumia](https://www.jumia.com.eg/) which is an egyptian ecommerce site that sells all products but is known for its tech deals and high discounts.

![Jumia \(Egypt\)](../.gitbook/assets/Egypt_site.png)

2- [Amazon.sa](https://www.amazon.sa/) which is the subsidary of the famous company Amazon in Saudi Arabia \(KSA\).

## ![Amazon \(KSA\)](../.gitbook/assets/Saudi_site.png)

3- [Boulanger](https://www.boulanger.com/) a local french eccomerce site that is famous for cheap prices espacially in the salles.

## ![Boulanger \(France\)](../.gitbook/assets/french_site.png)

each of these site had a search term "Gaming Laptop" written in the search bar and then the result was scrapped for either 5 pages or till the end.

_NB:this data was scrapped programmatically from 3 diffrent sites in 3 diffrent contries with a vpn to assure local data is shown._

## DataSet

{% page-ref page="./" %}

## Introduction

**Gaming Laptops** are a very widespread product sold in all parts of the wrold with a huge price varaition and quality variation. we explore today the realtion between price, the reigion, discount, cpu, gpu, ram.

## Feature Description

### Laptops.csv

* this is the aggregated dataset that was created during the cleaning phase from merging the scraped data from all 3 sites

1. **text:** scraped text from the site
2. **url:** the url of the link that was scrapped
3. **price:** price in dollars after cleaning and unifing the dataset
4. **cpu\_name:** the name of the cpu like i7, Ryzen 5
5. **cpu\_gen:** the generation of the cpu, ex: generation 7, 9, 5
6. **discount\_value:** the percentage of the discount
7. **store** the store from which this row was scrapped

### egypt\_store.csv

> Original dataset that was scraped from Jumia.eg further cleaning and feature extraction was done on this dataset during the cleaning phase 1. **selection1\_url:** url pointing to the link of the product

1. **selection1\_name:** name of the product as written on the site
2. **selection1\_discount:** discount value
3. **selection1\_price:** price of the product in EGP
4. **selection1\_brand:** Brand name \(ex: Lenovo, DELL\)
5. **selection1\_brand\_url:** link to the main site of the brand like Lenovo

### french store.csv

> Original dataset that was scraped from Jumia.eg further cleaning and feature extraction was done on this dataset during the cleaning phase

1. **Title:** name of the product on the site
2. **Title\_link:** link to product

3.**bestpoints:** dsplay info and other usefull info of the product **caracValue:** column with info about the specs of the laptop but it is not consistent so it has to be cleaned

1. **caracValue1:** refresh rate of dsiplay
2. **caracValue2:** cpu inforamtion
3. **caracValue3** storage info
4. **fix-price:** price in EUR
5. **stock:** stock infromation also info about delivery
6. **nb-opcom-1:** more specs like I/O ports and other modules
7. **Le+:** more specs
8. **priceBarre:** price before discount in EUR
9. **priceDiscount:** discount

### sa\_store.csv

> data scrapped from amazon KSA all the laptop specs were cramped in the name of the product so a lot of cleaning had to be done to extract these features

1. **selection1\_name:** name of the product which has all the specs in it
2. **selection1\_url:** link to product
3. **selection1\_selection2:** price in SAR
4. **selection1\_selection2\_url:** link to product

## Summary of Findings

### Intel vs AMD CPU

I found that Intel based CPU were more comman in all 3 countries which does show that Intel seems to have a bigger market share with laptop manufacturers

also there seems to be that higher end Intel CPU are on average more expensive then there AMD counterpart, while mid range CPU are actually prety even with Intel having a higher price variation

also Intel seems to be sold more in outliers which refrence super expensive High End models.

### Key Insights for Presentation

### Intel vs AMD CPU

I found that Intel based CPU were more comman in all 3 countries which does show that Intel seems to have a bigger market share with laptop manufacturers

then i created a Regression model and used it to get a correlation between each variable and the price. there I found that the most correlated variables are 1. which GPU gen was used: RTX, GTX, No gaming GPU 2. was the cpu genration which was more influential than the CPU brand. so choosing Intel or AMD does not influence the price as much as choosing which cpu generation: 5, 7, 9 3. the type of the secondary storage seems to be more immportant than that of the capacity as it is more correlated

then I wanted to test whether there was a diffrence in the average price of the laptops on each store

and there was also it seems the french store is the more expensive and high end store as the laptops sold seem to be as the average price for laptops sold in france is higher than that of egypt and saudi.

then I looked if there are any patterns between price and discount and contrary to comman belif there is no correlation but it seems that **Boulanger** store had both more expensive products with bigger discounts on many of them while **Jumia** seems to be cheaper while still puting discounts on it's products.

After this I looked at which GPU's are paired with which CPU's and it is clear that Intel seems to appeal to both Gamers and non-gamers as it's CPU is paired with RTX sometimes and othertimes paired without any Gaming GPU while AMD seems to strugle with non-gamers as it is almost non existant

then I show which combination of GPU generation and CPU generation is the most favored where the GTX 7th gen CPU are the most presented

then I examine the average price of each GPU and CPU combiantion where I find that non gaming GPU are also very expensive when paired with a 9th gen CPu

### Resources

1. Seaborn Documentation
2. matplot Lib
3. Udacity examples in Data Vis Course

