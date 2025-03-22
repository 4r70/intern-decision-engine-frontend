# Conclusion for TICKET-101

## Things you excelled at
### Code organization
- Code is clean and clear
- Clear package structure
- 
### Documentation
- Detailed Javadocs
- Good documentation for exceptions
- 
### Input validation
- Input is validate BEFORE sending it to the backend
- Different exceptions for different validation errors

## Places for improvement
### Scoring algorithm (major)
The calculation of the credit score was not implemented.
The requirements specified this calculation:
`credit score = ((credit modifier / loan amount) * loan period) / 10`
You tried to do something similar but that is not correct.
```java
private int highestValidLoanAmount(int loanPeriod) {
    return creditModifier * loanPeriod;
}
```
This changes the behaviour of the application massively. Therefore, I had to fix your implementation of the scoring 
algorithm.

### SOLID principles
#### Single responsibility principle
- The decision engine has quite a lot of responsibilities like validation, determination and calculation.
- Breaking the decision engine down to more classes could help with that.

### Tiny mismatches between the ticket and code, especially the loan period
There are some minor issues, for example the Loan Period slider has a minimum value label of 6 months even though the 
sliders' minimum value is 12 months. The same is with the maximum loan period. It is supposed to be 48 months but the 
label AND slider max value go up to 60 months. Similar typos also extend to javadocs, for example the javadoc for the 
function `calculateApprovedLoan()`.

## Conclusion
While you had some great ideas and code, it fell a bit short of the key requirements. Especially the credit score 
calculation requirement. This also has a major impact on business logic. 

You could also try to break down your code more. In some places you have handled it well, but for example in the 
`DecisionEngine` you have a class with too many responsibilities. 

Don't let this discourage you, we all had to learn! Making mistakes is the best way to learn:)
