# hyperloglog
We want to compare the performance of hyperloglogs in finding the cardinality of a set to the python data structure dictionary. The ipython notebook allowing comparisons is available in the repository complete with more detailed explanation of its functionality and testing. Python dictionaries are very straightforward and so do not require their own notebook. The following numbers were calculated by taking the mean time over 100 trials: 

## Cardinality (1000000 elements)
```
trials = []
for j in range(100):
    d = {} 
  for i in range (1000000):
      d[i] = 1
  start_time = time.time()
    x = len(d)
    timex = time.time() - start_time
    trials.append(timex)
np_trials = np.array(trials)
print np.mean(np_trials), np.std(np_trials)
```

mean time = 1.24 *10^(-5) seconds 
std = 1.06*10^(-5)s 
## Addition of an element (1000000 + 1 elements) 
```
trials = []
for j in range(100):
    d = {} 
  for i in range (1000000):
      d[i] = 1
  start_time = time.time()
    d[i+1] = 1 
    timex = time.time() - start_time
    trials.append(timex)
np_trials = np.array(trials)
print np.mean(np_trials), np.std(np_trials)
```
mean time = 1.06* 10^(-5)s 
std = 7*10^(-6) s 


