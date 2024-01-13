```R
#Here are the two proposals to include in a marketing campaign:
Design A
![image](https://github.com/jkim2252666/text_analysis/assets/67861374/eb1ce4bf-3e78-4cee-b9c0-28180db2430e)

Design B
![image](https://github.com/jkim2252666/text_analysis/assets/67861374/9ede310b-0d03-46af-8ab7-4b13c1a7f96d)

Assumes that two proposed images were exposed to two randomly assigned groups through an SNS. Below is the test result.

1020 users were exposed to Design A and 218 clicked it. The click-through rate is 21.37%.
1010 users were exposed to Design B and 150 clicked it. The click-through rate is 14.85%.

Can I claim that the click-through rate for design A is different from the rate for design B?
```

```R
# comparison of the two groups described in the case
prop.test(x = c(218,150), n = c(1020,1010),conf.level=0.95)
```

    
    	2-sample test for equality of proportions with continuity correction
    
    data:  c(218, 150) out of c(1020, 1010)
    X-squared = 14.104, df = 1, p-value = 0.0001729
    alternative hypothesis: two.sided
    95 percent confidence interval:
     0.03085083 0.09957045
    sample estimates:
       prop 1    prop 2 
    0.2137255 0.1485149 
    



```R
# Generate hypothetical data
# Assume that observations, binary outcomes 1 or 0, and conversion rate are below
set.seed(123)
group_a <- rbinom(1020, size=1, prob = 0.27)  # Conversion rate for group A: 20%
group_b <- rbinom(1010, size=1, prob = 0.25)  # Conversion rate for group B: 25%

# Perform A/B test (Assuming data is Bernoulli distributed)
prop.test(x = c(sum(group_a), sum(group_b)), n = c(length(group_a), length(group_b)))
```


    
    	2-sample test for equality of proportions with continuity correction
    
    data:  c(sum(group_a), sum(group_b)) out of c(length(group_a), length(group_b))
    X-squared = 1.3106, df = 1, p-value = 0.2523
    alternative hypothesis: two.sided
    95 percent confidence interval:
     -0.01573578  0.06195982
    sample estimates:
       prop 1    prop 2 
    0.2656863 0.2425743 
    



```R

```
