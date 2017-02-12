# EM-algorithm by javascript
## 
This is one of application for EM-algorithm to resolve user cluster from user-item matirx model.
From user-item matrix, the algorithm calculates each user's Expectation and likelihood maximized in them on latent classes.
Got convergence, we get to know the best class for each user. 

## code-example

see example.html for detail.
A Typical protocol is following.
```
  //  First ; set number of classes
  emalgorithm.initNUMCLASS(NUMCLASS);

  // Second ; create user-item table
  emalgorithm.add('u1','X','1');
  emalgorithm.add('u2','Y','1');
  emalgorithm.add('u3','Z','1');

  // Third ; initialize variables
  emalgorithm.initPIcollection();
  emalgorithm.initW()
  emalgorithm.initE()

  // run
  likelihood,loop = emalgorithm.exec(100,1-e100);


```
## input/output
In simple example as input,no doubt each user will be assigned for which class.
```
#user,item,value
A,X,o
B,Y,o
C,Z,o
```

click *Load* botton,and *Compute All*
execute and output result

```
L=-3.295836866004329,loop=16
user distribution
0:A
1:B
2:C
```
*L* is likelihood,*loop* is number of iteration.
following example, each latent class information.

```probabilitis of all items```

**[class=0]**
```
showing class:0
W=0.3333333333333333
item	value	probability
X	null	3.502263707236601e-182
X	o	1
Y	null	1
Y	o	3.245522044729311e-182
Z	null	1
Z	o	2.567416625072901e-183
```

**[class=1]**
```
showing class:1
W=0.3333333333333333
item	value	probability
X	null	1
X	o	4.281058298224786e-137
Y	null	9.452803266684445e-137
Y	o	1
Z	null	1
Z	o	5.17174496845966e-137
```

**[class=2]**
```
showing class:2
W=0.3333333333333333
item	value	probability
X	null	1
X	o	1.0678236090073944e-45
Y	null	1
Y	o	8.518031807275037e-44
Z	null	8.624814168175777e-44
Z	o	1
```

clicking *Compute one iteration* bring a result for execution of Estep,Mstep once.


## 
input to add some user and item, and you can get result you expect intuitively.

This code is simply implemented. More the number of items bring underflow probability.


