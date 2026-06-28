# TeXProcess
General conversion related updates
Normalize TeX files (books multiple chapters include in main.tex file) which works on pdflatex and future need to convert as xml
TeX specials printing characters with backslash (&,%,$,#,_,{,},~,^. Read the TeX file and analyze which should print and which should be tex special. For example A & B in tex file contains  normal text then it should be A \& B. Suppose found in tabular environment then it should be as  TAB character. So it print like  A & B suppose column separator. Suppose it should be inside the column content then it should A \& B. And also it comes in \label{..} retain as the same.
Suppose find any control character non printable ASCII character which is not required for TeX file, then it should be removed
TeX understanding utf codes like mdash —, ndash –, ldots … , multiplication × should be mdash ---, ndash -- , ldots \ldots, multiplication \ensuremath{\times}
á, é, í, ó, ú should be \'a, \'e, \'i, \'o, \'u
Any other utf codes found for example chinese characters like 切, 經, 音, 義 changed as dummy hexadecimal code like INTx5207;, INTx7D93;, INTx97F3;, INTx7FA9;
\begin{picture}...\end{picture} need to remove fully
\begin{comment}...\end{comment} need to remove
Avoid math in math $...$ inside $...$ or \ensuremath should be normalize single math. For example \begin{cases}...\end{cases}
