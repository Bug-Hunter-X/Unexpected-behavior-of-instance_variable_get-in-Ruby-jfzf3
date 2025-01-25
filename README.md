# Unexpected Behavior of instance_variable_get in Ruby

This repository demonstrates an uncommon bug related to accessing instance variables directly using `instance_variable_get` in Ruby.  The issue arises when the instance variable's value is modified through methods other than the direct accessor methods.  The `instance_variable_get` method might not always reflect the latest value of the instance variable.

## How to reproduce
1. Clone this repository.
2. Run `bug.rb`.
3. Observe the output. You'll notice an unexpected value when calling `instance_variable_get` after modifying the instance variable through other methods such as `instance_variable_set`.

## Solution
The solution involves accessing instance variables through accessor methods (`value` method in this case) rather than directly using `instance_variable_get` and `instance_variable_set`. This ensures that the value you get is consistent with the internal state of the object.

Refer to `bugSolution.rb` for a corrected version.