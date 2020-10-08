# Will you have a G'-not rainy-DAY tomorrow, mate? :sunny: :sun_behind_small_cloud: :partly_sunny: :sun_behind_rain_cloud: :cloud_with_rain:

<img src="imgs/gooday.jpg">

Repository includes: 
* Streamlit integration as a prediction to weather forecast
* Juyter notebooks for assessing weather predictions
* Relevant datasets, library requirements and pictures 

<img src="imgs/sydney_rain.jpg">

### Wait, how certain you are that it's gonna rain or not in the Down Under? :kangaroo:

Every day at 6pm(ish), Australia's favourite machine learning algorithm, Light GBM, will advise on whether aussies should leave their umbrellas home or not.

Leveraging data from weather stations across the nation (Outback included!), Light GBM has an outstanding 80% accuracy on its forecasts by taking into account the widely variety of inherent climates features.


### Given that last data on complaints, what are PagSeguro's main pain points according to its clients? :broken_heart:

* Image below illustrates main common terms in the complaint dataset, after normalizing for common stop words and non-insightful vocabulary:

<img src="imgs/wordcloud.png">

As we can surmise from the wordcloud:
>* Most common expression "entrei em contato" suggest that clients turn to ReclameAqui after exhausting options to resolve with PagSeguro

>* Expressions "conta pagseguro" (current account) and "cartao de credito" (credit card) suggest that those products might **detract customers' satisfaction**

>* PagSeguro flagship product, moderninha (a yellow credit card machine) is not a common term, which might that it **promotes customers' satisfaction**

## Anyhow, how was the gathering process? :microscope:

### Phase 1 (aka piece of :cake:): Integration with Yahoo Finance's API:

* Unfortunately, Yahoo deprecated their Finance API in 2017. Fortunately for us, Python has a stable API called yfinance, which does pretty much the same thing
* Adjusted share prices of PagSeguro and its peers were then scrapped by using the yf.download method 

### Phase 2 (aka :rocket: science): Scrapping ReclameAqui's website:

* Unfortunately, RA's website can only be scrapped using selenium, which slows down the overall process
* Scraping process was divided into two consequent streams:
>* **Stream 1**: Selenium gathered all the complaint links of PagSeguro available at RA: ~50k links were then consolidated into .txt files (RA allows selenium to scrape 10 links per interaction)  

>* **Stream 2**: Selenium then opened each complaint link to gather useful data for later parsing - more especifically: complaint title, body, status, date, city/state of the client

