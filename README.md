# Learning bug report of other compilers

## Project summary

Since April 2018, we have conducted a field study with our tool, LERE. The purpose of our study is to detect bugs in the C++ component of gcc and clang. The prior approaches [1-3] have detected hundreds of bugs in gcc and clang. Despite their incredible success, it is still quite difficult to detect compiler bugs. For example, a recent empirical study [4] shows that the C++ component has many bugs, but most tools can generate code samples only in C, since it is more challenging to detect bugs in C++ [2, 4].

In our project, we propose a novel approach to enrich the test inputs of compilers. Our basic idea is to learn code samples from bug reports of other compilers. Our tool, LERE, is able to extract code samples that appear in attachments and are embedded in natural language descriptions/comments. These code samples are often short, real, and provide insights on why a compiler is buggy. Although they are used to illustrate bugs in a compiler, programmers of other compilers are often not aware of such code samples. 

In our study, most of our found bugs are accept-invalid bugs and reject-valid bugs, which are not reported by the prior approaches [1-3].

We appreciate the developers of gcc and clang, for their efforts in analyzing and repairing our reported bugs. The difference in the number of found bugs is not an indicator for which compiler is better or not. In a way, it reflects their concerns of the quality and the compatibility of compilers.

Here is the list of our [found bugs](/reportedbug.xlsx).


## Reference

[1] X. Yang, Y. Chen, E. Eide, and J. Regehr. Finding and understanding bugs in C compilers. In Proc. PLDI, pages 283-294, 2011.

[2] V. Le, M. Afshari, and Z. Su. Compiler validation via equivalence modulo inputs. In Proc. PLDI, pages 216-226, 2014.

[3] V. Le, C. Sun, and Z. Su. Finding deep compiler bugs via guided stochastic program mutation. In Proc. OOPSLA, pages 386-399, 2015.

[4] C. Sun, V. Le, Q. Zhang, and Z. Su. Toward understanding compiler bugs in gcc and llvm. In Proc. ISSTA, pages 294-305, 2016.
