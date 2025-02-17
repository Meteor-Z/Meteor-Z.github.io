# GCD

```Mermaid
graph TD;
    A -->|业务逻辑| C[Queue 2]
    A -->|业务逻辑| D[Queue 3]
    A -->|业务逻辑| E[Queue 4]
    A[Queue] -->|业务逻辑| B[main Queue]
    C --> G[Thread 2]
    D --> H[Thread 3]
    E --> I[Thread 4]
    B --> F[main Thread]
    subgraph Thread Pool
        G
        H
        I
    end
```

RunLoop相关图片

```Mermaid
graph TD;
    A[Runloop] -->|Timer / performSelector| B[Main Thread]
    GG[Runloop] -->|NSThread| C[Thread 1]
    N[Runloop] -->|NSThread| D[Thread 2]
    Q[Runloop] -->|NSThread| E[Thread 3]
    B --> F[Main Queue]
    C --> G[Queue 1]
    D --> H[Queue 2]
    E --> I[Queue 3]
    F --> J[业务逻辑1]
    G --> K[业务逻辑2]
    H --> L[业务逻辑3]
    I --> M[业务逻辑4]

    subgraph RunLoop
        A
        GG
        N
        Q
    end
    subgraph Thread Pool
        C
        D
        E
    end

    subgraph Queue
        F
        G
        H
        I
    end

    subgraph GCD / NSOperation
        J
        K
        L
        M
    end
```
