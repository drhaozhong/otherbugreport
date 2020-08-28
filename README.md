# Enriching Compiler Test Program from Bug Report

## Project summary

A key problem of compiler testing is to generate test programs. The prior approaches either generate random programs or mutate available programs. With more test programs, the prior approaches [1-3] have detected hundreds of bugs in gcc and clang. Despite their incredible success, their generated test programs are still limited. For example, their generated test programs are not real code, and it is challenging to generate programs in complicated programming languages like C++. Partially due to the lack of test programs, the prior approaches are insufficient to detect some types of compiler bugs. For example, a recent empirical study [4] shows that the C++ component has many bugs, but most tools can generate test programs only in C [2, 4]. 

In our project, we propose a novel approach, called LERE, to enrich the test programs of the state of the art. LERE does not generate random programs nor mutate available programs. Instead, it proposes a new way to collect test programs. It is based on our following observation. Compilers have bug reports, and such bug reports are embedded with many test programs. These test programs are real code, and are tricky and challenging to compliers. As a result, even if programmers fixed their revealed problems in a compiler, similar problems remain in other compilers.

Our tool, LERE, is able to extract test programs that are embedded in natural language descriptions/comments. These test programs are often short, real, and provide insights on why a compiler is buggy. Although they are used to illustrate bugs in a compiler, programmers of other compilers are often not aware of such test programs. 


## Experience report

Since April 2018, we have conducted a field study with our tool, LERE. The purpose of our study is to detect bugs in the C++ component of gcc and clang. Most of our found bugs are accept-invalid bugs and reject-valid bugs, which are not reported by the prior approaches [1-3]. Although some found bugs appeared in other compilers, we do find new bugs that never appear in any compilers. As our extracted test programs are tricky and challenging, they can reveal bugs that are quite different from their original bug reports. 

We appreciate the developers of gcc and clang, for their efforts in analyzing and repairing our reported bugs. The difference in the number of found bugs is not an indicator for which compiler is better or not. In a way, it reflects their concerns of the quality and the compatibility of compilers.

Our found [gcc bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/gccbugs.txt) and [clang bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/clangbugs.txt).


## Reference

[1] X. Yang, Y. Chen, E. Eide, and J. Regehr. Finding and understanding bugs in C compilers. In Proc. PLDI, pages 283-294, 2011.

[2] V. Le, M. Afshari, and Z. Su. Compiler validation via equivalence modulo inputs. In Proc. PLDI, pages 216-226, 2014.

[3] V. Le, C. Sun, and Z. Su. Finding deep compiler bugs via guided stochastic program mutation. In Proc. OOPSLA, pages 386-399, 2015.

[4] C. Sun, V. Le, Q. Zhang, and Z. Su. Toward understanding compiler bugs in gcc and llvm. In Proc. ISSTA, pages 294-305, 2016.
