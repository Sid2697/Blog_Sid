---
layout: post
title: An Intuitive Introduction to Linear Programming
date: 2020-1-09 14:00:00 +0530
categories: Algorithm
google_analytics: UA-145393252-1
comments: true
---

A linear programming problem can be defined as the task of maximizing or minimizing a linear function subject to some linear constraints. The constraints can be equalities or inequalities.

## What Is It?

Linear programming is a kind of optimization problem where we attempt to maximize (or minimize) an objective function (or linear function) of the decision variables satisfying some linear constraints. Decision variables are the once that can be tuned for getting the optimal solution, they are the variable of interest here. Objective function defines the criterion for selecting the best values of the decision variables. Values obtained by the decision variables must satisfy the set of constraints (as there can be more than one constraints). 

## An Example

Let's go through an example to get a better feel of what actually linear programming (or **linear program**) is. 

Maximize the value

{: style="text-align:center"}
![Base Equation](http://latex.codecogs.com/svg.latex?3x_1+2x_2)

among all the vectors ![condition](http://latex.codecogs.com/svg.latex?(x_1, x_2)\in\rm I\!R^2)

satisfying the constraints

{: style="text-align:center"}
![c3](http://latex.codecogs.com/svg.latex?2x_1+x_2\leq6)

{: style="text-align:center"}
![c4](http://latex.codecogs.com/svg.latex?7x_1+8x_2\leq28)

{: style="text-align:center"}
![c5](http://latex.codecogs.com/svg.latex?x_1\geq0)

{: style="text-align:center"}
![c6](http://latex.codecogs.com/svg.latex?x_2\geq0)

As this linear program is in two-dimensional space, we can visualise it easily and get a feel of it. Plotting the constrtaint ![c3](http://latex.codecogs.com/svg.latex?2x_1+x_2\leq6) (which is a line in two-dimensional space) we get

![Plot 1](../../../../assets/images/Blog_3_fig_1.pdf)

{: style="text-align:center"}
*Fig. 1 Plot for the equation ![c3](http://latex.codecogs.com/svg.latex?2x_1+x_2\leq6)*

Fig. 1 shows the set ![c7](http://latex.codecogs.com/svg.latex?\{x\in\rm I\!R^2:2x_1+x_2\leq6\}) is the half-plane lying below the line ![c3](http://latex.codecogs.com/svg.latex?2x_1+x_2\leq6), similarly each of the remaining equations defines a half-plane. If we plot all the four constraints in a graph and consider the region where all the 4 constraints overlap, we get a convex polygon (also called as solution space):

![Plot 2](../../../../assets/images/Blog_3_fig_2.pdf)

{: style="text-align:center"}
*Fig. 2 Plot for all the four constraints. The line in red show the edges of the polygon and the black dots show the vertices of the polygon formed by overlapping sections from all the four constraints*

Once we have the convex polygon than the question to answer is which part of this polygon maximizes the value of ![Base Equation](http://latex.codecogs.com/svg.latex?3x_1+2x_2)? For this let us consider the equation ![Base Equation](http://latex.codecogs.com/svg.latex?3x_1+2x_2=K). At ![Cond 1](http://latex.codecogs.com/svg.latex?K=0) we get a line passing through the origin as shown in Fig. 3 in black. As we keep on increasing ![K](http://latex.codecogs.com/svg.latex?K) we have many points that line on the line and in the solution space (shown by the section of line in green in Fig. 3), all these points are **feasible solutions** as they satisfy all the constraints but are not the **optimal solution** (as they don't attend the max value). The value of ![K](http://latex.codecogs.com/svg.latex?K) for which we have only one feasible solution is the line which has the optimal value for this problem and hence the solution (shown in blue in Fig. 3). Now if we keep on increasing ![K](http://latex.codecogs.com/svg.latex?K) there will be no value for which all the constraints are satisfied (shown in red in Fig. 3), so, there is only one unique solution in this case. This shows that a linear program may have a single optimal solution, or infinitely many optimal solutions, or none at all. 

![Plot 3](../../../../assets/images/Blog_3_fig_3.pdf)

{: style="text-align:center"}
*Fig. 3 Plot showing various values of K for finding the optimal solution*

In our previous example if we update the constraints to 

{: style="text-align:center"}
![c3](http://latex.codecogs.com/svg.latex?2x_1+x_2\geq6)

{: style="text-align:center"}
![c4](http://latex.codecogs.com/svg.latex?7x_1+8x_2\geq28)

{: style="text-align:center"}
![c5](http://latex.codecogs.com/svg.latex?x_1\leq0)

{: style="text-align:center"}
![c6](http://latex.codecogs.com/svg.latex?x_2\leq0)

The graph in this case is

![Plot 4](../../../../assets/images/Blog_3_fig_4.pdf)

{: style="text-align:center"}
*Fig. 4 Plot when inequalities in all the four constraints is reversed*

As can be seen in Fig. 4, there is no region in the graphs where the half-planes formed by all the four constraints overlap. So, this is a linear program which has no feasible solution, and hence no optimal solution. Such a program is called **infeasible**. 

There can be a case where there are feasible solutions but no optimal solution. In our original example, if we remove the first constraint and reverse the inequality of the second constraint. We have the updated constraints as 

{: style="text-align:center"}
![c4](http://latex.codecogs.com/svg.latex?7x_1+8x_2\geq28)

{: style="text-align:center"}
![c5](http://latex.codecogs.com/svg.latex?x_1\geq0)

{: style="text-align:center"}
![c6](http://latex.codecogs.com/svg.latex?x_2\geq0)

The graph in this case is

{: style="text-align:center"}
![Plot 5](../../../../assets/images/Blog_3_fig_5.pdf)
*Fig. 5 Plot showing a case when the linear program is unbounded. Arrows point in the direction of all the feasible solutions*

As can be seen in Fig. 5, the region where the half-planes formed by all the three constraints overlaps starts from the bold black lines in Fig. 5 and extends up to infinity in the direction pointed by the arrows in Fig. 5. In this case, the objective function can attain arbitrarily large numbers, such a linear program is called to be **unbounded**. In summary, we have seen that a linear program can have one or infinitely many optimal solutions, but it can also be infeasible and unbounded.

## Conclusion

The example we chose to solve in this post consisted of only two variables, this made it easy to solve the linear program graphically. However, it will be difficult to even construct a picture of a linear program with four variables. Linear program in practice often has several thousand variables, rather than two or four. This illustration was useful for understanding the procedures and notions of linear programming, but using this method for solving a linear program is not feasible. There are various methods for solving them which we will discuss in future posts.

### References

- J Matousek and B. Gartner, "Understanding and Using Linear Programming", Springer, 2007
- Optimization Methods taught by Prof C.V. Jawahar at IIIT Hyderabad
