# Research Assistant (Answers to the questions)

## Recursion for Fibbonacci is bad
The reason for speed difference is: calling a function means putting the current function values and the call parameters on the stack, then after the function call finished the return value is put on the stack, and the last calling function is loaded by loading its state from the stack, and the returned value is read, too, to process it.


The compiler allocates new Activation Record (Just think as an ordinary Stack) for that new function. That stack is used to keep your states, variables, and addresses. The compiler creates a stack for each function, and this creation process continues until the base case is reached. So, when the data size becomes larger, the compiler needs a large stack segment to calculate the whole process. Recursion may cause memory overflow if your stack space is large, and is also inefficient in cases where the same value is calculated again and again.

In recursion, the stack segment is being raised during run-time. The compiler does not know how much memory will be occupied during compile time.



## Why Stock to Flow Model is Bad 
Stock to Flow Ratio is the amount of a commodity held in inventories divided by the amount produced annually. It is a measure of the abundance of the commodity. The higher the stock to flow ratio, the more scarce a commodity is and vice versa.

The S2F ratio of an asset is calculated by dividing the current supply by the number of new units of that asset produced in a given period. Bitcoin S2F equals its supply divided by the number of new coins per given period. 

Bitcoin stock to flow model (S2F) is one of many price forecasting model that is used to predict the future price of bitcoin, popularised by a pseudonymous investor under the Twitter account PlanB.
The bitcoin S2F model compares the correlation between the prices and the stock to flow of gold and silver to argues the same for bitcoin.
It states that certain precious metals have maintained a monetary role throughout history because of their unforgeable costliness and low rate of supply.

For example, gold is valuable both because new supply (mined gold) is insignificant to the current supply and because it is impossible to replicate the vast stores of gold around the globe. PlanB then argues that this same logic applies to Bitcoin, which becomes more valuable as new supply is reduced every four years. 

Plan B’s argument invariably implies that the value of bitcoin would keep increasing as its supply decreases and therefore increasing its scarcity which is a measure of S2F.

This model seems all good on paper; however, when tested against reality, this model fails. 
The problem with this model starts from first assuming that scarcity denotes value.
Just because a commodity is scarce, it doesn’t always mean it is valuable. It is the demand for a commodity that determines the price. For example, there are plentiful reserves of crude oil, but the demand is so high that the price has not fallen until recent when the demand fell.

Secondly, the premise of using the S2F ratio to determine the price of bitcoin. The model uses gold as an example, however, not only that the S2F of gold is not the only determinant of the price of gold, the S2F of gold is sometimes uncorrelated to gold's price.

Not only that the S2F model doesn’t account for the prices other cryptocurrencies, it also fails to explain why metals like to explain why palladium(S2F=) and platinum (S2F=0.4) are often worth more than gold despite having tiny stock-to-flow ratios. 

Conclusively, the S2F model attempt to predict the price of bitcoin looks good but there are alot of problems with the hypothesis, from using gold’s S2F ratio as a price determinant where gold’s price isn’t determined by its S2F. The problem of not solving for other cryptocurrencies. These among other factors male the Bitcoin S2F model not reliable.

#Code for checking Proth prime
```
#include <bits/stdc++.h> 
using namespace std; 

// Utility function to check power of two 
bool isPowerOfTwo(int n) 
{ 
	return (n && !(n & (n - 1))); 
} 

// Function to check if the 
// Given number is Proth number or not 
bool isProthNumber(int n) 
{ 

	int k = 1; 
	while (k < (n / k)) { 

		// check if k divides n or not 
		if (n % k == 0) { 

			// Check if n/k is power of 2 or not 
			if (isPowerOfTwo(n / k)) 
				return true; 
		} 

		// update k to next odd number 
		k = k + 2; 
	} 

	// If we reach here means 
	// there exists no value of K 
	// Such that k is odd number 
	// and n/k is a power of 2 greater than k 
	return false; 
} 

// Driver code 
int main() 
{ 

	// Get n 
	int n = 25; 

	// Check n for Proth Number 
	if (isProthNumber(n - 1)) 
		cout << "YES"; 
	else
		cout << "NO"; 

	return 0; 
}
```



