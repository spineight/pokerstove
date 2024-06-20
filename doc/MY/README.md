Gives a brief overview of Pokerstove functionlity:
https://www.cardschat.com/poker/tools/pokerstove/

# “Enumerate All” vs. “Monte Carlo”
PokerStove doesn’t calculate, it simulates. So when you run the software, it will pit the hands and ranges you entered, on the board that you put in (if any), randomize all the unknown variables many times, and tell you how often on average the different players win. There are two ways it can do this, which are selectable in the PokerStove interface:

“Enumerate all” goes through every possible combination. For some scenarios this is very fast since there are only a few possible combinations. Most cases involving only two players take mere fractions of a second to calculate. When you have three or more players involved in a pot, the number of possible cases grows exponentially, and it may take a long time for the program to run every single combination of possibilities.

That’s when using the “Monte Carlo” option comes in handy, as it randomizes the simulations. This means that instead of following a pattern and grinding its way through every possible holding, it will randomly run simulation after simulation. As computers are so fast, a huge number of samples (millions) can be simulated in around a second. This method is substituting precision for speed, but if left to run for a while it will quickly stabilize towards the true value.