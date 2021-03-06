<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
<head>
<!-- 2020-09-25 Fri 07:46 -->
<meta http-equiv="Content-Type" content="text/html;charset=utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Calculational Mathematics and <code>CalcCheck</code></title>
<meta name="generator" content="Org mode" />
<meta name="author" content="Musa Al-hassy" />
<meta name="description" content="Abrdiged Lecture Notes"
 />
<style type="text/css">
 <!--/*--><![CDATA[/*><!--*/
  .title  { text-align: center;
             margin-bottom: .2em; }
  .subtitle { text-align: center;
              font-size: medium;
              font-weight: bold;
              margin-top:0; }
  .todo   { font-family: monospace; color: red; }
  .done   { font-family: monospace; color: green; }
  .priority { font-family: monospace; color: orange; }
  .tag    { background-color: #eee; font-family: monospace;
            padding: 2px; font-size: 80%; font-weight: normal; }
  .timestamp { color: #bebebe; }
  .timestamp-kwd { color: #5f9ea0; }
  .org-right  { margin-left: auto; margin-right: 0px;  text-align: right; }
  .org-left   { margin-left: 0px;  margin-right: auto; text-align: left; }
  .org-center { margin-left: auto; margin-right: auto; text-align: center; }
  .underline { text-decoration: underline; }
  #postamble p, #preamble p { font-size: 90%; margin: .2em; }
  p.verse { margin-left: 3%; }
  pre {
    border: 1px solid #ccc;
    box-shadow: 3px 3px 3px #eee;
    padding: 8pt;
    font-family: monospace;
    overflow: auto;
    margin: 1.2em;
  }
  pre.src {
    position: relative;
    overflow: auto;
    padding-top: 1.2em;
  }
  pre.src:before {
    display: none;
    position: absolute;
    background-color: white;
    top: -10px;
    right: 10px;
    padding: 3px;
    border: 1px solid black;
  }
  pre.src:hover:before { display: inline;}
  /* Languages per Org manual */
  pre.src-asymptote:before { content: 'Asymptote'; }
  pre.src-awk:before { content: 'Awk'; }
  pre.src-C:before { content: 'C'; }
  /* pre.src-C++ doesn't work in CSS */
  pre.src-clojure:before { content: 'Clojure'; }
  pre.src-css:before { content: 'CSS'; }
  pre.src-D:before { content: 'D'; }
  pre.src-ditaa:before { content: 'ditaa'; }
  pre.src-dot:before { content: 'Graphviz'; }
  pre.src-calc:before { content: 'Emacs Calc'; }
  pre.src-emacs-lisp:before { content: 'Emacs Lisp'; }
  pre.src-fortran:before { content: 'Fortran'; }
  pre.src-gnuplot:before { content: 'gnuplot'; }
  pre.src-haskell:before { content: 'Haskell'; }
  pre.src-hledger:before { content: 'hledger'; }
  pre.src-java:before { content: 'Java'; }
  pre.src-js:before { content: 'Javascript'; }
  pre.src-latex:before { content: 'LaTeX'; }
  pre.src-ledger:before { content: 'Ledger'; }
  pre.src-lisp:before { content: 'Lisp'; }
  pre.src-lilypond:before { content: 'Lilypond'; }
  pre.src-lua:before { content: 'Lua'; }
  pre.src-matlab:before { content: 'MATLAB'; }
  pre.src-mscgen:before { content: 'Mscgen'; }
  pre.src-ocaml:before { content: 'Objective Caml'; }
  pre.src-octave:before { content: 'Octave'; }
  pre.src-org:before { content: 'Org mode'; }
  pre.src-oz:before { content: 'OZ'; }
  pre.src-plantuml:before { content: 'Plantuml'; }
  pre.src-processing:before { content: 'Processing.js'; }
  pre.src-python:before { content: 'Python'; }
  pre.src-R:before { content: 'R'; }
  pre.src-ruby:before { content: 'Ruby'; }
  pre.src-sass:before { content: 'Sass'; }
  pre.src-scheme:before { content: 'Scheme'; }
  pre.src-screen:before { content: 'Gnu Screen'; }
  pre.src-sed:before { content: 'Sed'; }
  pre.src-sh:before { content: 'shell'; }
  pre.src-sql:before { content: 'SQL'; }
  pre.src-sqlite:before { content: 'SQLite'; }
  /* additional languages in org.el's org-babel-load-languages alist */
  pre.src-forth:before { content: 'Forth'; }
  pre.src-io:before { content: 'IO'; }
  pre.src-J:before { content: 'J'; }
  pre.src-makefile:before { content: 'Makefile'; }
  pre.src-maxima:before { content: 'Maxima'; }
  pre.src-perl:before { content: 'Perl'; }
  pre.src-picolisp:before { content: 'Pico Lisp'; }
  pre.src-scala:before { content: 'Scala'; }
  pre.src-shell:before { content: 'Shell Script'; }
  pre.src-ebnf2ps:before { content: 'ebfn2ps'; }
  /* additional language identifiers per "defun org-babel-execute"
       in ob-*.el */
  pre.src-cpp:before  { content: 'C++'; }
  pre.src-abc:before  { content: 'ABC'; }
  pre.src-coq:before  { content: 'Coq'; }
  pre.src-groovy:before  { content: 'Groovy'; }
  /* additional language identifiers from org-babel-shell-names in
     ob-shell.el: ob-shell is the only babel language using a lambda to put
     the execution function name together. */
  pre.src-bash:before  { content: 'bash'; }
  pre.src-csh:before  { content: 'csh'; }
  pre.src-ash:before  { content: 'ash'; }
  pre.src-dash:before  { content: 'dash'; }
  pre.src-ksh:before  { content: 'ksh'; }
  pre.src-mksh:before  { content: 'mksh'; }
  pre.src-posh:before  { content: 'posh'; }
  /* Additional Emacs modes also supported by the LaTeX listings package */
  pre.src-ada:before { content: 'Ada'; }
  pre.src-asm:before { content: 'Assembler'; }
  pre.src-caml:before { content: 'Caml'; }
  pre.src-delphi:before { content: 'Delphi'; }
  pre.src-html:before { content: 'HTML'; }
  pre.src-idl:before { content: 'IDL'; }
  pre.src-mercury:before { content: 'Mercury'; }
  pre.src-metapost:before { content: 'MetaPost'; }
  pre.src-modula-2:before { content: 'Modula-2'; }
  pre.src-pascal:before { content: 'Pascal'; }
  pre.src-ps:before { content: 'PostScript'; }
  pre.src-prolog:before { content: 'Prolog'; }
  pre.src-simula:before { content: 'Simula'; }
  pre.src-tcl:before { content: 'tcl'; }
  pre.src-tex:before { content: 'TeX'; }
  pre.src-plain-tex:before { content: 'Plain TeX'; }
  pre.src-verilog:before { content: 'Verilog'; }
  pre.src-vhdl:before { content: 'VHDL'; }
  pre.src-xml:before { content: 'XML'; }
  pre.src-nxml:before { content: 'XML'; }
  /* add a generic configuration mode; LaTeX export needs an additional
     (add-to-list 'org-latex-listings-langs '(conf " ")) in .emacs */
  pre.src-conf:before { content: 'Configuration File'; }

  table { border-collapse:collapse; }
  caption.t-above { caption-side: top; }
  caption.t-bottom { caption-side: bottom; }
  td, th { vertical-align:top;  }
  th.org-right  { text-align: center;  }
  th.org-left   { text-align: center;   }
  th.org-center { text-align: center; }
  td.org-right  { text-align: right;  }
  td.org-left   { text-align: left;   }
  td.org-center { text-align: center; }
  dt { font-weight: bold; }
  .footpara { display: inline; }
  .footdef  { margin-bottom: 1em; }
  .figure { padding: 1em; }
  .figure p { text-align: center; }
  .equation-container {
    display: table;
    text-align: center;
    width: 100%;
  }
  .equation {
    vertical-align: middle;
  }
  .equation-label {
    display: table-cell;
    text-align: right;
    vertical-align: middle;
  }
  .inlinetask {
    padding: 10px;
    border: 2px solid gray;
    margin: 10px;
    background: #ffffcc;
  }
  #org-div-home-and-up
   { text-align: right; font-size: 70%; white-space: nowrap; }
  textarea { overflow-x: auto; }
  .linenr { font-size: smaller }
  .code-highlighted { background-color: #ffff00; }
  .org-info-js_info-navigation { border-style: none; }
  #org-info-js_console-label
    { font-size: 10px; font-weight: bold; white-space: nowrap; }
  .org-info-js_search-highlight
    { background-color: #ffff00; color: #000000; font-weight: bold; }
  .org-svg { width: 90%; }
  /*]]>*/-->
</style>
<link href="https://alhassy.github.io/org-notes-style.css" rel="stylesheet" type="text/css" />
<link href="https://alhassy.github.io/floating-toc.css" rel="stylesheet" type="text/css" />
<link href="https://alhassy.github.io/blog-banner.css" rel="stylesheet" type="text/css" />

        <style>
        /* From: https://endlessparentheses.com/public/css/endless.css */
        /* See also: https://meta.superuser.com/questions/4788/css-for-the-new-kbd-style */
        kbd
        {
          -moz-border-radius: 6px;
          -moz-box-shadow: 0 1px 0 rgba(0,0,0,0.2),0 0 0 2px #fff inset;
          -webkit-border-radius: 6px;
          -webkit-box-shadow: 0 1px 0 rgba(0,0,0,0.2),0 0 0 2px #fff inset;
          background-color: #f7f7f7;
          border: 1px solid #ccc;
          border-radius: 6px;
          box-shadow: 0 1px 0 rgba(0,0,0,0.2),0 0 0 2px #fff inset;
          color: #333;
          display: inline-block;
          font-family: 'Droid Sans Mono', monospace;
          font-size: 80%;
          font-weight: normal;
          line-height: inherit;
          margin: 0 .1em;
          padding: .08em .4em;
          text-shadow: 0 1px 0 #fff;
          word-spacing: -4px;

          box-shadow: 2px 2px 2px #222; /* MA: An extra I've added. */
        }
        </style>
        <link rel="stylesheet" type="text/css" href="https://alhassy.github.io/org-special-block-extras/tooltipster/dist/css/tooltipster.bundle.min.css"/>

        <link rel="stylesheet" type="text/css" href="https://alhassy.github.io/org-special-block-extras/tooltipster/dist/css/plugins/tooltipster/sideTip/themes/tooltipster-sideTip-punk.min.css" />

        <script type="text/javascript">
            if (typeof jQuery == 'undefined') {
                document.write(unescape('%3Cscript src="https://code.jquery.com/jquery-1.10.0.min.js"%3E%3C/script%3E'));
            }
        </script>

         <script type="text/javascript"            src="https://alhassy.github.io/org-special-block-extras/tooltipster/dist/js/tooltipster.bundle.min.js"></script>

          <script>
                 $(document).ready(function() {
                     $('.tooltip').tooltipster({
                         theme: 'tooltipster-punk',
                         contentAsHTML: true,
                         animation: 'grow',
                         delay: [100,500],
                         // trigger: 'click'
                         trigger: 'custom',
                         triggerOpen: {
                             mouseenter: true
                         },
                         triggerClose: {
                             originClick: true,
                             scroll: true
                         }
         });
                 });
             </script>

        <style>
           abbr {color: red;}

           .tooltip { border-bottom: 1px dotted #000;
                      color:red;
                      text-decoration: none;}
        </style>
<script type="text/javascript">
// @license magnet:?xt=urn:btih:e95b018ef3580986a04669f1b5879592219e2a7a&dn=public-domain.txt Public Domain
<!--/*--><![CDATA[/*><!--*/
     function CodeHighlightOn(elem, id)
     {
       var target = document.getElementById(id);
       if(null != target) {
         elem.classList.add("code-highlighted");
         target.classList.add("code-highlighted");
       }
     }
     function CodeHighlightOff(elem, id)
     {
       var target = document.getElementById(id);
       if(null != target) {
         elem.classList.remove("code-highlighted");
         target.classList.remove("code-highlighted");
       }
     }
    /*]]>*///-->
// @license-end
</script>
</head>
<body>
<div id="content">
<h1 class="title">Calculational Mathematics and <code>CalcCheck</code></h1>
<p>
Live webpage: <a href="https://alhassy.github.io/CalcCheck/">https://alhassy.github.io/CalcCheck/</a>
</p>

<div style="column-rule-style:none;column-count:2;"<p>

</p>

<p>
 <div style="padding: 1em; background-color: pink; border-radius: 15px; font-size: 0.9em; box-shadow: 0.05em 0.1em 5px 0.01em  #00000057;"> <h3></h3>
</p>
<h2>
<p>
<a href="https://alhassy.github.io/CalcCheck/Docs"><code>CalcCheck</code> Documentation</a>
</p>
</h2>
<p>
 </div>
</p>

<p>

</p>

<p>
 <div style="padding: 1em; background-color: pink; border-radius: 15px; font-size: 0.9em; box-shadow: 0.05em 0.1em 5px 0.01em  #00000057;"> <h3></h3>
</p>
<h2>
<p>
<a href="https://alhassy.github.io/CalcCheck/LectureNotes.html">Lecture Notes</a>
</p>
</h2>
<p>
 </div>
</p>
</div>


<div id="orga5c1277" class="figure">
<p><img src="images/proof trees vs calculational proofs.png" alt="proof trees vs calculational proofs.png" />
</p>
</div>

<p>
 <div style="padding: 1em; background-color: #99FFCC; border-radius: 15px; font-size: 0.9em; box-shadow: 0.05em 0.1em 5px 0.01em  #00000057;"> <h3></h3>
</p>
<h2>
<p>
Videos
</p>
</h2>

<ol class="org-ol">
<li><p>
<a href="https://youtu.be/5IyMizFhHMA">Introduction to Discrete &amp; Calculational Maths</a>
<kbd> Sep 8 </kbd>
</p>

<p>
What is a calculational proof? What is discrete mathematics?
How is math related to programming: “proofs-as-programs”.
</p></li>

<li><p>
<a href="https://youtu.be/0wM0WXLJULQ">Grammatical Analysis and Boolean Operators</a>
<kbd> Sep 10 </kbd>
</p>

<p>
A proof is a “story”, and calculation hints are the “transitions” that make
the story flow nicely.  The formulae are the “sentences” and they are formed
from operators, constants, and variables which act as “verbs”, “names”, and
“pronouns”, respectively.
</p>

<p>
ℕumber arithmetic is learned by memorising parts of
infinitely large addition and multiplication tables.
In contrast, 𝔹oolean arithmetic has tiny 2×2 “truth tables”.
As such, 𝔹  may be easier to learn than ℕ.
</p></li>

<li><p>
<a href="https://youtu.be/9oeJtu4JjSQ">Ladies and Tigers, a teaser</a>
<kbd> Sep 11 </kbd>
</p>

<p>
Continuing the discussion on Boolean operators and how they can be used to
model puzzles.
</p></li>

<li><p>
<a href="https://youtu.be/7cmretG3Zzg">Substitution</a>
<kbd> Sep 15 </kbd>
</p>

<p>
Textual substitution is a way to implement function application, grafting on
trees, and can be used for assignment commands in programming.
</p></li>

<li><p>
<a href="https://youtu.be/OXL-FvDqhX8">Inference rules, Proofs-are-programs, and Equivalence Part I</a>
<kbd> Sep 17 </kbd>
</p>

<p>
Update: There will be no knights and knaves problems in the upcoming Sep 22
midterm; but possibly in a future midterm.
</p>

<p>
The inference rules act as the foundational justification for the equational
proof style; the online lecture notes go into more detail.
</p></li>

<li><p>
<a href="https://youtu.be/JxRZC2UMJb0">Inference rules, Proofs-are-programs, and Equivalence Part II</a>
(with lofi music) <kbd> Sep 18 </kbd>
</p>

<p>
Quickly show how a program can be shown to meet its specification,
discuss equivalence and negation for the purposes of solving
knights and knaves problems.
</p>

<p>
<kbd> Sep 22 </kbd> is the first midterm; it is online during class time.
</p></li>

<li><p>
<a href="https://youtu.be/85MmBPp9jKc">Tabulation vs Calculation</a> <kbd> Sep 24 </kbd>
</p>

<p>
We review basic operations on the Booleans with a focus on how manipulating
symbols can be more effective than constructing truth tables, or evaluating
expressions by “plug and chug” simplifications.
</p>

<p>
We also discuss formalisations of English phrases as propositional expressions.
</p></li>
</ol>


<p>
&#x2026; more content at the webpage <a href="https://alhassy.github.io/CalcCheck/">https://alhassy.github.io/CalcCheck/</a> &#x2026;
</p>


<p>
 </div>
</p>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">⇨ <a href="https://github.com/alhassy/CalcCheck">Github Repository</a> ⇦</td>
</tr>
</tbody>
</table>
</div>
<div id="postamble" class="status">
<p class="author">Author: Musa Al-hassy</p>
<p class="date">Created: 2020-09-25 Fri 07:46</p>
<p class="validation"><a href="https://validator.w3.org/check?uri=referer">Validate</a></p>
</div>
</body>
</html>
