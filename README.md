readme_peter.md

# GRANDMA & GRANDPA'S ETF

## Introduction

Grandma and Grandpa's ETF was developed out of the concern that many older financially interested but technically challenged investors have, when trying to determine an appropriate investment vehicle to park their money.  The financial invesment world is full of earnest investment advice and latest investment crazes, which can generate confusion and trepidation. 

An ETF or exchange traded fund is a good way to mix stocks in a particualr sector or industry to get an even spread of return across an investment group that reflects their interests. Picking the right ETF can be tricky, and hence our model is designed to provide an end state performance tracking dashboard using a coding and mathematical build from the user's basic financial data and attitudes to both investments types and industries, to create a risk profile, which in turn matches the user to a ETF recommendation.

Our initial pie-in-the-sky thought process for our MVP (minimum viable product) looked at potentially collating a number of ETF recommendations based on a a dashboard of buttons and sliders, where individual preferences and risks could be adjusted by the user, which would then generate a risk profile. This profile could then be matched to a number of ETFs. This matching would generate a portfolio of multiple ETFs which could be built and displayed on Tkinter, a GUI toolkit and potentially published to a HTML site.

After coming to our senses with the work load proposed, it became clearer that the coding effort required was probably beyond the scope and available time and resource to deliver this. This bells and whistles version could be developed, time willing, post the initial MVP completion. 

**ADD INTIAL HAND DRAWN DIAGRAM** ![hand_drawn_table](\hand_drawn_process_1.jpg)

We then scaled our MVP back to a more manageable and staged approach. The concept required capturing relevant risk information from the user, and defining the optimal list of ETF portfolios to match:

1. Capture user data and generate a risk profile
2. Draw down API ETF information to provide a library of ETF products
3. Match the risk profile to the best ETF
4. Create and calculate a reference {table/dict/whatever} of dashboard data
5. Generate a dashboard to track the ETF performance and user's investment

**ADD DEVELOPED HAND DRAWN DIAGRAM (NEW VERSION A BIT CLEANER)** ![hand_drawn_table](\hand_drawn_process_2.jpg)

Background set up to manage the project was intially agreed to use Slack for communication, Trello to manage tasks, and Jupyter lab to build out our code. To manage code a github repostiry was set up with  a master and branches.

-------------
 
## Stage One - Grandma and Grandpa's invesment risk profile

Captured and generated in two stages:

1. User interface and data capture
2. Risk allocation

User interface and data capture was intensely debated to distill the input down to a series of questions that would capture the user's prevailing attitude to differing sectors and leanings to investment risk. The intial questions were developed in a yes/no data entry cell (but not a boolean as there is no null value allowed)

A series of questions was then designed to determine the user's risk tolerance to various industries and invesment sectors in an interesting and quizzical manner without seeming like they were filing a tax return. The questions are designed to add or subtract a point(s) for the sector/risk to allow a total risk score to be determined, thereby allowing the user to have the most appropriate ETF allocated for adoption.

---------------

## Stage Two - API Allocation Assessment
 
Queried, cleansed and captured in two (?) stages:

1. API sourcing and data extraction

The investigation of available data in the API world provided a plethora of data and information. Sorting through available data streams for what is needed to calculate the past, current and future performance of the recommended ETF took considerabe time and effort, given that some sources provided partial data, meaning further investigation was required. 

Several APIs were limited by the number of data pulls per day, others charged money . In the end, FinQuant was installed to query the required data to build the portfolio of ETFs. We then looked at whether we could extract further information from "eod history" API. The team found out that Alpaca was not compatible with the Pyviz enviroment, generating errors, and FinQuant was suffice for the data needs. Once tickers and intial data extracted, the team used https://eodhistoricaldata.com/ called the Historical Prices and Fundamental Financial Data API, to extract further data for analysis.

![Project_images](\https://files.slack.com/files-pri/T01U2EACJ03-F027FTHSVH7/image.png)

2. API data cleansing and data frame merging

Grandma and Grandpa's ETF is designed to not only allocate risk and an appropriate ETF portfolio but show the user simple useable dashboard information to ensure their investment is meeting its objectives.

Hence key outputs must include:

1. Return - Annual returns by ETF for past 5 years (looking back 5 years)
2. Projected return - initial investment projected return (looking forward 5 years)
3. Risk - expected return, volatility, sharpe ratio, Beta, Alpha etc
4. Asset allocation - ticker, and portfolio weight (% share)
5. Market health indicators - S&P 500 current state, etc



