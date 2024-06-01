# c-Questions

Q:2 In a world where numbers have magical properties, the kingdom of Numeria has a special tradition.
Every decade, a sacred scroll with a unique number sequence is uncovered from the ancient ruins. This sequence is
believed to hold the key to unlocking hidden knowledge and powers.
The latest scroll revealed the sequence: 2313131346465.
The wise sorcerers of Numeria believe that understanding the frequency of each digit in this sequence is crucial to
deciphering the magical incantation it holds.
The king has called upon the brightest minds in the kingdom to analyze the sequence and determine the frequency of
each digit.
Problem Statement
Given the number sequence 2 3 1 3 1 3 1 3 4 6 4 6 5, you need to write a program to count the frequency of each digit in
the sequence. Your task is to determine how many times each digit (from 0 to 9) appears in the sequence.
Ans:

    #include <bits/stdc++.h>
    using namespace std;

    int main ()
    {
    vector < int >arr = {2, 3, 1, 3, 1, 3, 1, 3, 4, 6, 4, 6, 5};
    map<int,int>count;
    for(auto it: arr){
        count[it]++;
    }
    for(auto it:count){
        cout<<it.first<<" "<<it.second<<"\n";
    }
    return 0;
    }

-----------------------------------------------------------------------------------------------------
Q:3Calculate the time complexity :

    a) for(int i=2;i<=n;i=i*i)
    {

    .......
    }

    b)for(int i=n;i>=2;i=sqrt(i))
    {

    .......
    }
Ans:
The time complexity of the first loop is 𝑂(log log 𝑛)
The time complexity of the second loop is O(log log n).

-------------------------------------------------------------------------------------------------
Q:4In the bustling town of Sweetville, there is a famous ice cream parlor known as "Circular Scoops." This parlor is
renowned for its unique way of serving ice cream flavors. Each day, they arrange their flavors in a circular display, and
they have a special promotion: customers get a special discount based on a unique calculation involving the positions
of the ice cream flavors.

Here's how the promotion works: for each flavor, the customer gets a discount based on the product of the price of
the current flavor and the price of the flavor three positions ahead in the circular display.
The ice cream flavors and their prices are arranged in a circular array as follows: 2,3,4,5,6 (prices in dollars).
Problem Statement

Given a circular array of integers representing the prices of ice cream flavors, you need to calculate the special
discount for each flavor. The discount for each flavor is determined by multiplying the price of the current flavor by
the price of the flavour of its two adjacent left and right.
Write a function to perform this operation and return a list of the discounts.
Output: [18, 8, 15, 24, 10]

Ans:

    #include <bits/stdc++.h>
    using namespace std;

    vector<int> calculate_discounts(const std::vector<int>& prices) {
    int n = prices.size();
    vector<int> discounts(n);

    for (int i = 0; i < n; ++i) {
        int nextindex = (i + 3) % n;
        discounts[i] = prices[i] * prices[nextindex];
    }

    return discounts;
    }

    int main() {
    vector<int> prices = {2, 3, 4, 5, 6};
    vector<int> discounts = calculate_discounts(prices);

    cout << "Discounts: ";
    for (int discount : discounts) {
        cout << discount << " ";
    }
    cout << std::endl;

    return 0;
    }
