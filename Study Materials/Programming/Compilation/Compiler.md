---
tags:
  - IFJ
  - to_be_finished
---
A compiler **reads, understands, optimizes and converts** a source program (**source files**) into target program (**executable**). To this the compiler goes through several compilation phases.
## Compilation Phases
Each compilation phase are commonly interconnected between each other. Often several walkthrough thought the code for multiple reasons, such as usage of functions before declaration or definition, checking for unused parameters and variables, etc. These phases are:
1. **Lexical** analysis (scanner)
2. **Syntactic** analysis (parser)
3. **Semantic** analysis
4. **Generation of internal code**
5. **Optimization**
6. **Generation of target code**
### Lexical Analysis
- **Input**: Source Code Text
- **Output**: Chain of Tokens
Lexical analyser or **scanner** works through the input source code text and recognizes and classifies **lexemes** that are represented by **tokens** that can hold multiple attributes, such values, names, strings, etc. Each **lexeme** is a small part of the original program that forms one logical unit, such as keywords, numbers, operators, special characters, etc. **Lexemes** are identified by [[Regular Expressions]] and can be detected/identified by a [[Finite Automata]], more specifically the deterministic version.
These scanners and their [[Finite Automata]] are most often created through a switch case in a while cycle. Keywords and identifications are differentiated by a table of keywords. Information about identifications and their parameters are stored in a **symbol table**, which has a [[Stack]] structure.
### Syntactic Analysis
- **Input**: Chain of Tokens
- **Output**: Simulation of Derivation Tree Construction
Syntactic analysis or **parser** checks if the chain of tokens represents a syntactically correctly written project. A program is correct if we can find its **derivation tree**, otherwise it is incorrect. There are two ways of approaching the analysis, either from **down-up** or **up-down**. A deterministic [[Stack Automata]] is most commonly used for the analysis as it is able to use or generate/check [[Context-Free Grammar]], both [[Context-Free Grammar#Derivation Direction|LL-Grammar]] and [[Context-Free Grammar#Derivation Direction|LR-Grammar]].
- **First L** means reading from left to right.
- **Second L** means leftmost derivation.
- **Second R** means rightmost derivation.
#### Syntactic Analysis Up-Down
![[Syntactic Analysis Up-Down]]
#### Syntactic Analysis Down-Up
![[Syntactic Analysis Down-Up]]
### Semantic Analysis
- **Input**: Simulation of Derivation Tree Construction
- **Output**: Abstract Syntactic Tree
Checks semantic aspects of the program, such as checking types, implicit conversions, declaration of functions and variables, division by zero, unused variables, truth values of logic expressions, etc.
#### Syntactic Lead Compilation
Is a version in which the syntactic analyser (parser) also leads:
- Rendering of semantic actions
- Generation of the abstract syntactic tree
### Generation of Internal Code
- **Input**: Abstract Syntactic Tree
- **Output**: Internal Code
Generates an internal code, an internal representation of the program, usually using [[Three Address Code]], which can be easily translated into the target code and it easily optimized.
![[Three Address Code]]
Generation of internal code can be done recursively based on the abstract syntactic tree. A parser that works **down-up** can generate the internal code directly, without creating the abstract syntactic tree, which is then done in **postfix notation**.
### Optimizer
- **Input**: Internal Code
- **Output**: Optimized Internal Code
An optimizer is an optional component that attempts to optimize the internal code to reduce time or space complexity. In the **global** frame is removes **dead code** and in the **local** frame is optimizes code inside a block. The local optimization involves things such as **propagation of constants**, **invariance of expressions in loop**, etc. 
### Generation of target code
- **Input**: Optimized Internal Code
- **Output**: Target Program
The last step is to generate the target program (code) from the internal code. Target languages/codes usually are [[bytecode]], [[assembly]], [[machine code]].
#### Blind Generation
This style of generation has for each [[Three Address Code]] [[Instruction|instruction]] a procedure, that generates the target code. This generation is rather easy to implement, but as a result of loosing context of other instructions it might lead to issues like unnecessary loading, storing, etc.
#### Context Generation
This style of generation keeps context between each each [[Three Address Code]] [[Instruction|instruction]], which allows it to know if a variable and its value in a [[Register|register]] is going to be used soon and keeps it within the register. Variables are divided into **alive**, which are going be used within the block, and **dead**, which won't be used in the block anymore. For alive variable the compiler also keeps the line in which it is going to get used. To find out which variables are alive and when are they last used, the generation uses a **backwards algorithms** that search from the end of the internal code towards the beginning.