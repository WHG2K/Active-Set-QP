# Active-Set QP

Implementation of the Active-Set method for inequality-constrained Quadratic Programming (QP).

Problem form (text only):  
min 1/2 x^T G x + c^T x  subject to  A x >= b

- **Course**: IEMS 450-2  
- **Author**: Wenhao Gu  
- **Notebook**: `Active_Set_QP.ipynb` (main file)  
- **Preview**: `Active_Set_QP_doc.html` (exported from the notebook)

## Features
- Solves QPs with constraints of the form `A x >= b`
- Maintains and updates a working set (active constraints)
- Iteration logs: objective value, step size, direction norm, working-set changes

## Usage (inside the notebook)

```python
# Given G, c, A, b, initial point x0, and initial working set W0
qp = ActiveSetQP(G, c, A, b, x0, W0, verbose=2)
x_sol, lambda_sol, W_sol, status, stats = qp.solve()

print("status:", status)
print("x*:", x_sol)
print("final working set:", W_sol)
```

**Return variables**
- `x_sol`: solution vector  
- `lambda_sol`: Lagrange multipliers  
- `W_sol`: final working set (active constraints)  
- `status`: solver status (e.g., "optimal")  
- `stats`: iteration count, timing, etc.
