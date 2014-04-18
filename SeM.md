Semantic Mathematics (SeM)
==============================================
Semantic Mathematics is a semantic markup language designed for mathematicians by mathematician.

# Rationale and objectives

Mathematic formulae represent fully defined objects. They have well defined properties and operations on them. But from the typical representation of LaTeX one can only extract visual representation.

Main objectives of SeM are:
* Make mathematical objects to be variable free (for example \int_a^b f(x) dx has one variable which can be replaced, i.e. \int_a^b f(y) dy is the same integral)
* Describe extensible modular language which supports symbol overloading
* Describe canonical form of expressions, such that it can be used to verify validity
* Provide reference implementation of validation tools
* Provide core libraries defining core mathematical objects (derivative, integral)

# Guiding example

\include{SeM}
\include{SeM-geom}
\include{SeM-diffgeom}

\newcommand{M}{\mani{M}}
\newcommand{S}{\surf[M]{S}}



\begin{document}
Let $\M$ be a manifold and $\S$ be its outer surface. Then by the Stockes theorem
\begin{equation}
\int_S \form{\omega} = \int_M \d\form{\omega} 
\end{equation}
\end{document}

# Main Objects

Most of the mathematical objects are defined by their properties. Properties are usually defined through operations on some parameters. And the operations are usually redefined for different objects, usually resulting in similar properties related to the operation.

In SeM everything is a set and a type simultaneously. For example elements of the set Mathematical objects usually have several subobjects in their definition and operations within those subobjects and between them. SeMOperation is a SeMObject which subobjects are operation parameters. The main method of the SeMObject is called canonify. Its purpose is to bring to the canonical form all of the components of the object. For the object representing operation this method executes the operation.

Let us define main objects of the language

Predefined symbols:
 * set - placeholder for any set
 * type - synonim for set
 * def - defines set/type

\def{Zero}
\def{One}
\def{Two}
\def{Infinity}

\begin[Natural]{def}
\Ordered
\MonotonicallyAdditive
\Infinite
\Multiplicative
\HasOne
\end{def}

\begin[Relation]{def}
\parameters{Two}
\end{def}

\begin[In:Relation]{def}

\end{def}

\begin[Order:Relation]{def}
\Relation
\end{def}

\begin[Additive]{def}
\end{def}


\begin{definition}
\name{Set}
\weaksubobject[Additive,Multiplicative,Comparable]{Element}
\end{definition}

\begin{definition}
\name{Manifold}
\specialcaseof{Set}
\weaksubobject{ConsistantCharts}
\end{definition}


