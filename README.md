[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Answer
Looking at the slides about quick sort we can see that it is implied that $\frac{1}{2}$ of the array are considered good pivots and the first and last $\frac{1}{4}$ are considered bad pivots. We can use this to calculate our probability of getting a good pivot. We can do this by checking all of the groups of three that we might select from our array and putting them into 3 categories, those categories being a bad pivot on the lower part denoted as $L$, a bad pivot on the upper part denoted as $U$, and finally a good or two good pivots in the middle denoted as $M$. From this we can get the probabilities of each of the parts:

$M$ has a good pivot for the second $\frac{1}{4}$ so we can add this to our running total of $\frac{1}{4}$ good pivots. It also has good pivots in the third $\frac{1}{4}$ so we can add this to our running total of good pivots to get $\frac{1}{2}$. So in the end the probability that $M$ has a good pivot is $\frac{1}{2}$.

$L$ has bad pivot for the first $\frac{1}{4}$ a good pivot in the second $\frac{1}{4}$. This gets a total of $\frac{1}{4}$ for the good pivots of $L$.

$U$ has bad pivot for the fourth $\frac{1}{4}$ a good pivot in the third $\frac{1}{4}$. This gets a total of $\frac{1}{4}$ for the good pivots of $U$.

Using the median of three method we get four seperate parts. The first part is PPP which gets us $\frac{8}{64}$. The second part is LPG which gets us $\frac{12}{64}$. The third part is PPL which gets us $\frac{12}{64}$. The first part is PPG which gets us $\frac{12}{64}$. When we add them all up we get $\frac{44}{64}$ or $68.75$% chance of selecting a good pivot.