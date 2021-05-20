# Representation of policy

## Decision Tree

A policy π(s) can also be represented with a decision tree, which has a more compact representation by exploiting context-specific independencies. Decision trees allow us to calculate the values of the minimum set of variables needed to define the next action to execute. Such property can be important when the policy is run in an environment where calculating the value of a variable has a cost.

Figure 4.5 shows the representation of an optimal policy using decision tree and the leaf nodes of the decisision tree are actions.

<image src="images/DT-policy.png" width="80%" height="80%">
  
  
 For detailed, see https://learning-oreilly-com.tudelft.idm.oclc.org/library/view/markov-decision-processes/9781118620106/xhtml/Chapter04.html
