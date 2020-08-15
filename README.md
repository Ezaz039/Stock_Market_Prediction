# Stock Market Live Update and Future Stock Value
‘A rising stock market is usually aligned with a growing economy and leads to greater investor confidence’. Investors follow some investment strategy:thinking: before investing his/her stock into the market. In that scenario previous stock history for any company is the key factor of investment. Futures and derivatives help increase the efficiency of the underlying market. In Indian market investors preffer ‘NSE’ companies:sunglasses: because it provides more liquidity for its stocks.

## Solution:
1. Every ‘NSE’ company provides it’s historical stock data:innocent:.
2. For any interval (i.e. 1m, 2m, 5m, 15m, 30m, 60m, 90m, 1h, 1d, 5d, 1w, 1mo, 3mo, YTD etc) historical data can be extracted using ‘Yahoo Finance Api’:upside_down_face:.
3. ‘LSTM (Long Short Term Memory)’ neural network model can predict future stock price based on historical data for any company.
4. Social influencing can also affect stock market (i.e. relevant news article can increase stock value for a company or vice-versa)[4].
5. This methodology:neutral_face: can be used to build a stock market website which will show historical stock data as well as future stock for any ‘NSE’ company.

## Methodology:
1. Every company provides it’s historical data:hugs:. We can extract historical data for any interval for a particular company using ‘Yahoo Finance Api’:hand_over_mouth:. On the basis of historical data we can predict stock data:money_mouth_face: for following data.
2. Our stock market website will always train prediction model:relieved: on the basis of historical data and sentimental analysis of news article:relieved: for all the comapnies and show results in web browser on the basis of user’s query.
3. As training Machine Learning model takes long time to execute:angry: so we divide our model into two part (website manipulation and training prediction model):slightly_frowning_face:. Both website manipulation and training prediction model will run parallally:pensive:.

## Background Process Scheduling:
- Our stock market website is build using ‘Flask’:no_mouth:.
- Training any machine learning algorithm is a lots of time consuming process:angry:. So we have scheduled model training in the background in our website i.e. both website and model training will be running parallally:slightly_frowning_face: so that model traing wouldn’t wait for any request:relieved:. It will automatically update the trained model after a fixed interval:relieved:.

### Pseudocode:
* app = Flask(__name__)
* scheduler = APScheduler()
* scheduler.init_app(app)
* scheduler.start()
* app.apscheduler.add_job(func=scheduled_task,trigger='interval',weeks=1,args=[100],id="background_process”)

## Sentimental Analysis:
‘Stock exchange’ is a subject that is highly affected by economic:nauseated_face:, social, and political factors. There are several factors e.g. external factors or internal factors which can affect and move the stock market. Stock prices rise and fall every second due to variations in supply and demand:grimacing:. Various Data mining techniques are frequently involved to solve this problem. But technique using machine learning will give more accurate, precise and simple way to solve such issues related to stock and market prices:relieved:.

## Some overview of my stock market prediction website:
![GitHub Logo](/images/home.png)
![GitHub Logo](/images/company_list.png)
![GitHub Logo](/images/live_stock.png)

## Usage:
Stock Market Website is currently deployed in Heroku. The website can be accessed through https://stockvalueprediction.herokuapp.com/
