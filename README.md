# Clean-Code-Notes
Notes on the book Clean Code

## Names
 - If we require a comment to explain name of a variable, then it is not named correctly.
 - Pick a name that people can pronounce.
 - Avoid encodings while picking names i.e. a `string` name should not be named `nameStr` to display that it is a `string`.
 - Choose parts of speech well while picking names. `isSet` should logically return a `boolean` as it asks a question.
 - `Variables` with smaller scope should have smaller names while `variables` with longer scope should have longer names
 - It is opposite with `functions`. `Functions` with longer scope i.e. `public` should have smaller names as they are going to be called from multiple places.
 - `Functions` with smaller scope i.e. `private` should have larger names as they are going to be called from a smaller context.
 - Classes follow the same rules as that of functions in naming. 
 - Derived classes get appended with adjectives to display derivition. `Account -> SavingsAccount`.

## Functions
 - `if/else` chains in a function should be replaced with well-named predicate function.
 - Ideal function size should be 4-6 lines where additional logic should be further function calls.
 - If a function exceeds the ideal function size and has a lot of complicated logic then it should be transformed to a `class` with its own `invoke` method.
 - This `class` should be built of smaller functions that are called from `invoke` function.
 - Large functions are where classes go to hide!
 - As a part of refactoring functions in legacy code, rely on tests that check the behaviour of legacy code. Perform the refactoring in a `TDD` manner.
 - If a function is composed of multiple sections, its doing more than 1 thing. 
 - If a function manipulates more than 1 level of abstraction, its doing more than 1 thing.
 - In order for a function to do just one thing, it should not cross one level of abstraction.
 - If you are unable to extract a functionality from a function, then originally function was not doing just one thing.
 - Extract as long as you can extract no more i.e. `Extract till you drop`.

## Comments
 - Comments don't make up for bad code.
 - While adding a comment, always think if there is a way to avoid comment and make the code self explanatory.
 - Treat comment as a failure.
 - The only good comment is the comment you found a way not to write.
 - If you end up writing comment, try to ensure that the comment does not goes out of sync with the actual code in future iterations.
 - Comments can act as warning. If you want someone to not change a code or provide instructions for reuse of code, warning comments might come in handy.
 - `TODO` comments can be used to plan the future changes of the code. Make sure to scan the codebase regularly for `TODO` and put an effort to reduce `TODO` with each iteration.
 - Comments can be used to amplify changes that might seem minor to others such as `trim`, `length - 1` etc.
 - For public facing APIs, have a very clean and clear `docstring`. `Javadoc` for example.
 - Avoid redundant comments at all cost. A comment that provides no extra information in addition to reading the actual code should be removed.
 - A comment that contradicts the behavior of actual code should be considered misleading comment. They create confusion for anyone reading the code.
 - Always prefer for a scenario where you can remove a comment with a function call or a variable. 
```
// Check if customer is eligible for discount
if (customer.age > 25 && customer.salary > 20000 && customer.salary < 60000) 
                               
                               VS
                               
if (customer.isEligibleForDiscount()) 

                               OR 
                               
if (checkIfCustomerIsEligibleForDiscount(customer)
```
 - Don't have comments for things that can be taken care by a version control system. Ex: comments about author's name or date the change was added or commit hash
 - Don't have commented out code. Delete it and if required in future, you can fetch it from git based on the commit hash when it was deleted.
 - Add a comment as local to the code it describes. Don't describe global state in the comments.
 - Make sure the comments have a clear connection with the code. Your comment should not confuse the reader about the code.

## Formatting
 - Having badly formatted code gives an impression to the reader that other parts of the code will also have some hidden discrepencies.
 - Having a set rules of formatting for the project and an automated tool to enforce the formatting helps to maintain the codebase.
 - Prefer small size over larger files.
 - Consider the newspaper as an example for maintaining a file. The filename should be clear enough to give a high-level overview of what the code does. As we go down in the file the lower level details should be exposed in the linear order of file depth.
 - Use blank lines judicially to describe separation of concepts and new ideas in a code.
 - Lines of code that are tightly linked should appear together without any break such as a blank line or a comment.
 - Concepts that are closely related should be kept vertically close to each other.
 -  
