---
layout: post
title: TikZ Update
published: true
category: Work
---

Ok, I admitted in the last [post](../../14/TikZ) that my TikZ diagram was a lot less than optimal, because of too many 
repetitions in the code. So I decided to spend some time with the TikZ manual (really useful source of information), 
with the result that I learned about 'for-loops': For everything that needs to be carried out more than 1 time, a for-loop 
can be used. 

The concept is quite simple: In the follwing example an "ultra thick" line is drawn for a certain point \x from -6 to -6.5 on the y-axis. This
is done for each of the points specified.


<pre id="latex"><code>
\foreach \x in {0.35,1.54,2.73,3.92,5.11,6.3} \draw[ultra thick] (\x,-6) -- (\x,-6.5);
</code></pre>


This however can be simplified even more. Just mention the first 2 and the last of the desired points and the ones in between 
can be replaced with "...", as below.

<pre id="latex"><code>
\foreach \x in {0.3,1.54,...,6.3} \draw[very thick] (\x,-6) -- (\x,-6.5);
</code></pre>

The complete picture looks just like the one before, the only difference is that I added some more connection lines, because it became so 
much easier. Also I changed the coordinates slightly, to improve the size of the final picture. Now it perfectly matches the text width in the 
document I use it in. If you want to see a bigger picture you can click on it!

<div align="center"><a href="http://www.doerte.eu/images/tikzNew.png"> <img src="/img/tikzNew.png" alt='New TikZ image'  border="0" width="311"> </a></div>

And again the Latex-code I used...:

<pre id="latex"><code>
\begin{figure}[!h]  
\begin{center}
\fbox{\begin{tikzpicture}[font=\scriptsize]

\node at (3.325,2)[text centered] (in) {Heard and seen speech};
\draw[thin,-triangle 90] (2,1.5)->(2,0.5);
\draw[thin,-triangle 90] (4.65,1.5)->(4.65,0.5);

\draw (0,0.5) rectangle (6.6,-7);

\foreach \x in {0.35,0.7,...,6.3} \draw[thick] (\x,0) -- (\x,-0.2);
\foreach \x in {0.35,1.09375,...,6.3} \draw[very thick] (\x,-3) -- (\x,-3.3);
\foreach \x in {0.35,1.54,...,6.3} \draw[ultra thick] (\x,-6) -- (\x,-6.5);

\foreach \x in {0.35,1.4,2.8,4.2,6.3} \draw[thin] (\x,-0.4) -- (0.35,-2.8);
\foreach \x in {0.35,1.05,2.45,3.85,5.25} \draw[thin] (\x,-0.4) -- (1.09375,-2.8);
\foreach \x in {0.7,2.1,2.8,4.55,5.6} \draw[thin] (\x,-0.4) -- (1.8375,-2.8);
\foreach \x in {1.75,2.8,3.15,3.5,4.55} \draw[thin] (\x,-0.4) --(2.58125,-2.8);
\foreach \x in {0.35,1.4,3.5,4.9,5.95} \draw[thin] (\x,-0.4) -- (3.325,-2.8);
\foreach \x in {2.1,3.5,3.85,4.2,5.25} \draw[thin] (\x,-0.4) -- (4.06875,-2.8);
\foreach \x in {1.05,1.75,3.15,5.25,5.95} \draw[thin] (\x,-0.4) -- (4.8125,-2.8);
\foreach \x in {0.7,1.75,4.55,5.6,6.3} \draw[thin] (\x,-0.4) -- (5.55625,-2.8);
\foreach \x in {1.05,2.45,3.85,4.9,6.3} \draw[thin] (\x,-0.4) -- (6.3,-2.8);

\foreach \x in {0.35,1.09375,2.58125,4.06875,5.55625} \draw[thin] (\x,-3.5) -- (0.35,-5.8);
\foreach \x in {0.35,1.8375,3.325,4.8125,6.3} \draw[thin] (\x,-3.5) -- (1.54,-5.8);
\foreach \x in {1.09375,1.8375,2.58125,4.06875,4.8125} \draw[thin] (\x,-3.5) -- (2.73,-5.8);
\foreach \x in {1.09375,1.8375,2.58125,5.55625,6.3} \draw[thin] (\x,-3.5) -- (3.92,-5.8);
\foreach \x in {0.35,3.325,4.06875,4.8125,6.3} \draw[thin] (\x,-3.5) -- (5.11,-5.8);
\foreach \x in {1.8375,3.325,4.06875,5.55625,6.3} \draw[thin] (\x,-3.5) -- (6.3,-5.8);

\node(phone) at (-1,-0.1)[text width=1.5cm,text centered]  {Phonetic units};
\node(phono) at (-1.3,-3.15)[text width=1.5cm,text centered]  {Phonological units};
\node(phonem) at (-1,-6.25)[text width=1.5cm,text centered]  {Abstract phonemic units};
\node(speech) at (-2.5,-3.15)[rotate=90]  {Perceiving speech};
\node(proc) at (3.325,-9)[draw, minimum height=1.5cm]  {Lexical processor};
\node(sys) at (7.6,-3.15)[text width=2cm,text centered] {Input phonetic-phonological system};

\draw[thin,triangle 90-triangle 90] (proc) -- (3.325,-7);

\end{tikzpicture}}
\end{center}
\end{figure}
</code></pre>
