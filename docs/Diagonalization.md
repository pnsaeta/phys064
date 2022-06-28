# Matrix Diagonalization

[Back to the top](LinearAlgebra.md)

A **similarity transformation** of a square matrix $$\mat{A}$$ is a product of the form
\\[
  \mat{D} = \mat{S}^{-1} \vdot \mat{A} \vdot \mat{S}
\\]
for some square matrix $$\mat{S}$$ such that $$\mat{D}$$ is a diagonal matrix (i.e. has nonzero elements only along the main diagonal). A similarity transformation represents a change of basis (a rotation) that allows the effect of $$\mat{A}$$ to be expressed in simplest terms.

Applying $$\mat{S}^{-1}$$ to the right and $$\mat{S}$$ to the left of this equation gives
\\[
  \mat{S} \vdot \mat{D} \vdot \mat{S}^{-1} = \mat{A}
\\]
Evidently, $$\mat{D}$$ expresses the same action as $$\mat{A}$$, but in a basis where its only effect is to stretch each dimension by a (potentially) different amount. The matrix $$\mat{S}^{-1}$$ transforms the basis of $$\mat{A}$$ into the “natural” diagonal basis of the transformation, and $$\mat{S}$$ transforms back from this basis to the basis of $$\mat{A}$$.

A similarity transformation preserves the determinant of a matrix.

## Eigenvalues and Eigenvectors

A rank-$$n$$ square matrix $$\mat{A}$$ transforms a vector in $$\mathbb{R}^n$$ to another vector in $$\mathbb{R}^n$$; in general, the transformed vector points in a different direction than the original vector and has different magnitude. However, an eigenvector satisfies
\\[
    \mat{A} \vdot \vb{x} = \lambda \vb{x}
\\]
for some *scalar* **eigenvalue** $$\lambda$$. That is, the action of transformation $$\mat{A}$$ on an **eigenvector** $$\vb{x}$$ produces a copy of $$\vb{x}$$ scaled by the **eigenvalue** $$\lambda$$. Diagonalizing a matrix $$\mat{A}$$ consists in finding the similarity transformation that puts all its eigenvalues along the main diagonal.

Certain kinds of matrices are guaranteed to be diagonalizable and to have a set of **eigenvectors** that span their $$n$$-dimensional space. These include

+ real symmetric matrices
+ Hermitian (complex self-adjoint) matrices

Eigenvectors corresponding to different eigenvalues are guaranteed to be orthogonal:
\begin{align}
  \mat{H}\vdot \vb{x}_1 &= \lambda_1 \vb{x_1} &\qquad \vb{x}_2\vdot\mat{H}\vdot\vb{x}_1 &= \lambda_1 \vb{x}_2 \vdot \vb{x}_1 \\\ 
  \mat{H}\vdot \vb{x}_2 &= \lambda_2 \vb{x_2} &\qquad \vb{x_1}\vdot\mat{H}\vdot\vb{x_2} &= \lambda_2 \vb{x}_1 \vdot \vb{x}_2
\end{align}
If $$\mat{H}$$ is a real symmetric matrix, then subtracting the two rows gives
\\[
    \vb{x}_2\vdot\mat{H}\vdot\vb{x}_1 - \vb{x_1}\vdot\mat{H}\vdot\vb{x_2} = (\lambda_1-\lambda_2) \vb{x}_1 \vdot \vb{x_2}
\\]
But $$(\vb{x}_2 \vdot \mat{H} \vdot \vb{x}_1)^{\rm T} = \vb{x}_1 \vdot \mat{H}^{\rm T} \vdot \vb{x}_2 =
 \vb{x}_1 \vdot \mat{H} \vdot \vb{x}_2 $$ since $$\mat{H}$$ is symmetric. Therefore, the left-hand side vanishes, and since $$\lambda_1 \ne \lambda_2$$, it must be true that $$\vb{x}_1\vdot\vb{x}_2 = 0$$. So, *eigenvectors corresponding to distinct eigenvalues are orthogonal*. The proof for Hermitian matrices is similar.

Since a scalar multiple of an eigenvector is also an eigenvector, it is possible to find a set of orthonormal eigenvectors that span the vector space of real symmetric matrices and also of Hermitian matrices.
