# MetaheuristicOptimizationAlgorithms
This repository contains 4 metaheuristic search algorithms 1) Genetic Algorithm 2) Differential Evolution 3) Cuckoo Search 4) Harmony Search and I used minimization problem which called the Michalewicz test function for the performance of algorithms. I don't test algorithms carefully therefore somewhere in the codes which probably be some problems. I've been trying to write codes as efficiently as possible written in Python. My request you who will look into codes please criticize me and show my mistakes or better way to write code. Contact with me at ogungorsahin@gmail.com 
Examples

    def michalewicz(xx):
        mm = 10
        n1 = np.shape(xx)[0]
        n2 = np.shape(xx)[1]
        outputs = np.zeros((n1, 1))
        for i in range(n1):
            s = 0
            for j in range(1, n2 + 1):
                s = s + np.sin(xx[i, j - 1]) * (np.sin(j * xx[i, j - 1] ** 2 / np.pi)) ** (2 * mm)
            outputs[i,0] = -s
        return outputs
    1) Genetic Algorithm 
    nd = 5
    lb = np.array([0] * nd)
    ub = np.array([np.pi] * nd)
    P = 50
    Generation = 2000
    m = 15
    minprob = True
    Pc = 0.85
    Pm = 0.03
    list1 = genetic_algorithm(P, nd, lb, ub, michalewicz, Generation)
    end = time.perf_counter()
    list2 = range(0, Generation)
    plt.plot(list2, list1, label="graph", color="red")
    plt.semilogx()
    plt.xlabel("GENERATİON", color="blue")
    plt.ylabel("OBJECTİVE VALUES", color="blue")
    plt.legend()
    plt.show()
    
    2) DEA
    nd = 10
    CR = 0.5
    nd = 10
    P = 100
    F = 0.8
    Max_iter = 10000
    lb = np.array([0] * nd)
    ub = np.array([np.pi] * nd)
    outputs = dea(P, F, CR, nd, lb, ub, michalewicz, Max_iter)
    list1 = outputs[0]
    list2 = range(0, outputs[1] + 1)
    plt.plot(list2, list1, label="graph", color="red")
    plt.semilogx()
    plt.xlabel("GENERATİON", color="blue")
    plt.ylabel("OBJECTİVE VALUES", color="blue")
    plt.legend()
    plt.show()
    3) Cuckoo Search
    N = 15  # number of nests
    total_iter = 100000
    pa = 0.25
    outputs = cuckoo_search(N, pa, nd, lb, ub, michalewicz)
    Just Cuckoo's parameters differ and rest of codes same as DEA
    4) Harmony Search 
    HMS = 50
    PAR = 0.2
    HMCR = 0.9
    maxiter = 150000
    segment = np.array([300] * nd)
    outputs = harmony_search(HMS,PAR,HMCR,nd,lb,ub,michalewicz,maxiter=maxiter)
    Just Cuckoo's parameters differ and rest of codes same as DEA

Exampes also avaliable in the given codes. Hope this repository will be useful for those interested

