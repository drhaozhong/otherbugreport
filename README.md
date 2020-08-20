# Enriching Compiler Test Program from Bug Report

## Project summary

Since April 2018, we have conducted a field study with our tool, LERE. The purpose of our study is to detect bugs in the C++ component of gcc and clang. The prior approaches [1-3] have detected hundreds of bugs in gcc and clang. Despite their incredible success, it is still difficult to generate sufficient test programs, and is quite difficult to detect some types of compiler bugs. For example, a recent empirical study [4] shows that the C++ component has many bugs, but most tools can generate test programs only in C, since it is more challenging to detect bugs in C++ [2, 4].

In our project, we propose a novel approach to enrich the test programs of compilers. Our basic idea is to learn test programs from bug reports of other compilers. Our tool, LERE, is able to extract test programs that are embedded in natural language descriptions/comments. These test programs are often short, real, and provide insights on why a compiler is buggy. Although they are used to illustrate bugs in a compiler, programmers of other compilers are often not aware of such test programs. 

In our study, most of our found bugs are accept-invalid bugs and reject-valid bugs, which are not reported by the prior approaches [1-3].

We appreciate the developers of gcc and clang, for their efforts in analyzing and repairing our reported bugs. The difference in the number of found bugs is not an indicator for which compiler is better or not. In a way, it reflects their concerns of the quality and the compatibility of compilers.

Our found [gcc bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/gccbugs.txt) and [clang bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/clangbugs.txt).


## Reference

[1] X. Yang, Y. Chen, E. Eide, and J. Regehr. Finding and understanding bugs in C compilers. In Proc. PLDI, pages 283-294, 2011.

[2] V. Le, M. Afshari, and Z. Su. Compiler validation via equivalence modulo inputs. In Proc. PLDI, pages 216-226, 2014.

[3] V. Le, C. Sun, and Z. Su. Finding deep compiler bugs via guided stochastic program mutation. In Proc. OOPSLA, pages 386-399, 2015.

[4] C. Sun, V. Le, Q. Zhang, and Z. Su. Toward understanding compiler bugs in gcc and llvm. In Proc. ISSTA, pages 294-305, 2016.
