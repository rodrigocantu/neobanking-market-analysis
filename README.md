# Neobanks Market Analysis through Topic Modeling

<img src='https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/NEO-BANKING_1.jpg'  width="300" height="300" align="left">

## Background

### Objective
To understand what are the users of the top Latinoamerican **neobanking** apps complaining about by **scraping** app reviews from the *iOS App Store* and *Android Play Store* and **classifying** via **topic modeling**.

### Importance
* **85% of consumers** trust online reviews as much as a *personal recommendation*.
* Users are more likely to write a review if they are *frustrated or having a bad experience*.
* App reviews will not only point out future aspects of _improvement_ but also make users feel **involved and influential**.
* **Users are 8x more likely to download a highly rated app of an unknown brand than a poorly rated app of a known brand**.

### LATAM Neobanks Analyzed
* [albo]('https://www.albo.mx/')
* [Klar]('https://www.klar.mx/')
* [Cuenca]('https://cuenca.com/')
* [Fondeadora]('https://fondeadora.com/')
* [hey]('https://www.heybanco.com/index')

<img src="https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/albo-logo.jpg"  width="180" height="75"> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/cuenca-logo.png"  width="100" height="80"> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/klar-logo.png"  width="80" height="80">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/fondeadora-logo.jpg"  width="80" height="80">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/hey-logo.png"  width="80" height="80">

## What is Topic Modeling?
Topic modeling is an unsupervised **natural language processing machine learning** technique that's capable of scanning a set of documents, detecting word and phrase patterns within them, and automatically clustering word groups and similar expressions that best characterize a set of documents. *Topic modeling* can be easily compared to **clustering**. By doing topic modeling we build clusters of words rather than clusters of texts. A text is thus a mixture of all the topics, each having a certain weight.

### How does it work?
If document classification is assigning a single category to a text, topic modeling is assigning multiple tags to a text. A human expert can label the resulting topics with human-readable labels and use different heuristics to convert the weighted topics to a set of tags.

### Why do you need it?
There are several scenarios when topic modeling can prove useful. Here are some of them:
- **Text classification** – Topic modeling can improve classification by grouping similar words together in topics rather than using each word as a feature
- **Recommender Systems** – Using a similarity measure we can build recommender systems. If our system would recommend articles for readers, it will recommend articles with a topic structure similar to the articles the user has already read.
- **Uncovering Themes in Texts** – Useful for detecting trends in online publications, for example.

## Methodology
These are the steps taken during this analysis:
1. Scrape the data from all countries' *Apple App Stores* and *Google Play Stores*.
2. Homogenize the data by joining both *iOS* and *Android* datasets.
3. Normalize the comments by changing the encoding to **ASCII**.
4. **Classify** the comments' language.
    - 47 languages detected.
    - ~1% of data was in English.
    - **~95% of data was in Spanish**.
5. Limit the reviews to ratings below *4 stars and that contain at least 15 characters*.
    - **~18.5%** of reviews across all neobanking apps **are rated below 4 stars**.
6. Generate source topics of *bad reviews* through [Latent Dirichlet allocation]('https://en.wikipedia.org/wiki/Latent_Dirichlet_allocation').
    - A list of common and meaningless words were omitted for this section.
7. Label and extract the topics and their most represented words. Four main topics of issue where detected:
    - Products, services and features provided by the app.
    - Ease of registration and verification. This includes receiving the companies' physical card.
    - App performance and functionality.
    - Customer support provided by the company behind the apps.
8. Merge and label the results into the initial dataset.
9. Manually label a random sample.
10. Validate the model with the validation data.
    - The model reached 76% accuracy.

## Results and Discussion.

![Figure 1](https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/figures/fig-1.png)

As it can be seen in **Figure 1**, the *most frequent reason* that users complain about **LATAM neobanks** is the **customer support**, followed by **app performance**, then **ease of registration/verification**, and finally the **products, services and features provided by the app**. This implies that almost **one third** of the unpleased users _weren't even able to use the companies' services in the first place._


![Figure 2](https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/figures/fig-2.png)


But is this true for **every** of the analyzed neobanks? **Figure 2** shows that in general, the answer is **no**. As it can be observed, **hey's** main critical issue is the **performance** of the app itself. On the other hand, **Klar** is shown to struggle with **customer support** more than anything else.


![Figure 3](https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/figures/fig-3.png)


## Conclusion
With that said, the four predicted topics are present across the five main neobanks in Latinoamerica, meaning that those issues shall be bared in mind by potential new users. However, there are problems issued by the users that are more present in certain apps (e.g. app performance and functionality in **hey** is higher than its competitors).
Neobanks should consider that a good customer support is essential to their success, if they don't want to generate bad reviews. There certainly is room for improvement in all of the discussed topics, specially on the **customer support** and **ease of registration and verification**,  including receiving the companies' **physical card**, as shown in **Figure 3**.

<img src='https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/graphics/NEO-BANKING_2.jpg'  width="300" height="300" align="right">

All **libraries** used can be found in the [**_requirements.txt_**](https://github.com/rodrigocantu/neobanking-market-analysis/blob/main/requirements.txt) file.

You can see the **Tableau** sheets [**_here._**](https://public.tableau.com/views/online-banks/Sheet1?:language=en&:display_count=y&:origin=viz_share_link)

### References
* [Askalidis, Georgios & Malthouse, Edward. (2016). The Value of Online Customer Reviews. 10.1145/2959100.2959181.]('https://www.researchgate.net/publication/305044577_The_Value_of_Online_Customer_Reviews')
* [Utz, Sonja & Kerkhof, Peter & Bos, Joost. (2011). Consumers rule: How consumer reviews influence perceived trustworthiness of online stores. Electronic Commerce Research and Applications. 10.1016/j.elerap.2011.07.010.]('https://www.researchgate.net/publication/251693484_Consumers_rule_How_consumer_reviews_influence_perceived_trustworthiness_of_online_stores')
