```mermaid
graph TD
A[Start]-->B[Input]
B-->C[CalcW]
C-->D[S=Xin]
D-->E{iter<max?}
E-->|Y|H[Sold=S]
H-->I[SignW]
I-->J{Stable?}
J-->|Y|F[Output]
F-->G[End]
J-->|N|K[iter++]
K-->E
E-->|N|F
```
