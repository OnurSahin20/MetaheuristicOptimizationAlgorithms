# MetaheuristicOptimizationAlgorithms
This repository contains 4 metaheuristic search algorithms 1) Genetic Algorithm 2) Differential Evolution 3) Cuckoo Search 4) Harmony Search and I used minimization problem which called the Michalewicz test function for the performance of algorithms. I don't test algorithms carefully, therefore somewhere in the codes, there might be some flaws.I've been trying to write these codes in Python as efficiently as possible. My request you who will look into codes please criticize me and show my mistakes or better way to write code. Contact with me at ogungorsahin@gmail.com 
Example
    
    import numpy as np
    from GA_functions import genetic_algorithm
    import time
    import matplotlib.pyplot as plt
    
    start = time.perf_counter()
    nd = 5
    lb = np.array([0] * nd)
    ub = np.array([np.pi] * nd)
    P = 50
    Generation = 2500
    m = 15
    minprob = True
    Pc = 0.85
    Pm = 0.03


    def michalewicz(xx):
        mm = 10
        n1 = np.shape(xx)[0]
        n2 = np.shape(xx)[1]
        outputs = np.zeros((n1, 1))
        for i in range(n1):
            s = 0
            for j in range(1, n2 + 1):
                s = s + np.sin(xx[i, j - 1]) * (np.sin(j * xx[i, j - 1] ** 2 / np.pi)) ** (2 * mm)
            outputs[i, 0] = -s
        return outputs


    list1 = genetic_algorithm(P, nd, lb, ub, michalewicz, Generation)
    list2 = range(0, Generation)
    end = time.perf_counter()
    print('Process time is {}'.format(end-start))
    plt.plot(list2, list1, label="graph", color="red")
    plt.semilogx()
    plt.xlabel("GENERATİON", color="blue")
    plt.ylabel("OBJECTİVE VALUES", color="blue")
    plt.legend()
    plt.show()

 

Exampes also avaliable in the given codes. Hope this repository will be useful for those interested

