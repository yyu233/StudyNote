[Ref](https://math.stackexchange.com/questions/21100/importance-of-matrix-rank)   
A rank of the matrix is probably the most important concept you learn in Matrix Algebra. There are two ways to look at the rank of a matrix. One from a theoretical setting and the other from a applied setting.

From a theoretical setting, if we say that a linear operator has a rank 𝑝, it means that the range of the linear operator is a 𝑝 dimensional space. From a matrix algebra point of view, column rank denotes the number of independent columns of a matrix while row rank denotes the number of independent rows of a matrix. An interesting, and I think a non-obvious (though the proof is not hard) fact is the row rank is same as column rank. When we say a matrix 𝐴∈ℝ𝑛×𝑛 has rank 𝑝, what it means is that if we take all vectors 𝑥∈ℝ𝑛×1, then 𝐴𝑥 spans a 𝑝 dimensional sub-space. Let us see this in a 2D setting. For instance, if

𝐴=(1224)∈ℝ2×2 and let 𝑥=(𝑥1𝑥2)∈ℝ2×1, then (𝑦1𝑦2)=𝑦=𝐴𝑥=(𝑥1+2𝑥22𝑥1+4𝑥2).

The rank of matrix 𝐴 is 1 and we find that 𝑦2=2𝑦1 which is nothing but a line passing through the origin in the plane.

What has happened is the points (𝑥1,𝑥2) on the 𝑥1−𝑥2 plane have all been mapped on to a line 𝑦2=2𝑦1. Looking closely, the points in the 𝑥1−𝑥2 plane along the line 𝑥1+2𝑥2=𝑐=const, have all been mapped onto a single point (𝑐,2𝑐) in the 𝑦1−𝑦2 plane. So the single point (𝑐,2𝑐) on the 𝑦1−𝑦2 plane represents a straight line 𝑥1+2𝑥2=𝑐 in the 𝑥1−𝑥2 plane.

This is the reason why you cannot solve a linear system when it is rank deficient. The rank deficient matrix 𝐴 maps 𝑥 to 𝑦 and this transformation is neither onto (points in the 𝑦1−𝑦2 plane not on the line 𝑦2=2𝑦1 e.g. (2,3) are not mapped onto, which results in no solutions) nor one-to-one (every point (𝑐,2𝑐) on the line 𝑦2=2𝑦1 corresponds to the line 𝑥1+2𝑥2=𝑐 in the 𝑥1−𝑥2 plane, which results in infinite solutions).

An observation you can make here is that the product of the slopes of the line 𝑥1+2𝑥2=𝑐 and 𝑦2=2𝑦1 is −1. This is true in general for higher dimensions as well.

From an applied setting, rank of a matrix denotes the information content of the matrix. The lower the rank, the lower is the "information content". For instance, when we say a rank 1 matrix, the matrix can be written as a product of a column vector times a row vector i.e. if 𝑢 and 𝑣 are column vectors, the matrix 𝑢𝑣𝑇 is a rank one matrix. So all we need to represent the matrix is 2𝑛−1 elements. In general, if we know that a matrix 𝐴∈ℝ𝑚×𝑛 is of rank 𝑝, then we can write 𝐴 as 𝑈𝑉𝑇 where 𝑈∈ℝ𝑚×𝑝 and is of rank 𝑝 and 𝑉∈ℝ𝑛×𝑝 and is of rank 𝑝. So if we know that a matrix 𝐴 is of rank 𝑝 all we need is only 2𝑛𝑝−𝑝2 of its entries. So if we know that a matrix is of low rank, then we can compress and store the matrix and can do efficient matrix operations using it. The above ideas can be extended for any linear operator and these in fact form the basis for various compression techniques. You might also want to look up Singular Value Decomposition which gives us a nice (though expensive) way to make low rank approximations of a matrix which allows for compression.

From solving a linear system point of view, when the square matrix is rank deficient, it means that we do not have complete information about the system, ergo we cannot solve the system.
