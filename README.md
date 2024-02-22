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
Looking at the slides about quick sort we can see that it is implied that $\frac{1}{2}$ of the array are considered good pivots and the first and last $\frac{1}{4}$ are considered bad pivots. We can use this to calculate our probability of getting a good pivot. We can do this by checking all of the groups of three that we might select from our array and putting them into 3 categories, those categories being a bad pivot on the lower part denoted as $L$, a bad pivot on the upper part denoted as $U$, and finally a good or two good pivots in the middle denoted as $M$. From before we can see that the probability of $L$ is $\frac{1}{4}$, $U$ is $\frac{1}{4}$, and $M$ is $\frac{1}{2}$. We can then add these all up to get $\frac{11}{16}$ or $68.75$% chance of selecting a good pivot.