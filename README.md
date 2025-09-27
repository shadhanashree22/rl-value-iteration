# VALUE ITERATION ALGORITHM
## AIM
Implement value iteration algorithm to find optimal policy for the altered frozen lake environment.

## PROBLEM STATEMENT
Make alterations in the default frozen lake environment like changing the starting state, goal state and holes in the environment. Further find optimal policy using value iteration.

## VALUE ITERATION ALGORITHM

# Step 1:
Import required libraries for the program.
# Step 2:
Load the frozen lake environment and make changes. 
# Step 3: 
Define the value iteration function.
# Step 4:
Run the function and display the results.

## VALUE ITERATION FUNCTION
### Name: S V SHADHANASHREE
### Register Number: 212223230202
```
def value_iteration(P, gamma=1.0, theta=1e-10):
    V = np.zeros(len(P), dtype=np.float64)
    while True:
      Q=np.zeros((len(P),len(P[0])),dtype=np.float64)
      for s in range(len(P)):
        for a in range(len(P[s])):
          for prob, next_state, reward, done in P[s][a]:
            Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
      if np.max(np.abs(V-np.max(Q,axis=1)))<theta:
        break
      V=np.max(Q,axis=1)
    pi=lambda s: {s:a for s,a in enumerate(np.argmax(Q,axis=1))}[s]
    return V, pi
```

## OUTPUT:
# Optimal Policy
<img width="622" height="187" alt="Screenshot 2025-09-27 112425" src="https://github.com/user-attachments/assets/0395b9b7-f867-44d1-9d9f-dfc99fc35848" />


# Success Rate for the Optimal Policy
<img width="747" height="73" alt="Screenshot 2025-09-27 112432" src="https://github.com/user-attachments/assets/cc224668-6c9c-4e59-a9fb-0345172331b4" />


# Optimal value function 
<img width="591" height="141" alt="Screenshot 2025-09-27 112438" src="https://github.com/user-attachments/assets/d5e5995b-7599-4f62-a6e3-296e4586e2b6" />

## RESULT:
Therefore, value iteration algorithm to find optimal policy for the altered frozen lake environment is successfully implemented.
