# Superficial Robot


Kate is an average person who has accumulated a lot of stuff over the years. 

A large portion Kate’s stuff is her clothing.

She has 25 jackets or coats, 20 bags, 50 bottoms (skirts, pants or jeans), 60 pairs of shoes, and 130 tops (shirts, sweaters, and t-shirts).

This is a combination formula:

![GitHub Logo](https://cloud.githubusercontent.com/assets/16660416/24681870/e5c48a28-194b-11e7-82bf-18db090d485c.GIF)

Kate just wants to get dressed and start her day.

But the amount of unique combinations she can make with her items is

n!/r!(n-r)! = 295!/5!(295-5)! = 295!/5!*290! = 1.302405364 E+602/120*6.031611618 E+589 =

= 130240536421542917278229579384676189809452723396833830881919418346829088259701652869791124822088676130693811076368225756785347739189353701535633041283562993445822106610934526642389209595125469386118872535411437545685252428896850271843922536464309018822342445871554626664317634424228848950164791490789924849157336730173758797906108816385979568498605532576905819795362719529920287521877108764591305813253343348372319239814648594495088292628894518916165874874657736591671523889732638401211216090244005499218918811963278481347594682368000000000000000000000000000000000000000000000000000000000000000000000000
/
7237933942065385171934157148273594280950395658011111970083504296645720458298386229419767821957137265817112983100811434345701542726591278815471614277879515323892151421372887581918496262165412919659445065515032533698307296057564890365610941499990530000611235883971167450350243779995693098604698559234586625897329757278395939420217612589659637791006373521315244669614852053876538652016282911113538914442726597312483493685770423924342743665151937714022484809749093046204703015710787403099967524592510291819319738132439498752000000000000000000000000000000000000000000000000000000000000000000000000 =

## 17 994 159 309

Kate would rather unsee this number. 
She needs help.

Her better self comes to the rescue.

She studies SQL and creates a schema with 3 tables in it.

The largest table, articles_list, contains 16 fields, including:
- Article_ID (primary key)
- Subcategory_ID
- Brand_Name
- Weather
- Occasion_Name (example: "BCD", "BD", "C," where "B" stands for "Business," "C" for Casual," and "D" for Dressy")
- Color
- Color_Family
- IsCurrent (boolean)
- IsOversized (boolean)
- NumTimes (the amount of times a particular item was chosen)
- NumYears (the amount of years Kate has the item)
- Style (example: "BFM" stands for "Bohemian," "Futuristic," and "Modern")

Kate quiries her database and begins to realize what causes her problems.

 ```
SELECT outfit_robot.articles_list.Weather,
COUNT(Article_ID) AS Num_Warm
FROM outfit_robot.articles_list
WHERE Weather = "WRM";
 
 ```
Result = 62, or 26% (there are 238 records in the articles_list database). 26% of Kate's clothing is suitable only for very warm  weather, while the proportion of really warm days in SF is about 5%.

```

SELECT outfit_robot.articles_list.Occasion_Name,
COUNT(Article_ID) AS Num_Formal
FROM outfit_robot.articles_list
WHERE Occasion_Name like "%D%";

```
The result of 191 means that 80% of her items are somewhat formal (and she often tries to avoid them).

Kate's still determined to spend no more than 2 minutes on getting dressed every day. She begins creating the Superficial Robot algorithm.

She makes an inner join of articles_list and article_category and saves the result as an csv file.

Parses the file in Python and makes 6 lists of lists.

*the code works. the readme is unfinished*
