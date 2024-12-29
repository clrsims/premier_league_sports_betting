# premier_league_betting
Developed a neural network analyzing a dataset of 2000 games, helping me gamble on Premier League sports that increased my betting accuracy by ~8%. Technologies used: Python, Keras &amp; Tensorflow, Scikit-learn, numPy, Pandas.

I'm a huge Premier League soccer fan, and I have been recently getting into the world of sports betting. Unfortunately, I lost $50 on a bet I was SURE I would win and wondered if there was a better way to maximize my earnings using my own intuition. 

I found a dataset of every Premier League since 1994, two years after the league was founded. The initial difficulty lay in analyzing what data mattered and what didn't and choosing my architecture.

I decided my neural network will be a softmax multi-class classification problem, with three output neurons: probability of home team winning, drawing, and losing.

I would want to predict the result BEFORE the game - the most useful statistics will most likely be the Bet365 and Market stats - i.e. what do other people think the most likely result is?

Away and home team probably has a much larger correlation than people assume too. And what teams usually perform better at home vs away. i.e. not every team performs the same home and away.

Current form is the most important. My neural network will have to be trained on only the most recent data. Say, past five years.

I need a way to place higher weight on recent form. Like a sliding scale, with most recent performances weighted much much more highly than performances from years ago. Thus, I biased recent performances.

Additionally, I needed a way to compare how good two teams were compared to each other. Therefore, I engineered two new features, home_team_ELO and away_team_ELO from http://clubelo.com/ENG.

Then I performed feature scaling and split my test data into train, cross-validation, and testing branches.
I also had to one-hot encode my y data so that my neural network could analyze it using a sparse categorical cross entropy loss function. 
After constructing a very basic neural network, I started implementing techniques to reduce overfitting such as Dropout layers, tweaking optimizers and learning rate, implementing l2 regularization, and callbacks to avoid wasting data.

My model ended up overfitting :( But it was a great introduction into using neural networks!
