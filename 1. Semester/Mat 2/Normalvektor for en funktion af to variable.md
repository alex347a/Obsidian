To find the normal vector to a function $f(x, y)$ with two variables:
## Normalvektor formel
Husk at indsætte punkternes værdi
$$
n=\begin{pmatrix}f_{x}'(x,y) \\ f_{y}'(x,y) \\ -1\end{pmatrix}
$$
$$
n=(\nabla f(x, y),-1) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, -1 \right)
$$
## Step by step:

1. **Understand the context**:  
   The function $f(x, y)$ may represent a surface $z = f(x, y)$. The gradient of $f$ gives a vector normal to this surface.

2. **Compute the gradient**:  
   $$
   \nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, -1 \right)
   $$
   This represents the normal vector to the surface $z = f(x, y)$.

3. **Evaluate the gradient**:  
   Substitute the desired point $(x_0, y_0, z_0)$ into the gradient to find the specific normal vector at that point:
   $$
   \mathbf{n} = \nabla f(x_0, y_0) = \left( \frac{\partial f}{\partial x} \big|_{(x_0, y_0)}, \frac{\partial f}{\partial y} \big|_{(x_0, y_0)}, -1 \right)
   $$

4. **Normalize (OPTIONAL)**:  
   If you need a unit normal vector, normalize $\mathbf{n}$ by dividing it by its magnitude:
   $$
   \mathbf{n}_{\text{unit}} = \frac{\mathbf{n}}{\|\mathbf{n}\|}
   $$
### Example:

Consider the surface $z = f(x, y) = x^2 + y^2$. We will find the normal vector to this surface at the point $(1, 1, 2)$.

1. **Compute the gradient of $f(x, y)$:**
   The gradient of $f(x, y)$ is:
   $$
   \nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, -1 \right)
   $$

   For $f(x, y) = x^2 + y^2$:
   $$
   \frac{\partial f}{\partial x} = 2x, \quad \frac{\partial f}{\partial y} = 2y
   $$

   Thus, the gradient becomes:
   $$
   \nabla f(x, y) = \left( 2x, 2y, -1 \right)
   $$

2. **Evaluate the gradient at $(x_0, y_0, z_0) = (1, 1, 2)$:**
   Substitute $x = 1$ and $y = 1$ into the gradient:
   $$
   \nabla f(1, 1) = \left( 2(1), 2(1), -1 \right) = \left( 2, 2, -1 \right)
   $$

   So, the normal vector at $(1, 1, 2)$ is:
   $$
   \mathbf{n} = (2, 2, -1)
   $$

3. **Normalize the normal vector (IF REQUIRED):**
   The magnitude of $\mathbf{n} = (2, 2, -1)$ is:
   $$
   \|\mathbf{n}\| = \sqrt{2^2 + 2^2 + (-1)^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3
   $$

   The unit normal vector is:
   $$
   \mathbf{n}_{\text{unit}} = \frac{\mathbf{n}}{\|\mathbf{n}\|} = \frac{(2, 2, -1)}{3} = \left( \frac{2}{3}, \frac{2}{3}, -\frac{1}{3} \right)
   $$

### Final Answer:
- Normal vector: $\mathbf{n} = (2, 2, -1)$
- Unit normal vector: $\mathbf{n}_{\text{unit}} = \left( \frac{2}{3}, \frac{2}{3}, -\frac{1}{3} \right)$
