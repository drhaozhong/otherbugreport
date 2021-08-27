# Enriching Compiler Testing with Real Program from Bug Report

## Project summary

A key problem of compiler testing is to generate test  programs. Only after test programs are generated, other approaches can check whether compilation results are as expected, adn thus detect bugs in compilers. The prior approaches either generate random programs or mutate available programs. In particular, random-based approaches [1] generate random programs, and mutation-based approaches [2,3] mutate known programs to generate more test programs. Despite their incredible success, their generated test programs are still limited. For example, their generated test programs are not real code, and it is challenging to generate programs in complicated programming languages like C++. 

In our project, we identify another source to generate test programs. For the first time, we identify that test programs from bug reports are an effective source to detect compiler bugs. WE implemented a tool called LERE to extract test programs from bug reports of other compilers; compile test programs with default settings; and compare compilation results to detect bugs in compilers. 


## Experience report

Since April 2018, we have conducted a field study with our tool, LERE. The purpose of our study is to detect bugs in the C++ component of gcc and clang. Most of our found bugs are accept-invalid bugs and reject-valid bugs, which are not reported by the prior approaches [1-3]. Although some found bugs appeared in other compilers, we do find new bugs that never appear in any compilers. As our extracted test programs are tricky and challenging, they can reveal bugs that are quite different from their original bug reports. 

We appreciate the developers of gcc and clang, for their efforts in analyzing and repairing our reported bugs. The difference in the number of found bugs is not an indicator for which compiler is better or not. In a way, it reflects their concerns of the quality and the compatibility of compilers.

Our found [gcc bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/gccbugs.txt) and [clang bugs](https://anonymous.4open.science/repository/bae36f81-a4bc-46fa-bea5-c04af4271d4d/clangbugs.txt).


## Reference

[1] X. Yang, Y. Chen, E. Eide, and J. Regehr. Finding and understanding bugs in C compilers. In Proc. PLDI, pages 283-294, 2011.

[2] V. Le, M. Afshari, and Z. Su. Compiler validation via equivalence modulo inputs. In Proc. PLDI, pages 216-226, 2014.

[3] V. Le, C. Sun, and Z. Su. Finding deep compiler bugs via guided stochastic program mutation. In Proc. OOPSLA, pages 386-399, 2015.

