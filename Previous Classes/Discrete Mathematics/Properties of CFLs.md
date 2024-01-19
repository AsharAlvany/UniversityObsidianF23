**The Pumping Lemma for CFLs**
says that for CFL L there exists a constant n > 0 s.t. for any z $\epsilon$ L with |z| $\ge$ n, z can be written as z = uvwxy satisfying
1. $|vwx| \le n$
2. $|vx| \ge 1$ either v $\ne \epsilon$ or $x \ne \epsilon$ 
3. $\forall i \ge 0 : uv^iwx^iy \  \epsilon \  L$
Example 1: L = $\{ 0^{j^2} | j \ge 0\}$ is not CF
1.  Let n > 0 be an arbitrary constant
2. Let $z=0^{n^2}$ The z $\epsilon$ and $|z| \ge n$
3. Consider an arbitrary factorization of z as z - uvwxy with |vwx| $\le$ n and |vx| $\ge$ 1
4. Let i = 2 Then z' = $uv^2wx^2y = 0^{n^2+l}$ where 1 $\le l = |vx| \le |vwx| \le n$ now $n^2 < |z'| = n^2 + l < n^2 + 2n + 1 = (n+1)^2$  Since |z'\ is strictly between two consecutive perfect squares z' canot be of the form $0^{j^2}$ Thus z' $\not{\epsilon}$ L