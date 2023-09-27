# NBA Sports Betting Using Machine Learning 🏀
<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/output.png" width="1010" height="292" />

This project utilizes machine learning techniques to predict the winners and over/under outcomes of NBA games. By utilizing team data from every season from 2007-08 to now and incorporating the odds of these games, the model employs a neural network to predit outcomes and odds of upcoming games. The model achieves rougly 75% accuracy on moneyline predictions and roughly 58% on over/under outcomes. Additionally, the AI provides an expected value on the moneyline for a future game and suggests an amount of your bankroll to bet, following the Kelly Criterion. Keep in mind, a more popular and less risky approach is to bet only half of what the Kelly Criterion suggests.
## Packages Used

This project is implemented in Python 3.8 and relies on various packages and libraries, including:

* Tensorflow - Machine learning library
* XGBoost - Gradient boosting framework
* Numpy - Package for scientific computing in Python
* Pandas - Data manipulation and analysis
* Colorama - Used for color text output
* Tqdm - Provides progress bars
* Requests - Http library
* Scikit-learn - Machine learning library

## Usage

<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/Expected_value.png" width="1010" height="424" />

To get started, ensure that you have installed all of the above packages, which you can do by running these commands:

```bash
$ git clone https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting.git
$ cd NBA-Machine-Learning-Sports-Betting
$ pip3 install -r requirements.txt
```

Then, you can run the AI using different flags; here is an example:

```bash
$ python3 main.py -xgb -odds=fanduel
```

Odds data is automatically fetched from sbrodds if the -odds flag is present.  Options include: 
* fanduel
* draftkings
* betmgm
* pointsbet
* caesars
* wynn
* bet_rivers_ny

Without the -odds flag, enter the over/under for today's games manually after starting the script.

You can also use the '-kc' flag to view the recommended fraction of your bankroll to wager based on the model's edge.

## Flask Web App
<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/Flask-App.png" width="922" height="580" />

This repo also includes a small Flask application to help view the data from this tool in the browser.  To run it:
```
cd Flask
flask --debug run
```

## Getting new data and training models
```
# Create dataset with the latest data for 2022-23 season
cd src/Process-Data
python -m Get_Data
python -m Get_Odds_Data
python -m Create_Games

# Train models
cd ../Train-Models
python -m XGBoost_Model_ML
python -m XGBoost_Model_UO
```

## Contributing

All contributions welcomed and encouraged.
