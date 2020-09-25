<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
<head>
<!-- 2020-09-25 Fri 07:37 -->
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

</p>
<div class="org-center">
<script>
function myFunction() {
var x = document.getElementById("theColors");
if (x.style.display === "block") {
x.style.display = "none";
} else {
x.style.display = "block";
}
}
</script>
<button style='padding: 0; margin: -200px 0px;'onclick="myFunction()">🎨🖌</button>


<div id="theColors" style="display: none"> <center><strong>Click on a name to
      make it the background colour ^_^
     </strong></center>
<button style='background-color: #fffafa;' OnClick="document.bgColor='#fffafa';
document.body.style.background='#fffafa'">snow</button><button style='background-color:
#f8f8ff;' OnClick="document.bgColor='#f8f8ff';
document.body.style.background='#f8f8ff'">ghost
white</button><button style='background-color: #f8f8ff;'
OnClick="document.bgColor='#f8f8ff'; currentcolor = 'white';
document.body.style.background='#f8f8ff'">ghostwhite</button><button style='background-color:
#f5f5f5;' OnClick="document.bgColor='#f5f5f5';
document.body.style.background='#f5f5f5'">white
smoke</button><button style='background-color: #f5f5f5;'
OnClick="document.bgColor='#f5f5f5';
document.body.style.background='#f5f5f5'">whitesmoke</button><button style='background-color:
#dcdcdc;' OnClick="document.bgColor='#dcdcdc';
document.body.style.background='#dcdcdc'">gainsboro</button><button style='background-color:
#fffaf0;' OnClick="document.bgColor='#fffaf0';
document.body.style.background='#fffaf0'">floral
white</button><button style='background-color: #fffaf0;'
OnClick="document.bgColor='#fffaf0';
document.body.style.background='#fffaf0'">floralwhite</button><button style='background-color:
#fdf5e6;' OnClick="document.bgColor='#fdf5e6';
document.body.style.background='#fdf5e6'">old
lace</button><button style='background-color: #fdf5e6;'
OnClick="document.bgColor='#fdf5e6'; currentcolor='old lace';
document.body.style.background='#fdf5e6'">oldlace</button><button style='background-color:
#faf0e6;' OnClick="document.bgColor='#faf0e6';
document.body.style.background='#faf0e6'">linen</button><button style='background-color:
#faebd7;' OnClick="document.bgColor='#faebd7';
document.body.style.background='#faebd7'">antique
white</button><button style='background-color: #faebd7;'
OnClick="document.bgColor='#faebd7';
document.body.style.background='#faebd7'">antiquewhite</button><button style='background-color:
#ffefd5;' OnClick="document.bgColor='#ffefd5';
document.body.style.background='#ffefd5'">papaya
whip</button><button style='background-color: #ffefd5;'
OnClick="document.bgColor='#ffefd5';
document.body.style.background='#ffefd5'">papayawhip</button><button style='background-color:
#ffebcd;' OnClick="document.bgColor='#ffebcd';
document.body.style.background='#ffebcd'">blanched
almond</button><button style='background-color: #ffebcd;'
OnClick="document.bgColor='#ffebcd';
document.body.style.background='#ffebcd'">blanchedalmond</button><button style='background-color:
#ffe4c4;' OnClick="document.bgColor='#ffe4c4';
document.body.style.background='#ffe4c4'">bisque</button><button style='background-color:
#ffdab9;' OnClick="document.bgColor='#ffdab9';
document.body.style.background='#ffdab9'">peach
puff</button><button style='background-color: #ffdab9;'
OnClick="document.bgColor='#ffdab9';
document.body.style.background='#ffdab9'">peachpuff</button><button style='background-color:
#ffdead;' OnClick="document.bgColor='#ffdead';
document.body.style.background='#ffdead'">navajo
white</button><button style='background-color: #ffdead;'
OnClick="document.bgColor='#ffdead';
document.body.style.background='#ffdead'">navajowhite</button><button style='background-color:
#ffe4b5;' OnClick="document.bgColor='#ffe4b5';
document.body.style.background='#ffe4b5'">moccasin</button><button style='background-color:
#fff8dc;' OnClick="document.bgColor='#fff8dc';
document.body.style.background='#fff8dc'">cornsilk</button><button style='background-color:
#fffff0;' OnClick="document.bgColor='#fffff0';
document.body.style.background='#fffff0'">ivory</button><button style='background-color:
#fffacd;' OnClick="document.bgColor='#fffacd';
document.body.style.background='#fffacd'">lemon
chiffon</button><button style='background-color: #fffacd;'
OnClick="document.bgColor='#fffacd';
document.body.style.background='#fffacd'">lemonchiffon</button><button style='background-color:
#fff5ee;' OnClick="document.bgColor='#fff5ee';
document.body.style.background='#fff5ee'">seashell</button><button style='background-color:
#f0fff0;' OnClick="document.bgColor='#f0fff0';
document.body.style.background='#f0fff0'">honeydew</button><button style='background-color:
#f5fffa;' OnClick="document.bgColor='#f5fffa';
document.body.style.background='#f5fffa'">mint
cream</button><button style='background-color: #f5fffa;'
OnClick="document.bgColor='#f5fffa';
document.body.style.background='#f5fffa'">mintcream</button><button style='background-color:
#f0ffff;' OnClick="document.bgColor='#f0ffff';
document.body.style.background='#f0ffff'">azure</button><button style='background-color:
#f0f8ff;' OnClick="document.bgColor='#f0f8ff';
document.body.style.background='#f0f8ff'">alice
blue</button><button style='background-color: #f0f8ff;'
OnClick="document.bgColor='#f0f8ff';
document.body.style.background='#f0f8ff'">aliceblue</button><button style='background-color:
#e6e6fa;' OnClick="document.bgColor='#e6e6fa';
document.body.style.background='#e6e6fa'">lavender</button><button style='background-color:
#fff0f5;' OnClick="document.bgColor='#fff0f5';
document.body.style.background='#fff0f5'">lavender
blush</button><button style='background-color: #fff0f5;'
OnClick="document.bgColor='#fff0f5';
document.body.style.background='#fff0f5'">lavenderblush</button><button style='background-color:
#ffe4e1;' OnClick="document.bgColor='#ffe4e1';
document.body.style.background='#ffe4e1'">misty
rose</button><button style='background-color: #ffe4e1;'
OnClick="document.bgColor='#ffe4e1';
document.body.style.background='#ffe4e1'">mistyrose</button><button style='background-color:
#ffffff;' OnClick="document.bgColor='#ffffff';
document.body.style.background='#ffffff'">white</button><button style='background-color:
#000000;' OnClick="document.bgColor='#000000';
document.body.style.background='#000000'">black</button><button style='background-color:
#2f4f4f;' OnClick="document.bgColor='#2f4f4f';
document.body.style.background='#2f4f4f'">dark slate
gray</button><button style='background-color: #2f4f4f;'
OnClick="document.bgColor='#2f4f4f';
document.body.style.background='#2f4f4f'">darkslategray</button><button style='background-color:
#2f4f4f;' OnClick="document.bgColor='#2f4f4f';
document.body.style.background='#2f4f4f'">dark slate
grey</button><button style='background-color: #2f4f4f;'
OnClick="document.bgColor='#2f4f4f';
document.body.style.background='#2f4f4f'">darkslategrey</button><button style='background-color:
#696969;' OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">dim
gray</button><button style='background-color: #696969;'
OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">dimgray</button><button style='background-color:
#696969;' OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">dim
grey</button><button style='background-color: #696969;'
OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">dimgrey</button><button style='background-color:
#708090;' OnClick="document.bgColor='#708090';
document.body.style.background='#708090'">slate
gray</button><button style='background-color: #708090;'
OnClick="document.bgColor='#708090';
document.body.style.background='#708090'">slategray</button><button style='background-color:
#708090;' OnClick="document.bgColor='#708090';
document.body.style.background='#708090'">slate
grey</button><button style='background-color: #708090;'
OnClick="document.bgColor='#708090';
document.body.style.background='#708090'">slategrey</button><button style='background-color:
#778899;' OnClick="document.bgColor='#778899';
document.body.style.background='#778899'">light slate
gray</button><button style='background-color: #778899;'
OnClick="document.bgColor='#778899';
document.body.style.background='#778899'">lightslategray</button><button style='background-color:
#778899;' OnClick="document.bgColor='#778899';
document.body.style.background='#778899'">light slate
grey</button><button style='background-color: #778899;'
OnClick="document.bgColor='#778899';
document.body.style.background='#778899'">lightslategrey</button><button style='background-color:
#bebebe;' OnClick="document.bgColor='#bebebe';
document.body.style.background='#bebebe'">gray</button><button style='background-color:
#bebebe;' OnClick="document.bgColor='#bebebe';
document.body.style.background='#bebebe'">grey</button><button style='background-color:
#d3d3d3;' OnClick="document.bgColor='#d3d3d3';
document.body.style.background='#d3d3d3'">light
grey</button><button style='background-color: #d3d3d3;'
OnClick="document.bgColor='#d3d3d3';
document.body.style.background='#d3d3d3'">lightgrey</button><button style='background-color:
#d3d3d3;' OnClick="document.bgColor='#d3d3d3';
document.body.style.background='#d3d3d3'">light
gray</button><button style='background-color: #d3d3d3;'
OnClick="document.bgColor='#d3d3d3';
document.body.style.background='#d3d3d3'">lightgray</button><button style='background-color:
#191970;' OnClick="document.bgColor='#191970';
document.body.style.background='#191970'">midnight
blue</button><button style='background-color: #191970;'
OnClick="document.bgColor='#191970';
document.body.style.background='#191970'">midnightblue</button><button style='background-color:
#000080;' OnClick="document.bgColor='#000080';
document.body.style.background='#000080'">navy</button><button style='background-color:
#000080;' OnClick="document.bgColor='#000080';
document.body.style.background='#000080'">navy
blue</button><button style='background-color: #000080;'
OnClick="document.bgColor='#000080';
document.body.style.background='#000080'">navyblue</button><button style='background-color:
#6495ed;' OnClick="document.bgColor='#6495ed';
document.body.style.background='#6495ed'">cornflower
blue</button><button style='background-color: #6495ed;'
OnClick="document.bgColor='#6495ed';
document.body.style.background='#6495ed'">cornflowerblue</button><button style='background-color:
#483d8b;' OnClick="document.bgColor='#483d8b';
document.body.style.background='#483d8b'">dark slate
blue</button><button style='background-color: #483d8b;'
OnClick="document.bgColor='#483d8b';
document.body.style.background='#483d8b'">darkslateblue</button><button style='background-color:
#6a5acd;' OnClick="document.bgColor='#6a5acd';
document.body.style.background='#6a5acd'">slate
blue</button><button style='background-color: #6a5acd;'
OnClick="document.bgColor='#6a5acd';
document.body.style.background='#6a5acd'">slateblue</button><button style='background-color:
#7b68ee;' OnClick="document.bgColor='#7b68ee';
document.body.style.background='#7b68ee'">medium slate
blue</button><button style='background-color: #7b68ee;'
OnClick="document.bgColor='#7b68ee';
document.body.style.background='#7b68ee'">mediumslateblue</button><button style='background-color:
#8470ff;' OnClick="document.bgColor='#8470ff';
document.body.style.background='#8470ff'">light slate
blue</button><button style='background-color: #8470ff;'
OnClick="document.bgColor='#8470ff';
document.body.style.background='#8470ff'">lightslateblue</button><button style='background-color:
#0000cd;' OnClick="document.bgColor='#0000cd';
document.body.style.background='#0000cd'">medium
blue</button><button style='background-color: #0000cd;'
OnClick="document.bgColor='#0000cd';
document.body.style.background='#0000cd'">mediumblue</button><button style='background-color:
#4169e1;' OnClick="document.bgColor='#4169e1';
document.body.style.background='#4169e1'">royal
blue</button><button style='background-color: #4169e1;'
OnClick="document.bgColor='#4169e1';
document.body.style.background='#4169e1'">royalblue</button><button style='background-color:
#0000ff;' OnClick="document.bgColor='#0000ff';
document.body.style.background='#0000ff'">blue</button><button style='background-color:
#1e90ff;' OnClick="document.bgColor='#1e90ff';
document.body.style.background='#1e90ff'">dodger
blue</button><button style='background-color: #1e90ff;'
OnClick="document.bgColor='#1e90ff';
document.body.style.background='#1e90ff'">dodgerblue</button><button style='background-color:
#00bfff;' OnClick="document.bgColor='#00bfff';
document.body.style.background='#00bfff'">deep sky
blue</button><button style='background-color: #00bfff;'
OnClick="document.bgColor='#00bfff';
document.body.style.background='#00bfff'">deepskyblue</button><button style='background-color:
#87ceeb;' OnClick="document.bgColor='#87ceeb';
document.body.style.background='#87ceeb'">sky
blue</button><button style='background-color: #87ceeb;'
OnClick="document.bgColor='#87ceeb';
document.body.style.background='#87ceeb'">skyblue</button><button style='background-color:
#87cefa;' OnClick="document.bgColor='#87cefa';
document.body.style.background='#87cefa'">light sky
blue</button><button style='background-color: #87cefa;'
OnClick="document.bgColor='#87cefa';
document.body.style.background='#87cefa'">lightskyblue</button><button style='background-color:
#4682b4;' OnClick="document.bgColor='#4682b4';
document.body.style.background='#4682b4'">steel
blue</button><button style='background-color: #4682b4;'
OnClick="document.bgColor='#4682b4';
document.body.style.background='#4682b4'">steelblue</button><button style='background-color:
#b0c4de;' OnClick="document.bgColor='#b0c4de';
document.body.style.background='#b0c4de'">light steel
blue</button><button style='background-color: #b0c4de;'
OnClick="document.bgColor='#b0c4de';
document.body.style.background='#b0c4de'">lightsteelblue</button><button style='background-color:
#add8e6;' OnClick="document.bgColor='#add8e6';
document.body.style.background='#add8e6'">light
blue</button><button style='background-color: #add8e6;'
OnClick="document.bgColor='#add8e6';
document.body.style.background='#add8e6'">lightblue</button><button style='background-color:
#b0e0e6;' OnClick="document.bgColor='#b0e0e6';
document.body.style.background='#b0e0e6'">powder
blue</button><button style='background-color: #b0e0e6;'
OnClick="document.bgColor='#b0e0e6';
document.body.style.background='#b0e0e6'">powderblue</button><button style='background-color:
#afeeee;' OnClick="document.bgColor='#afeeee';
document.body.style.background='#afeeee'">pale
turquoise</button><button style='background-color: #afeeee;'
OnClick="document.bgColor='#afeeee';
document.body.style.background='#afeeee'">paleturquoise</button><button style='background-color:
#00ced1;' OnClick="document.bgColor='#00ced1';
document.body.style.background='#00ced1'">dark
turquoise</button><button style='background-color: #00ced1;'
OnClick="document.bgColor='#00ced1';
document.body.style.background='#00ced1'">darkturquoise</button><button style='background-color:
#48d1cc;' OnClick="document.bgColor='#48d1cc';
document.body.style.background='#48d1cc'">medium
turquoise</button><button style='background-color: #48d1cc;'
OnClick="document.bgColor='#48d1cc';
document.body.style.background='#48d1cc'">mediumturquoise</button><button style='background-color:
#40e0d0;' OnClick="document.bgColor='#40e0d0';
document.body.style.background='#40e0d0'">turquoise</button><button style='background-color:
#00ffff;' OnClick="document.bgColor='#00ffff';
document.body.style.background='#00ffff'">cyan</button><button style='background-color:
#e0ffff;' OnClick="document.bgColor='#e0ffff';
document.body.style.background='#e0ffff'">light
cyan</button><button style='background-color: #e0ffff;'
OnClick="document.bgColor='#e0ffff';
document.body.style.background='#e0ffff'">lightcyan</button><button style='background-color:
#5f9ea0;' OnClick="document.bgColor='#5f9ea0';
document.body.style.background='#5f9ea0'">cadet
blue</button><button style='background-color: #5f9ea0;'
OnClick="document.bgColor='#5f9ea0';
document.body.style.background='#5f9ea0'">cadetblue</button><button style='background-color:
#66cdaa;' OnClick="document.bgColor='#66cdaa';
document.body.style.background='#66cdaa'">medium
aquamarine</button><button style='background-color: #66cdaa;'
OnClick="document.bgColor='#66cdaa';
document.body.style.background='#66cdaa'">mediumaquamarine</button><button style='background-color:
#7fffd4;' OnClick="document.bgColor='#7fffd4';
document.body.style.background='#7fffd4'">aquamarine</button><button style='background-color:
#006400;' OnClick="document.bgColor='#006400';
document.body.style.background='#006400'">dark
green</button><button style='background-color: #006400;'
OnClick="document.bgColor='#006400';
document.body.style.background='#006400'">darkgreen</button><button style='background-color:
#556b2f;' OnClick="document.bgColor='#556b2f';
document.body.style.background='#556b2f'">dark olive
green</button><button style='background-color: #556b2f;'
OnClick="document.bgColor='#556b2f';
document.body.style.background='#556b2f'">darkolivegreen</button><button style='background-color:
#8fbc8f;' OnClick="document.bgColor='#8fbc8f';
document.body.style.background='#8fbc8f'">dark sea
green</button><button style='background-color: #8fbc8f;'
OnClick="document.bgColor='#8fbc8f';
document.body.style.background='#8fbc8f'">darkseagreen</button><button style='background-color:
#2e8b57;' OnClick="document.bgColor='#2e8b57';
document.body.style.background='#2e8b57'">sea
green</button><button style='background-color: #2e8b57;'
OnClick="document.bgColor='#2e8b57';
document.body.style.background='#2e8b57'">seagreen</button><button style='background-color:
#3cb371;' OnClick="document.bgColor='#3cb371';
document.body.style.background='#3cb371'">medium sea
green</button><button style='background-color: #3cb371;'
OnClick="document.bgColor='#3cb371';
document.body.style.background='#3cb371'">mediumseagreen</button><button style='background-color:
#20b2aa;' OnClick="document.bgColor='#20b2aa';
document.body.style.background='#20b2aa'">light sea
green</button><button style='background-color: #20b2aa;'
OnClick="document.bgColor='#20b2aa';
document.body.style.background='#20b2aa'">lightseagreen</button><button style='background-color:
#98fb98;' OnClick="document.bgColor='#98fb98';
document.body.style.background='#98fb98'">pale
green</button><button style='background-color: #98fb98;'
OnClick="document.bgColor='#98fb98';
document.body.style.background='#98fb98'">palegreen</button><button style='background-color:
#00ff7f;' OnClick="document.bgColor='#00ff7f';
document.body.style.background='#00ff7f'">spring
green</button><button style='background-color: #00ff7f;'
OnClick="document.bgColor='#00ff7f';
document.body.style.background='#00ff7f'">springgreen</button><button style='background-color:
#7cfc00;' OnClick="document.bgColor='#7cfc00';
document.body.style.background='#7cfc00'">lawn
green</button><button style='background-color: #7cfc00;'
OnClick="document.bgColor='#7cfc00';
document.body.style.background='#7cfc00'">lawngreen</button><button style='background-color:
#00ff00;' OnClick="document.bgColor='#00ff00';
document.body.style.background='#00ff00'">green</button><button style='background-color:
#7fff00;' OnClick="document.bgColor='#7fff00';
document.body.style.background='#7fff00'">chartreuse</button><button style='background-color:
#00fa9a;' OnClick="document.bgColor='#00fa9a';
document.body.style.background='#00fa9a'">medium spring
green</button><button style='background-color: #00fa9a;'
OnClick="document.bgColor='#00fa9a';
document.body.style.background='#00fa9a'">mediumspringgreen</button><button style='background-color:
#adff2f;' OnClick="document.bgColor='#adff2f';
document.body.style.background='#adff2f'">green
yellow</button><button style='background-color: #adff2f;'
OnClick="document.bgColor='#adff2f';
document.body.style.background='#adff2f'">greenyellow</button><button style='background-color:
#32cd32;' OnClick="document.bgColor='#32cd32';
document.body.style.background='#32cd32'">lime
green</button><button style='background-color: #32cd32;'
OnClick="document.bgColor='#32cd32';
document.body.style.background='#32cd32'">limegreen</button><button style='background-color:
#9acd32;' OnClick="document.bgColor='#9acd32';
document.body.style.background='#9acd32'">yellow
green</button><button style='background-color: #9acd32;'
OnClick="document.bgColor='#9acd32';
document.body.style.background='#9acd32'">yellowgreen</button><button style='background-color:
#228b22;' OnClick="document.bgColor='#228b22';
document.body.style.background='#228b22'">forest
green</button><button style='background-color: #228b22;'
OnClick="document.bgColor='#228b22';
document.body.style.background='#228b22'">forestgreen</button><button style='background-color:
#6b8e23;' OnClick="document.bgColor='#6b8e23';
document.body.style.background='#6b8e23'">olive
drab</button><button style='background-color: #6b8e23;'
OnClick="document.bgColor='#6b8e23';
document.body.style.background='#6b8e23'">olivedrab</button><button style='background-color:
#bdb76b;' OnClick="document.bgColor='#bdb76b';
document.body.style.background='#bdb76b'">dark
khaki</button><button style='background-color: #bdb76b;'
OnClick="document.bgColor='#bdb76b';
document.body.style.background='#bdb76b'">darkkhaki</button><button style='background-color:
#f0e68c;' OnClick="document.bgColor='#f0e68c';
document.body.style.background='#f0e68c'">khaki</button><button style='background-color:
#eee8aa;' OnClick="document.bgColor='#eee8aa';
document.body.style.background='#eee8aa'">pale
goldenrod</button><button style='background-color: #eee8aa;'
OnClick="document.bgColor='#eee8aa';
document.body.style.background='#eee8aa'">palegoldenrod</button><button style='background-color:
#fafad2;' OnClick="document.bgColor='#fafad2';
document.body.style.background='#fafad2'">light goldenrod
yellow</button><button style='background-color: #fafad2;'
OnClick="document.bgColor='#fafad2';
document.body.style.background='#fafad2'">lightgoldenrodyellow</button><button style='background-color:
#ffffe0;' OnClick="document.bgColor='#ffffe0';
document.body.style.background='#ffffe0'">light
yellow</button><button style='background-color: #ffffe0;'
OnClick="document.bgColor='#ffffe0';
document.body.style.background='#ffffe0'">lightyellow</button><button style='background-color:
#ffff00;' OnClick="document.bgColor='#ffff00';
document.body.style.background='#ffff00'">yellow</button><button style='background-color:
#ffd700;' OnClick="document.bgColor='#ffd700';
document.body.style.background='#ffd700'">gold</button><button style='background-color:
#eedd82;' OnClick="document.bgColor='#eedd82';
document.body.style.background='#eedd82'">light
goldenrod</button><button style='background-color: #eedd82;'
OnClick="document.bgColor='#eedd82';
document.body.style.background='#eedd82'">lightgoldenrod</button><button style='background-color:
#daa520;' OnClick="document.bgColor='#daa520';
document.body.style.background='#daa520'">goldenrod</button><button style='background-color:
#b8860b;' OnClick="document.bgColor='#b8860b';
document.body.style.background='#b8860b'">dark
goldenrod</button><button style='background-color: #b8860b;'
OnClick="document.bgColor='#b8860b';
document.body.style.background='#b8860b'">darkgoldenrod</button><button style='background-color:
#bc8f8f;' OnClick="document.bgColor='#bc8f8f';
document.body.style.background='#bc8f8f'">rosy
brown</button><button style='background-color: #bc8f8f;'
OnClick="document.bgColor='#bc8f8f';
document.body.style.background='#bc8f8f'">rosybrown</button><button style='background-color:
#cd5c5c;' OnClick="document.bgColor='#cd5c5c';
document.body.style.background='#cd5c5c'">indian
red</button><button style='background-color: #cd5c5c;'
OnClick="document.bgColor='#cd5c5c';
document.body.style.background='#cd5c5c'">indianred</button><button style='background-color:
#8b4513;' OnClick="document.bgColor='#8b4513';
document.body.style.background='#8b4513'">saddle
brown</button><button style='background-color: #8b4513;'
OnClick="document.bgColor='#8b4513';
document.body.style.background='#8b4513'">saddlebrown</button><button style='background-color:
#a0522d;' OnClick="document.bgColor='#a0522d';
document.body.style.background='#a0522d'">sienna</button><button style='background-color:
#cd853f;' OnClick="document.bgColor='#cd853f';
document.body.style.background='#cd853f'">peru</button><button style='background-color:
#deb887;' OnClick="document.bgColor='#deb887';
document.body.style.background='#deb887'">burlywood</button><button style='background-color:
#f5f5dc;' OnClick="document.bgColor='#f5f5dc';
document.body.style.background='#f5f5dc'">beige</button><button style='background-color:
#f5deb3;' OnClick="document.bgColor='#f5deb3';
document.body.style.background='#f5deb3'">wheat</button><button style='background-color:
#f4a460;' OnClick="document.bgColor='#f4a460';
document.body.style.background='#f4a460'">sandy
brown</button><button style='background-color: #f4a460;'
OnClick="document.bgColor='#f4a460';
document.body.style.background='#f4a460'">sandybrown</button><button style='background-color:
#d2b48c;' OnClick="document.bgColor='#d2b48c';
document.body.style.background='#d2b48c'">tan</button><button style='background-color:
#d2691e;' OnClick="document.bgColor='#d2691e';
document.body.style.background='#d2691e'">chocolate</button><button style='background-color:
#b22222;' OnClick="document.bgColor='#b22222';
document.body.style.background='#b22222'">firebrick</button><button style='background-color:
#a52a2a;' OnClick="document.bgColor='#a52a2a';
document.body.style.background='#a52a2a'">brown</button><button style='background-color:
#e9967a;' OnClick="document.bgColor='#e9967a';
document.body.style.background='#e9967a'">dark
salmon</button><button style='background-color: #e9967a;'
OnClick="document.bgColor='#e9967a';
document.body.style.background='#e9967a'">darksalmon</button><button style='background-color:
#fa8072;' OnClick="document.bgColor='#fa8072';
document.body.style.background='#fa8072'">salmon</button><button style='background-color:
#ffa07a;' OnClick="document.bgColor='#ffa07a';
document.body.style.background='#ffa07a'">light
salmon</button><button style='background-color: #ffa07a;'
OnClick="document.bgColor='#ffa07a';
document.body.style.background='#ffa07a'">lightsalmon</button><button style='background-color:
#ffa500;' OnClick="document.bgColor='#ffa500';
document.body.style.background='#ffa500'">orange</button><button style='background-color:
#ff8c00;' OnClick="document.bgColor='#ff8c00';
document.body.style.background='#ff8c00'">dark
orange</button><button style='background-color: #ff8c00;'
OnClick="document.bgColor='#ff8c00';
document.body.style.background='#ff8c00'">darkorange</button><button style='background-color:
#ff7f50;' OnClick="document.bgColor='#ff7f50';
document.body.style.background='#ff7f50'">coral</button><button style='background-color:
#f08080;' OnClick="document.bgColor='#f08080';
document.body.style.background='#f08080'">light
coral</button><button style='background-color: #f08080;'
OnClick="document.bgColor='#f08080';
document.body.style.background='#f08080'">lightcoral</button><button style='background-color:
#ff6347;' OnClick="document.bgColor='#ff6347';
document.body.style.background='#ff6347'">tomato</button><button style='background-color:
#ff4500;' OnClick="document.bgColor='#ff4500';
document.body.style.background='#ff4500'">orange
red</button><button style='background-color: #ff4500;'
OnClick="document.bgColor='#ff4500';
document.body.style.background='#ff4500'">orangered</button><button style='background-color:
#ff0000;' OnClick="document.bgColor='#ff0000';
document.body.style.background='#ff0000'">red</button><button style='background-color:
#ff69b4;' OnClick="document.bgColor='#ff69b4';
document.body.style.background='#ff69b4'">hot
pink</button><button style='background-color: #ff69b4;'
OnClick="document.bgColor='#ff69b4';
document.body.style.background='#ff69b4'">hotpink</button><button style='background-color:
#ff1493;' OnClick="document.bgColor='#ff1493';
document.body.style.background='#ff1493'">deep
pink</button><button style='background-color: #ff1493;'
OnClick="document.bgColor='#ff1493';
document.body.style.background='#ff1493'">deeppink</button><button style='background-color:
#ffc0cb;' OnClick="document.bgColor='#ffc0cb';
document.body.style.background='#ffc0cb'">pink</button><button style='background-color:
#ffb6c1;' OnClick="document.bgColor='#ffb6c1';
document.body.style.background='#ffb6c1'">light
pink</button><button style='background-color: #ffb6c1;'
OnClick="document.bgColor='#ffb6c1';
document.body.style.background='#ffb6c1'">lightpink</button><button style='background-color:
#db7093;' OnClick="document.bgColor='#db7093';
document.body.style.background='#db7093'">pale violet
red</button><button style='background-color: #db7093;'
OnClick="document.bgColor='#db7093';
document.body.style.background='#db7093'">palevioletred</button><button style='background-color:
#b03060;' OnClick="document.bgColor='#b03060';
document.body.style.background='#b03060'">maroon</button><button style='background-color:
#c71585;' OnClick="document.bgColor='#c71585';
document.body.style.background='#c71585'">medium violet
red</button><button style='background-color: #c71585;'
OnClick="document.bgColor='#c71585';
document.body.style.background='#c71585'">mediumvioletred</button><button style='background-color:
#d02090;' OnClick="document.bgColor='#d02090';
document.body.style.background='#d02090'">violet
red</button><button style='background-color: #d02090;'
OnClick="document.bgColor='#d02090';
document.body.style.background='#d02090'">violetred</button><button style='background-color:
#ff00ff;' OnClick="document.bgColor='#ff00ff';
document.body.style.background='#ff00ff'">magenta</button><button style='background-color:
#ee82ee;' OnClick="document.bgColor='#ee82ee';
document.body.style.background='#ee82ee'">violet</button><button style='background-color:
#dda0dd;' OnClick="document.bgColor='#dda0dd';
document.body.style.background='#dda0dd'">plum</button><button style='background-color:
#da70d6;' OnClick="document.bgColor='#da70d6';
document.body.style.background='#da70d6'">orchid</button><button style='background-color:
#ba55d3;' OnClick="document.bgColor='#ba55d3';
document.body.style.background='#ba55d3'">medium
orchid</button><button style='background-color: #ba55d3;'
OnClick="document.bgColor='#ba55d3';
document.body.style.background='#ba55d3'">mediumorchid</button><button style='background-color:
#9932cc;' OnClick="document.bgColor='#9932cc';
document.body.style.background='#9932cc'">dark
orchid</button><button style='background-color: #9932cc;'
OnClick="document.bgColor='#9932cc';
document.body.style.background='#9932cc'">darkorchid</button><button style='background-color:
#9400d3;' OnClick="document.bgColor='#9400d3';
document.body.style.background='#9400d3'">dark
violet</button><button style='background-color: #9400d3;'
OnClick="document.bgColor='#9400d3';
document.body.style.background='#9400d3'">darkviolet</button><button style='background-color:
#8a2be2;' OnClick="document.bgColor='#8a2be2';
document.body.style.background='#8a2be2'">blue
violet</button><button style='background-color: #8a2be2;'
OnClick="document.bgColor='#8a2be2';
document.body.style.background='#8a2be2'">blueviolet</button><button style='background-color:
#a020f0;' OnClick="document.bgColor='#a020f0';
document.body.style.background='#a020f0'">purple</button><button style='background-color:
#9370db;' OnClick="document.bgColor='#9370db';
document.body.style.background='#9370db'">medium
purple</button><button style='background-color: #9370db;'
OnClick="document.bgColor='#9370db';
document.body.style.background='#9370db'">mediumpurple</button><button style='background-color:
#d8bfd8;' OnClick="document.bgColor='#d8bfd8';
document.body.style.background='#d8bfd8'">thistle</button><button style='background-color:
#fffafa;' OnClick="document.bgColor='#fffafa';
document.body.style.background='#fffafa'">snow1</button><button style='background-color:
#eee9e9;' OnClick="document.bgColor='#eee9e9';
document.body.style.background='#eee9e9'">snow2</button><button style='background-color:
#cdc9c9;' OnClick="document.bgColor='#cdc9c9';
document.body.style.background='#cdc9c9'">snow3</button><button style='background-color:
#8b8989;' OnClick="document.bgColor='#8b8989';
document.body.style.background='#8b8989'">snow4</button><button style='background-color:
#fff5ee;' OnClick="document.bgColor='#fff5ee';
document.body.style.background='#fff5ee'">seashell1</button><button style='background-color:
#eee5de;' OnClick="document.bgColor='#eee5de';
document.body.style.background='#eee5de'">seashell2</button><button style='background-color:
#cdc5bf;' OnClick="document.bgColor='#cdc5bf';
document.body.style.background='#cdc5bf'">seashell3</button><button style='background-color:
#8b8682;' OnClick="document.bgColor='#8b8682';
document.body.style.background='#8b8682'">seashell4</button><button style='background-color:
#ffefdb;' OnClick="document.bgColor='#ffefdb';
document.body.style.background='#ffefdb'">antiquewhite1</button><button style='background-color:
#eedfcc;' OnClick="document.bgColor='#eedfcc';
document.body.style.background='#eedfcc'">antiquewhite2</button><button style='background-color:
#cdc0b0;' OnClick="document.bgColor='#cdc0b0';
document.body.style.background='#cdc0b0'">antiquewhite3</button><button style='background-color:
#8b8378;' OnClick="document.bgColor='#8b8378';
document.body.style.background='#8b8378'">antiquewhite4</button><button style='background-color:
#ffe4c4;' OnClick="document.bgColor='#ffe4c4';
document.body.style.background='#ffe4c4'">bisque1</button><button style='background-color:
#eed5b7;' OnClick="document.bgColor='#eed5b7';
document.body.style.background='#eed5b7'">bisque2</button><button style='background-color:
#cdb79e;' OnClick="document.bgColor='#cdb79e';
document.body.style.background='#cdb79e'">bisque3</button><button style='background-color:
#8b7d6b;' OnClick="document.bgColor='#8b7d6b';
document.body.style.background='#8b7d6b'">bisque4</button><button style='background-color:
#ffdab9;' OnClick="document.bgColor='#ffdab9';
document.body.style.background='#ffdab9'">peachpuff1</button><button style='background-color:
#eecbad;' OnClick="document.bgColor='#eecbad';
document.body.style.background='#eecbad'">peachpuff2</button><button style='background-color:
#cdaf95;' OnClick="document.bgColor='#cdaf95';
document.body.style.background='#cdaf95'">peachpuff3</button><button style='background-color:
#8b7765;' OnClick="document.bgColor='#8b7765';
document.body.style.background='#8b7765'">peachpuff4</button><button style='background-color:
#ffdead;' OnClick="document.bgColor='#ffdead';
document.body.style.background='#ffdead'">navajowhite1</button><button style='background-color:
#eecfa1;' OnClick="document.bgColor='#eecfa1';
document.body.style.background='#eecfa1'">navajowhite2</button><button style='background-color:
#cdb38b;' OnClick="document.bgColor='#cdb38b';
document.body.style.background='#cdb38b'">navajowhite3</button><button style='background-color:
#8b795e;' OnClick="document.bgColor='#8b795e';
document.body.style.background='#8b795e'">navajowhite4</button><button style='background-color:
#fffacd;' OnClick="document.bgColor='#fffacd';
document.body.style.background='#fffacd'">lemonchiffon1</button><button style='background-color:
#eee9bf;' OnClick="document.bgColor='#eee9bf';
document.body.style.background='#eee9bf'">lemonchiffon2</button><button style='background-color:
#cdc9a5;' OnClick="document.bgColor='#cdc9a5';
document.body.style.background='#cdc9a5'">lemonchiffon3</button><button style='background-color:
#8b8970;' OnClick="document.bgColor='#8b8970';
document.body.style.background='#8b8970'">lemonchiffon4</button><button style='background-color:
#fff8dc;' OnClick="document.bgColor='#fff8dc';
document.body.style.background='#fff8dc'">cornsilk1</button><button style='background-color:
#eee8cd;' OnClick="document.bgColor='#eee8cd';
document.body.style.background='#eee8cd'">cornsilk2</button><button style='background-color:
#cdc8b1;' OnClick="document.bgColor='#cdc8b1';
document.body.style.background='#cdc8b1'">cornsilk3</button><button style='background-color:
#8b8878;' OnClick="document.bgColor='#8b8878';
document.body.style.background='#8b8878'">cornsilk4</button><button style='background-color:
#fffff0;' OnClick="document.bgColor='#fffff0';
document.body.style.background='#fffff0'">ivory1</button><button style='background-color:
#eeeee0;' OnClick="document.bgColor='#eeeee0';
document.body.style.background='#eeeee0'">ivory2</button><button style='background-color:
#cdcdc1;' OnClick="document.bgColor='#cdcdc1';
document.body.style.background='#cdcdc1'">ivory3</button><button style='background-color:
#8b8b83;' OnClick="document.bgColor='#8b8b83';
document.body.style.background='#8b8b83'">ivory4</button><button style='background-color:
#f0fff0;' OnClick="document.bgColor='#f0fff0';
document.body.style.background='#f0fff0'">honeydew1</button><button style='background-color:
#e0eee0;' OnClick="document.bgColor='#e0eee0';
document.body.style.background='#e0eee0'">honeydew2</button><button style='background-color:
#c1cdc1;' OnClick="document.bgColor='#c1cdc1';
document.body.style.background='#c1cdc1'">honeydew3</button><button style='background-color:
#838b83;' OnClick="document.bgColor='#838b83';
document.body.style.background='#838b83'">honeydew4</button><button style='background-color:
#fff0f5;' OnClick="document.bgColor='#fff0f5';
document.body.style.background='#fff0f5'">lavenderblush1</button><button style='background-color:
#eee0e5;' OnClick="document.bgColor='#eee0e5';
document.body.style.background='#eee0e5'">lavenderblush2</button><button style='background-color:
#cdc1c5;' OnClick="document.bgColor='#cdc1c5';
document.body.style.background='#cdc1c5'">lavenderblush3</button><button style='background-color:
#8b8386;' OnClick="document.bgColor='#8b8386';
document.body.style.background='#8b8386'">lavenderblush4</button><button style='background-color:
#ffe4e1;' OnClick="document.bgColor='#ffe4e1';
document.body.style.background='#ffe4e1'">mistyrose1</button><button style='background-color:
#eed5d2;' OnClick="document.bgColor='#eed5d2';
document.body.style.background='#eed5d2'">mistyrose2</button><button style='background-color:
#cdb7b5;' OnClick="document.bgColor='#cdb7b5';
document.body.style.background='#cdb7b5'">mistyrose3</button><button style='background-color:
#8b7d7b;' OnClick="document.bgColor='#8b7d7b';
document.body.style.background='#8b7d7b'">mistyrose4</button><button style='background-color:
#f0ffff;' OnClick="document.bgColor='#f0ffff';
document.body.style.background='#f0ffff'">azure1</button><button style='background-color:
#e0eeee;' OnClick="document.bgColor='#e0eeee';
document.body.style.background='#e0eeee'">azure2</button><button style='background-color:
#c1cdcd;' OnClick="document.bgColor='#c1cdcd';
document.body.style.background='#c1cdcd'">azure3</button><button style='background-color:
#838b8b;' OnClick="document.bgColor='#838b8b';
document.body.style.background='#838b8b'">azure4</button><button style='background-color:
#836fff;' OnClick="document.bgColor='#836fff';
document.body.style.background='#836fff'">slateblue1</button><button style='background-color:
#7a67ee;' OnClick="document.bgColor='#7a67ee';
document.body.style.background='#7a67ee'">slateblue2</button><button style='background-color:
#6959cd;' OnClick="document.bgColor='#6959cd';
document.body.style.background='#6959cd'">slateblue3</button><button style='background-color:
#473c8b;' OnClick="document.bgColor='#473c8b';
document.body.style.background='#473c8b'">slateblue4</button><button style='background-color:
#4876ff;' OnClick="document.bgColor='#4876ff';
document.body.style.background='#4876ff'">royalblue1</button><button style='background-color:
#436eee;' OnClick="document.bgColor='#436eee';
document.body.style.background='#436eee'">royalblue2</button><button style='background-color:
#3a5fcd;' OnClick="document.bgColor='#3a5fcd';
document.body.style.background='#3a5fcd'">royalblue3</button><button style='background-color:
#27408b;' OnClick="document.bgColor='#27408b';
document.body.style.background='#27408b'">royalblue4</button><button style='background-color:
#0000ff;' OnClick="document.bgColor='#0000ff';
document.body.style.background='#0000ff'">blue1</button><button style='background-color:
#0000ee;' OnClick="document.bgColor='#0000ee';
document.body.style.background='#0000ee'">blue2</button><button style='background-color:
#0000cd;' OnClick="document.bgColor='#0000cd';
document.body.style.background='#0000cd'">blue3</button><button style='background-color:
#00008b;' OnClick="document.bgColor='#00008b';
document.body.style.background='#00008b'">blue4</button><button style='background-color:
#1e90ff;' OnClick="document.bgColor='#1e90ff';
document.body.style.background='#1e90ff'">dodgerblue1</button><button style='background-color:
#1c86ee;' OnClick="document.bgColor='#1c86ee';
document.body.style.background='#1c86ee'">dodgerblue2</button><button style='background-color:
#1874cd;' OnClick="document.bgColor='#1874cd';
document.body.style.background='#1874cd'">dodgerblue3</button><button style='background-color:
#104e8b;' OnClick="document.bgColor='#104e8b';
document.body.style.background='#104e8b'">dodgerblue4</button><button style='background-color:
#63b8ff;' OnClick="document.bgColor='#63b8ff';
document.body.style.background='#63b8ff'">steelblue1</button><button style='background-color:
#5cacee;' OnClick="document.bgColor='#5cacee';
document.body.style.background='#5cacee'">steelblue2</button><button style='background-color:
#4f94cd;' OnClick="document.bgColor='#4f94cd';
document.body.style.background='#4f94cd'">steelblue3</button><button style='background-color:
#36648b;' OnClick="document.bgColor='#36648b';
document.body.style.background='#36648b'">steelblue4</button><button style='background-color:
#00bfff;' OnClick="document.bgColor='#00bfff';
document.body.style.background='#00bfff'">deepskyblue1</button><button style='background-color:
#00b2ee;' OnClick="document.bgColor='#00b2ee';
document.body.style.background='#00b2ee'">deepskyblue2</button><button style='background-color:
#009acd;' OnClick="document.bgColor='#009acd';
document.body.style.background='#009acd'">deepskyblue3</button><button style='background-color:
#00688b;' OnClick="document.bgColor='#00688b';
document.body.style.background='#00688b'">deepskyblue4</button><button style='background-color:
#87ceff;' OnClick="document.bgColor='#87ceff';
document.body.style.background='#87ceff'">skyblue1</button><button style='background-color:
#7ec0ee;' OnClick="document.bgColor='#7ec0ee';
document.body.style.background='#7ec0ee'">skyblue2</button><button style='background-color:
#6ca6cd;' OnClick="document.bgColor='#6ca6cd';
document.body.style.background='#6ca6cd'">skyblue3</button><button style='background-color:
#4a708b;' OnClick="document.bgColor='#4a708b';
document.body.style.background='#4a708b'">skyblue4</button><button style='background-color:
#b0e2ff;' OnClick="document.bgColor='#b0e2ff';
document.body.style.background='#b0e2ff'">lightskyblue1</button><button style='background-color:
#a4d3ee;' OnClick="document.bgColor='#a4d3ee';
document.body.style.background='#a4d3ee'">lightskyblue2</button><button style='background-color:
#8db6cd;' OnClick="document.bgColor='#8db6cd';
document.body.style.background='#8db6cd'">lightskyblue3</button><button style='background-color:
#607b8b;' OnClick="document.bgColor='#607b8b';
document.body.style.background='#607b8b'">lightskyblue4</button><button style='background-color:
#c6e2ff;' OnClick="document.bgColor='#c6e2ff';
document.body.style.background='#c6e2ff'">slategray1</button><button style='background-color:
#b9d3ee;' OnClick="document.bgColor='#b9d3ee';
document.body.style.background='#b9d3ee'">slategray2</button><button style='background-color:
#9fb6cd;' OnClick="document.bgColor='#9fb6cd';
document.body.style.background='#9fb6cd'">slategray3</button><button style='background-color:
#6c7b8b;' OnClick="document.bgColor='#6c7b8b';
document.body.style.background='#6c7b8b'">slategray4</button><button style='background-color:
#cae1ff;' OnClick="document.bgColor='#cae1ff';
document.body.style.background='#cae1ff'">lightsteelblue1</button><button style='background-color:
#bcd2ee;' OnClick="document.bgColor='#bcd2ee';
document.body.style.background='#bcd2ee'">lightsteelblue2</button><button style='background-color:
#a2b5cd;' OnClick="document.bgColor='#a2b5cd';
document.body.style.background='#a2b5cd'">lightsteelblue3</button><button style='background-color:
#6e7b8b;' OnClick="document.bgColor='#6e7b8b';
document.body.style.background='#6e7b8b'">lightsteelblue4</button><button style='background-color:
#bfefff;' OnClick="document.bgColor='#bfefff';
document.body.style.background='#bfefff'">lightblue1</button><button style='background-color:
#b2dfee;' OnClick="document.bgColor='#b2dfee';
document.body.style.background='#b2dfee'">lightblue2</button><button style='background-color:
#9ac0cd;' OnClick="document.bgColor='#9ac0cd';
document.body.style.background='#9ac0cd'">lightblue3</button><button style='background-color:
#68838b;' OnClick="document.bgColor='#68838b';
document.body.style.background='#68838b'">lightblue4</button><button style='background-color:
#e0ffff;' OnClick="document.bgColor='#e0ffff';
document.body.style.background='#e0ffff'">lightcyan1</button><button style='background-color:
#d1eeee;' OnClick="document.bgColor='#d1eeee';
document.body.style.background='#d1eeee'">lightcyan2</button><button style='background-color:
#b4cdcd;' OnClick="document.bgColor='#b4cdcd';
document.body.style.background='#b4cdcd'">lightcyan3</button><button style='background-color:
#7a8b8b;' OnClick="document.bgColor='#7a8b8b';
document.body.style.background='#7a8b8b'">lightcyan4</button><button style='background-color:
#bbffff;' OnClick="document.bgColor='#bbffff';
document.body.style.background='#bbffff'">paleturquoise1</button><button style='background-color:
#aeeeee;' OnClick="document.bgColor='#aeeeee';
document.body.style.background='#aeeeee'">paleturquoise2</button><button style='background-color:
#96cdcd;' OnClick="document.bgColor='#96cdcd';
document.body.style.background='#96cdcd'">paleturquoise3</button><button style='background-color:
#668b8b;' OnClick="document.bgColor='#668b8b';
document.body.style.background='#668b8b'">paleturquoise4</button><button style='background-color:
#98f5ff;' OnClick="document.bgColor='#98f5ff';
document.body.style.background='#98f5ff'">cadetblue1</button><button style='background-color:
#8ee5ee;' OnClick="document.bgColor='#8ee5ee';
document.body.style.background='#8ee5ee'">cadetblue2</button><button style='background-color:
#7ac5cd;' OnClick="document.bgColor='#7ac5cd';
document.body.style.background='#7ac5cd'">cadetblue3</button><button style='background-color:
#53868b;' OnClick="document.bgColor='#53868b';
document.body.style.background='#53868b'">cadetblue4</button><button style='background-color:
#00f5ff;' OnClick="document.bgColor='#00f5ff';
document.body.style.background='#00f5ff'">turquoise1</button><button style='background-color:
#00e5ee;' OnClick="document.bgColor='#00e5ee';
document.body.style.background='#00e5ee'">turquoise2</button><button style='background-color:
#00c5cd;' OnClick="document.bgColor='#00c5cd';
document.body.style.background='#00c5cd'">turquoise3</button><button style='background-color:
#00868b;' OnClick="document.bgColor='#00868b';
document.body.style.background='#00868b'">turquoise4</button><button style='background-color:
#00ffff;' OnClick="document.bgColor='#00ffff';
document.body.style.background='#00ffff'">cyan1</button><button style='background-color:
#00eeee;' OnClick="document.bgColor='#00eeee';
document.body.style.background='#00eeee'">cyan2</button><button style='background-color:
#00cdcd;' OnClick="document.bgColor='#00cdcd';
document.body.style.background='#00cdcd'">cyan3</button><button style='background-color:
#008b8b;' OnClick="document.bgColor='#008b8b';
document.body.style.background='#008b8b'">cyan4</button><button style='background-color:
#97ffff;' OnClick="document.bgColor='#97ffff';
document.body.style.background='#97ffff'">darkslategray1</button><button style='background-color:
#8deeee;' OnClick="document.bgColor='#8deeee';
document.body.style.background='#8deeee'">darkslategray2</button><button style='background-color:
#79cdcd;' OnClick="document.bgColor='#79cdcd';
document.body.style.background='#79cdcd'">darkslategray3</button><button style='background-color:
#528b8b;' OnClick="document.bgColor='#528b8b';
document.body.style.background='#528b8b'">darkslategray4</button><button style='background-color:
#7fffd4;' OnClick="document.bgColor='#7fffd4';
document.body.style.background='#7fffd4'">aquamarine1</button><button style='background-color:
#76eec6;' OnClick="document.bgColor='#76eec6';
document.body.style.background='#76eec6'">aquamarine2</button><button style='background-color:
#66cdaa;' OnClick="document.bgColor='#66cdaa';
document.body.style.background='#66cdaa'">aquamarine3</button><button style='background-color:
#458b74;' OnClick="document.bgColor='#458b74';
document.body.style.background='#458b74'">aquamarine4</button><button style='background-color:
#c1ffc1;' OnClick="document.bgColor='#c1ffc1';
document.body.style.background='#c1ffc1'">darkseagreen1</button><button style='background-color:
#b4eeb4;' OnClick="document.bgColor='#b4eeb4';
document.body.style.background='#b4eeb4'">darkseagreen2</button><button style='background-color:
#9bcd9b;' OnClick="document.bgColor='#9bcd9b';
document.body.style.background='#9bcd9b'">darkseagreen3</button><button style='background-color:
#698b69;' OnClick="document.bgColor='#698b69';
document.body.style.background='#698b69'">darkseagreen4</button><button style='background-color:
#54ff9f;' OnClick="document.bgColor='#54ff9f';
document.body.style.background='#54ff9f'">seagreen1</button><button style='background-color:
#4eee94;' OnClick="document.bgColor='#4eee94';
document.body.style.background='#4eee94'">seagreen2</button><button style='background-color:
#43cd80;' OnClick="document.bgColor='#43cd80';
document.body.style.background='#43cd80'">seagreen3</button><button style='background-color:
#2e8b57;' OnClick="document.bgColor='#2e8b57';
document.body.style.background='#2e8b57'">seagreen4</button><button style='background-color:
#9aff9a;' OnClick="document.bgColor='#9aff9a';
document.body.style.background='#9aff9a'">palegreen1</button><button style='background-color:
#90ee90;' OnClick="document.bgColor='#90ee90';
document.body.style.background='#90ee90'">palegreen2</button><button style='background-color:
#7ccd7c;' OnClick="document.bgColor='#7ccd7c';
document.body.style.background='#7ccd7c'">palegreen3</button><button style='background-color:
#548b54;' OnClick="document.bgColor='#548b54';
document.body.style.background='#548b54'">palegreen4</button><button style='background-color:
#00ff7f;' OnClick="document.bgColor='#00ff7f';
document.body.style.background='#00ff7f'">springgreen1</button><button style='background-color:
#00ee76;' OnClick="document.bgColor='#00ee76';
document.body.style.background='#00ee76'">springgreen2</button><button style='background-color:
#00cd66;' OnClick="document.bgColor='#00cd66';
document.body.style.background='#00cd66'">springgreen3</button><button style='background-color:
#008b45;' OnClick="document.bgColor='#008b45';
document.body.style.background='#008b45'">springgreen4</button><button style='background-color:
#00ff00;' OnClick="document.bgColor='#00ff00';
document.body.style.background='#00ff00'">green1</button><button style='background-color:
#00ee00;' OnClick="document.bgColor='#00ee00';
document.body.style.background='#00ee00'">green2</button><button style='background-color:
#00cd00;' OnClick="document.bgColor='#00cd00';
document.body.style.background='#00cd00'">green3</button><button style='background-color:
#008b00;' OnClick="document.bgColor='#008b00';
document.body.style.background='#008b00'">green4</button><button style='background-color:
#7fff00;' OnClick="document.bgColor='#7fff00';
document.body.style.background='#7fff00'">chartreuse1</button><button style='background-color:
#76ee00;' OnClick="document.bgColor='#76ee00';
document.body.style.background='#76ee00'">chartreuse2</button><button style='background-color:
#66cd00;' OnClick="document.bgColor='#66cd00';
document.body.style.background='#66cd00'">chartreuse3</button><button style='background-color:
#458b00;' OnClick="document.bgColor='#458b00';
document.body.style.background='#458b00'">chartreuse4</button><button style='background-color:
#c0ff3e;' OnClick="document.bgColor='#c0ff3e';
document.body.style.background='#c0ff3e'">olivedrab1</button><button style='background-color:
#b3ee3a;' OnClick="document.bgColor='#b3ee3a';
document.body.style.background='#b3ee3a'">olivedrab2</button><button style='background-color:
#9acd32;' OnClick="document.bgColor='#9acd32';
document.body.style.background='#9acd32'">olivedrab3</button><button style='background-color:
#698b22;' OnClick="document.bgColor='#698b22';
document.body.style.background='#698b22'">olivedrab4</button><button style='background-color:
#caff70;' OnClick="document.bgColor='#caff70';
document.body.style.background='#caff70'">darkolivegreen1</button><button style='background-color:
#bcee68;' OnClick="document.bgColor='#bcee68';
document.body.style.background='#bcee68'">darkolivegreen2</button><button style='background-color:
#a2cd5a;' OnClick="document.bgColor='#a2cd5a';
document.body.style.background='#a2cd5a'">darkolivegreen3</button><button style='background-color:
#6e8b3d;' OnClick="document.bgColor='#6e8b3d';
document.body.style.background='#6e8b3d'">darkolivegreen4</button><button style='background-color:
#fff68f;' OnClick="document.bgColor='#fff68f';
document.body.style.background='#fff68f'">khaki1</button><button style='background-color:
#eee685;' OnClick="document.bgColor='#eee685';
document.body.style.background='#eee685'">khaki2</button><button style='background-color:
#cdc673;' OnClick="document.bgColor='#cdc673';
document.body.style.background='#cdc673'">khaki3</button><button style='background-color:
#8b864e;' OnClick="document.bgColor='#8b864e';
document.body.style.background='#8b864e'">khaki4</button><button style='background-color:
#ffec8b;' OnClick="document.bgColor='#ffec8b';
document.body.style.background='#ffec8b'">lightgoldenrod1</button><button style='background-color:
#eedc82;' OnClick="document.bgColor='#eedc82';
document.body.style.background='#eedc82'">lightgoldenrod2</button><button style='background-color:
#cdbe70;' OnClick="document.bgColor='#cdbe70';
document.body.style.background='#cdbe70'">lightgoldenrod3</button><button style='background-color:
#8b814c;' OnClick="document.bgColor='#8b814c';
document.body.style.background='#8b814c'">lightgoldenrod4</button><button style='background-color:
#ffffe0;' OnClick="document.bgColor='#ffffe0';
document.body.style.background='#ffffe0'">lightyellow1</button><button style='background-color:
#eeeed1;' OnClick="document.bgColor='#eeeed1';
document.body.style.background='#eeeed1'">lightyellow2</button><button style='background-color:
#cdcdb4;' OnClick="document.bgColor='#cdcdb4';
document.body.style.background='#cdcdb4'">lightyellow3</button><button style='background-color:
#8b8b7a;' OnClick="document.bgColor='#8b8b7a';
document.body.style.background='#8b8b7a'">lightyellow4</button><button style='background-color:
#ffff00;' OnClick="document.bgColor='#ffff00';
document.body.style.background='#ffff00'">yellow1</button><button style='background-color:
#eeee00;' OnClick="document.bgColor='#eeee00';
document.body.style.background='#eeee00'">yellow2</button><button style='background-color:
#cdcd00;' OnClick="document.bgColor='#cdcd00';
document.body.style.background='#cdcd00'">yellow3</button><button style='background-color:
#8b8b00;' OnClick="document.bgColor='#8b8b00';
document.body.style.background='#8b8b00'">yellow4</button><button style='background-color:
#ffd700;' OnClick="document.bgColor='#ffd700';
document.body.style.background='#ffd700'">gold1</button><button style='background-color:
#eec900;' OnClick="document.bgColor='#eec900';
document.body.style.background='#eec900'">gold2</button><button style='background-color:
#cdad00;' OnClick="document.bgColor='#cdad00';
document.body.style.background='#cdad00'">gold3</button><button style='background-color:
#8b7500;' OnClick="document.bgColor='#8b7500';
document.body.style.background='#8b7500'">gold4</button><button style='background-color:
#ffc125;' OnClick="document.bgColor='#ffc125';
document.body.style.background='#ffc125'">goldenrod1</button><button style='background-color:
#eeb422;' OnClick="document.bgColor='#eeb422';
document.body.style.background='#eeb422'">goldenrod2</button><button style='background-color:
#cd9b1d;' OnClick="document.bgColor='#cd9b1d';
document.body.style.background='#cd9b1d'">goldenrod3</button><button style='background-color:
#8b6914;' OnClick="document.bgColor='#8b6914';
document.body.style.background='#8b6914'">goldenrod4</button><button style='background-color:
#ffb90f;' OnClick="document.bgColor='#ffb90f';
document.body.style.background='#ffb90f'">darkgoldenrod1</button><button style='background-color:
#eead0e;' OnClick="document.bgColor='#eead0e';
document.body.style.background='#eead0e'">darkgoldenrod2</button><button style='background-color:
#cd950c;' OnClick="document.bgColor='#cd950c';
document.body.style.background='#cd950c'">darkgoldenrod3</button><button style='background-color:
#8b6508;' OnClick="document.bgColor='#8b6508';
document.body.style.background='#8b6508'">darkgoldenrod4</button><button style='background-color:
#ffc1c1;' OnClick="document.bgColor='#ffc1c1';
document.body.style.background='#ffc1c1'">rosybrown1</button><button style='background-color:
#eeb4b4;' OnClick="document.bgColor='#eeb4b4';
document.body.style.background='#eeb4b4'">rosybrown2</button><button style='background-color:
#cd9b9b;' OnClick="document.bgColor='#cd9b9b';
document.body.style.background='#cd9b9b'">rosybrown3</button><button style='background-color:
#8b6969;' OnClick="document.bgColor='#8b6969';
document.body.style.background='#8b6969'">rosybrown4</button><button style='background-color:
#ff6a6a;' OnClick="document.bgColor='#ff6a6a';
document.body.style.background='#ff6a6a'">indianred1</button><button style='background-color:
#ee6363;' OnClick="document.bgColor='#ee6363';
document.body.style.background='#ee6363'">indianred2</button><button style='background-color:
#cd5555;' OnClick="document.bgColor='#cd5555';
document.body.style.background='#cd5555'">indianred3</button><button style='background-color:
#8b3a3a;' OnClick="document.bgColor='#8b3a3a';
document.body.style.background='#8b3a3a'">indianred4</button><button style='background-color:
#ff8247;' OnClick="document.bgColor='#ff8247';
document.body.style.background='#ff8247'">sienna1</button><button style='background-color:
#ee7942;' OnClick="document.bgColor='#ee7942';
document.body.style.background='#ee7942'">sienna2</button><button style='background-color:
#cd6839;' OnClick="document.bgColor='#cd6839';
document.body.style.background='#cd6839'">sienna3</button><button style='background-color:
#8b4726;' OnClick="document.bgColor='#8b4726';
document.body.style.background='#8b4726'">sienna4</button><button style='background-color:
#ffd39b;' OnClick="document.bgColor='#ffd39b';
document.body.style.background='#ffd39b'">burlywood1</button><button style='background-color:
#eec591;' OnClick="document.bgColor='#eec591';
document.body.style.background='#eec591'">burlywood2</button><button style='background-color:
#cdaa7d;' OnClick="document.bgColor='#cdaa7d';
document.body.style.background='#cdaa7d'">burlywood3</button><button style='background-color:
#8b7355;' OnClick="document.bgColor='#8b7355';
document.body.style.background='#8b7355'">burlywood4</button><button style='background-color:
#ffe7ba;' OnClick="document.bgColor='#ffe7ba';
document.body.style.background='#ffe7ba'">wheat1</button><button style='background-color:
#eed8ae;' OnClick="document.bgColor='#eed8ae';
document.body.style.background='#eed8ae'">wheat2</button><button style='background-color:
#cdba96;' OnClick="document.bgColor='#cdba96';
document.body.style.background='#cdba96'">wheat3</button><button style='background-color:
#8b7e66;' OnClick="document.bgColor='#8b7e66';
document.body.style.background='#8b7e66'">wheat4</button><button style='background-color:
#ffa54f;' OnClick="document.bgColor='#ffa54f';
document.body.style.background='#ffa54f'">tan1</button><button style='background-color:
#ee9a49;' OnClick="document.bgColor='#ee9a49';
document.body.style.background='#ee9a49'">tan2</button><button style='background-color:
#cd853f;' OnClick="document.bgColor='#cd853f';
document.body.style.background='#cd853f'">tan3</button><button style='background-color:
#8b5a2b;' OnClick="document.bgColor='#8b5a2b';
document.body.style.background='#8b5a2b'">tan4</button><button style='background-color:
#ff7f24;' OnClick="document.bgColor='#ff7f24';
document.body.style.background='#ff7f24'">chocolate1</button><button style='background-color:
#ee7621;' OnClick="document.bgColor='#ee7621';
document.body.style.background='#ee7621'">chocolate2</button><button style='background-color:
#cd661d;' OnClick="document.bgColor='#cd661d';
document.body.style.background='#cd661d'">chocolate3</button><button style='background-color:
#8b4513;' OnClick="document.bgColor='#8b4513';
document.body.style.background='#8b4513'">chocolate4</button><button style='background-color:
#ff3030;' OnClick="document.bgColor='#ff3030';
document.body.style.background='#ff3030'">firebrick1</button><button style='background-color:
#ee2c2c;' OnClick="document.bgColor='#ee2c2c';
document.body.style.background='#ee2c2c'">firebrick2</button><button style='background-color:
#cd2626;' OnClick="document.bgColor='#cd2626';
document.body.style.background='#cd2626'">firebrick3</button><button style='background-color:
#8b1a1a;' OnClick="document.bgColor='#8b1a1a';
document.body.style.background='#8b1a1a'">firebrick4</button><button style='background-color:
#ff4040;' OnClick="document.bgColor='#ff4040';
document.body.style.background='#ff4040'">brown1</button><button style='background-color:
#ee3b3b;' OnClick="document.bgColor='#ee3b3b';
document.body.style.background='#ee3b3b'">brown2</button><button style='background-color:
#cd3333;' OnClick="document.bgColor='#cd3333';
document.body.style.background='#cd3333'">brown3</button><button style='background-color:
#8b2323;' OnClick="document.bgColor='#8b2323';
document.body.style.background='#8b2323'">brown4</button><button style='background-color:
#ff8c69;' OnClick="document.bgColor='#ff8c69';
document.body.style.background='#ff8c69'">salmon1</button><button style='background-color:
#ee8262;' OnClick="document.bgColor='#ee8262';
document.body.style.background='#ee8262'">salmon2</button><button style='background-color:
#cd7054;' OnClick="document.bgColor='#cd7054';
document.body.style.background='#cd7054'">salmon3</button><button style='background-color:
#8b4c39;' OnClick="document.bgColor='#8b4c39';
document.body.style.background='#8b4c39'">salmon4</button><button style='background-color:
#ffa07a;' OnClick="document.bgColor='#ffa07a';
document.body.style.background='#ffa07a'">lightsalmon1</button><button style='background-color:
#ee9572;' OnClick="document.bgColor='#ee9572';
document.body.style.background='#ee9572'">lightsalmon2</button><button style='background-color:
#cd8162;' OnClick="document.bgColor='#cd8162';
document.body.style.background='#cd8162'">lightsalmon3</button><button style='background-color:
#8b5742;' OnClick="document.bgColor='#8b5742';
document.body.style.background='#8b5742'">lightsalmon4</button><button style='background-color:
#ffa500;' OnClick="document.bgColor='#ffa500';
document.body.style.background='#ffa500'">orange1</button><button style='background-color:
#ee9a00;' OnClick="document.bgColor='#ee9a00';
document.body.style.background='#ee9a00'">orange2</button><button style='background-color:
#cd8500;' OnClick="document.bgColor='#cd8500';
document.body.style.background='#cd8500'">orange3</button><button style='background-color:
#8b5a00;' OnClick="document.bgColor='#8b5a00';
document.body.style.background='#8b5a00'">orange4</button><button style='background-color:
#ff7f00;' OnClick="document.bgColor='#ff7f00';
document.body.style.background='#ff7f00'">darkorange1</button><button style='background-color:
#ee7600;' OnClick="document.bgColor='#ee7600';
document.body.style.background='#ee7600'">darkorange2</button><button style='background-color:
#cd6600;' OnClick="document.bgColor='#cd6600';
document.body.style.background='#cd6600'">darkorange3</button><button style='background-color:
#8b4500;' OnClick="document.bgColor='#8b4500';
document.body.style.background='#8b4500'">darkorange4</button><button style='background-color:
#ff7256;' OnClick="document.bgColor='#ff7256';
document.body.style.background='#ff7256'">coral1</button><button style='background-color:
#ee6a50;' OnClick="document.bgColor='#ee6a50';
document.body.style.background='#ee6a50'">coral2</button><button style='background-color:
#cd5b45;' OnClick="document.bgColor='#cd5b45';
document.body.style.background='#cd5b45'">coral3</button><button style='background-color:
#8b3e2f;' OnClick="document.bgColor='#8b3e2f';
document.body.style.background='#8b3e2f'">coral4</button><button style='background-color:
#ff6347;' OnClick="document.bgColor='#ff6347';
document.body.style.background='#ff6347'">tomato1</button><button style='background-color:
#ee5c42;' OnClick="document.bgColor='#ee5c42';
document.body.style.background='#ee5c42'">tomato2</button><button style='background-color:
#cd4f39;' OnClick="document.bgColor='#cd4f39';
document.body.style.background='#cd4f39'">tomato3</button><button style='background-color:
#8b3626;' OnClick="document.bgColor='#8b3626';
document.body.style.background='#8b3626'">tomato4</button><button style='background-color:
#ff4500;' OnClick="document.bgColor='#ff4500';
document.body.style.background='#ff4500'">orangered1</button><button style='background-color:
#ee4000;' OnClick="document.bgColor='#ee4000';
document.body.style.background='#ee4000'">orangered2</button><button style='background-color:
#cd3700;' OnClick="document.bgColor='#cd3700';
document.body.style.background='#cd3700'">orangered3</button><button style='background-color:
#8b2500;' OnClick="document.bgColor='#8b2500';
document.body.style.background='#8b2500'">orangered4</button><button style='background-color:
#ff0000;' OnClick="document.bgColor='#ff0000';
document.body.style.background='#ff0000'">red1</button><button style='background-color:
#ee0000;' OnClick="document.bgColor='#ee0000';
document.body.style.background='#ee0000'">red2</button><button style='background-color:
#cd0000;' OnClick="document.bgColor='#cd0000';
document.body.style.background='#cd0000'">red3</button><button style='background-color:
#8b0000;' OnClick="document.bgColor='#8b0000';
document.body.style.background='#8b0000'">red4</button><button style='background-color:
#ff1493;' OnClick="document.bgColor='#ff1493';
document.body.style.background='#ff1493'">deeppink1</button><button style='background-color:
#ee1289;' OnClick="document.bgColor='#ee1289';
document.body.style.background='#ee1289'">deeppink2</button><button style='background-color:
#cd1076;' OnClick="document.bgColor='#cd1076';
document.body.style.background='#cd1076'">deeppink3</button><button style='background-color:
#8b0a50;' OnClick="document.bgColor='#8b0a50';
document.body.style.background='#8b0a50'">deeppink4</button><button style='background-color:
#ff6eb4;' OnClick="document.bgColor='#ff6eb4';
document.body.style.background='#ff6eb4'">hotpink1</button><button style='background-color:
#ee6aa7;' OnClick="document.bgColor='#ee6aa7';
document.body.style.background='#ee6aa7'">hotpink2</button><button style='background-color:
#cd6090;' OnClick="document.bgColor='#cd6090';
document.body.style.background='#cd6090'">hotpink3</button><button style='background-color:
#8b3a62;' OnClick="document.bgColor='#8b3a62';
document.body.style.background='#8b3a62'">hotpink4</button><button style='background-color:
#ffb5c5;' OnClick="document.bgColor='#ffb5c5';
document.body.style.background='#ffb5c5'">pink1</button><button style='background-color:
#eea9b8;' OnClick="document.bgColor='#eea9b8';
document.body.style.background='#eea9b8'">pink2</button><button style='background-color:
#cd919e;' OnClick="document.bgColor='#cd919e';
document.body.style.background='#cd919e'">pink3</button><button style='background-color:
#8b636c;' OnClick="document.bgColor='#8b636c';
document.body.style.background='#8b636c'">pink4</button><button style='background-color:
#ffaeb9;' OnClick="document.bgColor='#ffaeb9';
document.body.style.background='#ffaeb9'">lightpink1</button><button style='background-color:
#eea2ad;' OnClick="document.bgColor='#eea2ad';
document.body.style.background='#eea2ad'">lightpink2</button><button style='background-color:
#cd8c95;' OnClick="document.bgColor='#cd8c95';
document.body.style.background='#cd8c95'">lightpink3</button><button style='background-color:
#8b5f65;' OnClick="document.bgColor='#8b5f65';
document.body.style.background='#8b5f65'">lightpink4</button><button style='background-color:
#ff82ab;' OnClick="document.bgColor='#ff82ab';
document.body.style.background='#ff82ab'">palevioletred1</button><button style='background-color:
#ee799f;' OnClick="document.bgColor='#ee799f';
document.body.style.background='#ee799f'">palevioletred2</button><button style='background-color:
#cd6889;' OnClick="document.bgColor='#cd6889';
document.body.style.background='#cd6889'">palevioletred3</button><button style='background-color:
#8b475d;' OnClick="document.bgColor='#8b475d';
document.body.style.background='#8b475d'">palevioletred4</button><button style='background-color:
#ff34b3;' OnClick="document.bgColor='#ff34b3';
document.body.style.background='#ff34b3'">maroon1</button><button style='background-color:
#ee30a7;' OnClick="document.bgColor='#ee30a7';
document.body.style.background='#ee30a7'">maroon2</button><button style='background-color:
#cd2990;' OnClick="document.bgColor='#cd2990';
document.body.style.background='#cd2990'">maroon3</button><button style='background-color:
#8b1c62;' OnClick="document.bgColor='#8b1c62';
document.body.style.background='#8b1c62'">maroon4</button><button style='background-color:
#ff3e96;' OnClick="document.bgColor='#ff3e96';
document.body.style.background='#ff3e96'">violetred1</button><button style='background-color:
#ee3a8c;' OnClick="document.bgColor='#ee3a8c';
document.body.style.background='#ee3a8c'">violetred2</button><button style='background-color:
#cd3278;' OnClick="document.bgColor='#cd3278';
document.body.style.background='#cd3278'">violetred3</button><button style='background-color:
#8b2252;' OnClick="document.bgColor='#8b2252';
document.body.style.background='#8b2252'">violetred4</button><button style='background-color:
#ff00ff;' OnClick="document.bgColor='#ff00ff';
document.body.style.background='#ff00ff'">magenta1</button><button style='background-color:
#ee00ee;' OnClick="document.bgColor='#ee00ee';
document.body.style.background='#ee00ee'">magenta2</button><button style='background-color:
#cd00cd;' OnClick="document.bgColor='#cd00cd';
document.body.style.background='#cd00cd'">magenta3</button><button style='background-color:
#8b008b;' OnClick="document.bgColor='#8b008b';
document.body.style.background='#8b008b'">magenta4</button><button style='background-color:
#ff83fa;' OnClick="document.bgColor='#ff83fa';
document.body.style.background='#ff83fa'">orchid1</button><button style='background-color:
#ee7ae9;' OnClick="document.bgColor='#ee7ae9';
document.body.style.background='#ee7ae9'">orchid2</button><button style='background-color:
#cd69c9;' OnClick="document.bgColor='#cd69c9';
document.body.style.background='#cd69c9'">orchid3</button><button style='background-color:
#8b4789;' OnClick="document.bgColor='#8b4789';
document.body.style.background='#8b4789'">orchid4</button><button style='background-color:
#ffbbff;' OnClick="document.bgColor='#ffbbff';
document.body.style.background='#ffbbff'">plum1</button><button style='background-color:
#eeaeee;' OnClick="document.bgColor='#eeaeee';
document.body.style.background='#eeaeee'">plum2</button><button style='background-color:
#cd96cd;' OnClick="document.bgColor='#cd96cd';
document.body.style.background='#cd96cd'">plum3</button><button style='background-color:
#8b668b;' OnClick="document.bgColor='#8b668b';
document.body.style.background='#8b668b'">plum4</button><button style='background-color:
#e066ff;' OnClick="document.bgColor='#e066ff';
document.body.style.background='#e066ff'">mediumorchid1</button><button style='background-color:
#d15fee;' OnClick="document.bgColor='#d15fee';
document.body.style.background='#d15fee'">mediumorchid2</button><button style='background-color:
#b452cd;' OnClick="document.bgColor='#b452cd';
document.body.style.background='#b452cd'">mediumorchid3</button><button style='background-color:
#7a378b;' OnClick="document.bgColor='#7a378b';
document.body.style.background='#7a378b'">mediumorchid4</button><button style='background-color:
#bf3eff;' OnClick="document.bgColor='#bf3eff';
document.body.style.background='#bf3eff'">darkorchid1</button><button style='background-color:
#b23aee;' OnClick="document.bgColor='#b23aee';
document.body.style.background='#b23aee'">darkorchid2</button><button style='background-color:
#9a32cd;' OnClick="document.bgColor='#9a32cd';
document.body.style.background='#9a32cd'">darkorchid3</button><button style='background-color:
#68228b;' OnClick="document.bgColor='#68228b';
document.body.style.background='#68228b'">darkorchid4</button><button style='background-color:
#9b30ff;' OnClick="document.bgColor='#9b30ff';
document.body.style.background='#9b30ff'">purple1</button><button style='background-color:
#912cee;' OnClick="document.bgColor='#912cee';
document.body.style.background='#912cee'">purple2</button><button style='background-color:
#7d26cd;' OnClick="document.bgColor='#7d26cd';
document.body.style.background='#7d26cd'">purple3</button><button style='background-color:
#551a8b;' OnClick="document.bgColor='#551a8b';
document.body.style.background='#551a8b'">purple4</button><button style='background-color:
#ab82ff;' OnClick="document.bgColor='#ab82ff';
document.body.style.background='#ab82ff'">mediumpurple1</button><button style='background-color:
#9f79ee;' OnClick="document.bgColor='#9f79ee';
document.body.style.background='#9f79ee'">mediumpurple2</button><button style='background-color:
#8968cd;' OnClick="document.bgColor='#8968cd';
document.body.style.background='#8968cd'">mediumpurple3</button><button style='background-color:
#5d478b;' OnClick="document.bgColor='#5d478b';
document.body.style.background='#5d478b'">mediumpurple4</button><button style='background-color:
#ffe1ff;' OnClick="document.bgColor='#ffe1ff';
document.body.style.background='#ffe1ff'">thistle1</button><button style='background-color:
#eed2ee;' OnClick="document.bgColor='#eed2ee';
document.body.style.background='#eed2ee'">thistle2</button><button style='background-color:
#cdb5cd;' OnClick="document.bgColor='#cdb5cd';
document.body.style.background='#cdb5cd'">thistle3</button><button style='background-color:
#8b7b8b;' OnClick="document.bgColor='#8b7b8b';
document.body.style.background='#8b7b8b'">thistle4</button><button style='background-color:
#000000;' OnClick="document.bgColor='#000000';
document.body.style.background='#000000'">gray0</button><button style='background-color:
#000000;' OnClick="document.bgColor='#000000';
document.body.style.background='#000000'">grey0</button><button style='background-color:
#030303;' OnClick="document.bgColor='#030303';
document.body.style.background='#030303'">gray1</button><button style='background-color:
#030303;' OnClick="document.bgColor='#030303';
document.body.style.background='#030303'">grey1</button><button style='background-color:
#050505;' OnClick="document.bgColor='#050505';
document.body.style.background='#050505'">gray2</button><button style='background-color:
#050505;' OnClick="document.bgColor='#050505';
document.body.style.background='#050505'">grey2</button><button style='background-color:
#080808;' OnClick="document.bgColor='#080808';
document.body.style.background='#080808'">gray3</button><button style='background-color:
#080808;' OnClick="document.bgColor='#080808';
document.body.style.background='#080808'">grey3</button><button style='background-color:
#0a0a0a;' OnClick="document.bgColor='#0a0a0a';
document.body.style.background='#0a0a0a'">gray4</button><button style='background-color:
#0a0a0a;' OnClick="document.bgColor='#0a0a0a';
document.body.style.background='#0a0a0a'">grey4</button><button style='background-color:
#0d0d0d;' OnClick="document.bgColor='#0d0d0d';
document.body.style.background='#0d0d0d'">gray5</button><button style='background-color:
#0d0d0d;' OnClick="document.bgColor='#0d0d0d';
document.body.style.background='#0d0d0d'">grey5</button><button style='background-color:
#0f0f0f;' OnClick="document.bgColor='#0f0f0f';
document.body.style.background='#0f0f0f'">gray6</button><button style='background-color:
#0f0f0f;' OnClick="document.bgColor='#0f0f0f';
document.body.style.background='#0f0f0f'">grey6</button><button style='background-color:
#121212;' OnClick="document.bgColor='#121212';
document.body.style.background='#121212'">gray7</button><button style='background-color:
#121212;' OnClick="document.bgColor='#121212';
document.body.style.background='#121212'">grey7</button><button style='background-color:
#141414;' OnClick="document.bgColor='#141414';
document.body.style.background='#141414'">gray8</button><button style='background-color:
#141414;' OnClick="document.bgColor='#141414';
document.body.style.background='#141414'">grey8</button><button style='background-color:
#171717;' OnClick="document.bgColor='#171717';
document.body.style.background='#171717'">gray9</button><button style='background-color:
#171717;' OnClick="document.bgColor='#171717';
document.body.style.background='#171717'">grey9</button><button style='background-color:
#1a1a1a;' OnClick="document.bgColor='#1a1a1a';
document.body.style.background='#1a1a1a'">gray10</button><button style='background-color:
#1a1a1a;' OnClick="document.bgColor='#1a1a1a';
document.body.style.background='#1a1a1a'">grey10</button><button style='background-color:
#1c1c1c;' OnClick="document.bgColor='#1c1c1c';
document.body.style.background='#1c1c1c'">gray11</button><button style='background-color:
#1c1c1c;' OnClick="document.bgColor='#1c1c1c';
document.body.style.background='#1c1c1c'">grey11</button><button style='background-color:
#1f1f1f;' OnClick="document.bgColor='#1f1f1f';
document.body.style.background='#1f1f1f'">gray12</button><button style='background-color:
#1f1f1f;' OnClick="document.bgColor='#1f1f1f';
document.body.style.background='#1f1f1f'">grey12</button><button style='background-color:
#212121;' OnClick="document.bgColor='#212121';
document.body.style.background='#212121'">gray13</button><button style='background-color:
#212121;' OnClick="document.bgColor='#212121';
document.body.style.background='#212121'">grey13</button><button style='background-color:
#242424;' OnClick="document.bgColor='#242424';
document.body.style.background='#242424'">gray14</button><button style='background-color:
#242424;' OnClick="document.bgColor='#242424';
document.body.style.background='#242424'">grey14</button><button style='background-color:
#262626;' OnClick="document.bgColor='#262626';
document.body.style.background='#262626'">gray15</button><button style='background-color:
#262626;' OnClick="document.bgColor='#262626';
document.body.style.background='#262626'">grey15</button><button style='background-color:
#292929;' OnClick="document.bgColor='#292929';
document.body.style.background='#292929'">gray16</button><button style='background-color:
#292929;' OnClick="document.bgColor='#292929';
document.body.style.background='#292929'">grey16</button><button style='background-color:
#2b2b2b;' OnClick="document.bgColor='#2b2b2b';
document.body.style.background='#2b2b2b'">gray17</button><button style='background-color:
#2b2b2b;' OnClick="document.bgColor='#2b2b2b';
document.body.style.background='#2b2b2b'">grey17</button><button style='background-color:
#2e2e2e;' OnClick="document.bgColor='#2e2e2e';
document.body.style.background='#2e2e2e'">gray18</button><button style='background-color:
#2e2e2e;' OnClick="document.bgColor='#2e2e2e';
document.body.style.background='#2e2e2e'">grey18</button><button style='background-color:
#303030;' OnClick="document.bgColor='#303030';
document.body.style.background='#303030'">gray19</button><button style='background-color:
#303030;' OnClick="document.bgColor='#303030';
document.body.style.background='#303030'">grey19</button><button style='background-color:
#333333;' OnClick="document.bgColor='#333333';
document.body.style.background='#333333'">gray20</button><button style='background-color:
#333333;' OnClick="document.bgColor='#333333';
document.body.style.background='#333333'">grey20</button><button style='background-color:
#363636;' OnClick="document.bgColor='#363636';
document.body.style.background='#363636'">gray21</button><button style='background-color:
#363636;' OnClick="document.bgColor='#363636';
document.body.style.background='#363636'">grey21</button><button style='background-color:
#383838;' OnClick="document.bgColor='#383838';
document.body.style.background='#383838'">gray22</button><button style='background-color:
#383838;' OnClick="document.bgColor='#383838';
document.body.style.background='#383838'">grey22</button><button style='background-color:
#3b3b3b;' OnClick="document.bgColor='#3b3b3b';
document.body.style.background='#3b3b3b'">gray23</button><button style='background-color:
#3b3b3b;' OnClick="document.bgColor='#3b3b3b';
document.body.style.background='#3b3b3b'">grey23</button><button style='background-color:
#3d3d3d;' OnClick="document.bgColor='#3d3d3d';
document.body.style.background='#3d3d3d'">gray24</button><button style='background-color:
#3d3d3d;' OnClick="document.bgColor='#3d3d3d';
document.body.style.background='#3d3d3d'">grey24</button><button style='background-color:
#404040;' OnClick="document.bgColor='#404040';
document.body.style.background='#404040'">gray25</button><button style='background-color:
#404040;' OnClick="document.bgColor='#404040';
document.body.style.background='#404040'">grey25</button><button style='background-color:
#424242;' OnClick="document.bgColor='#424242';
document.body.style.background='#424242'">gray26</button><button style='background-color:
#424242;' OnClick="document.bgColor='#424242';
document.body.style.background='#424242'">grey26</button><button style='background-color:
#454545;' OnClick="document.bgColor='#454545';
document.body.style.background='#454545'">gray27</button><button style='background-color:
#454545;' OnClick="document.bgColor='#454545';
document.body.style.background='#454545'">grey27</button><button style='background-color:
#474747;' OnClick="document.bgColor='#474747';
document.body.style.background='#474747'">gray28</button><button style='background-color:
#474747;' OnClick="document.bgColor='#474747';
document.body.style.background='#474747'">grey28</button><button style='background-color:
#4a4a4a;' OnClick="document.bgColor='#4a4a4a';
document.body.style.background='#4a4a4a'">gray29</button><button style='background-color:
#4a4a4a;' OnClick="document.bgColor='#4a4a4a';
document.body.style.background='#4a4a4a'">grey29</button><button style='background-color:
#4d4d4d;' OnClick="document.bgColor='#4d4d4d';
document.body.style.background='#4d4d4d'">gray30</button><button style='background-color:
#4d4d4d;' OnClick="document.bgColor='#4d4d4d';
document.body.style.background='#4d4d4d'">grey30</button><button style='background-color:
#4f4f4f;' OnClick="document.bgColor='#4f4f4f';
document.body.style.background='#4f4f4f'">gray31</button><button style='background-color:
#4f4f4f;' OnClick="document.bgColor='#4f4f4f';
document.body.style.background='#4f4f4f'">grey31</button><button style='background-color:
#525252;' OnClick="document.bgColor='#525252';
document.body.style.background='#525252'">gray32</button><button style='background-color:
#525252;' OnClick="document.bgColor='#525252';
document.body.style.background='#525252'">grey32</button><button style='background-color:
#545454;' OnClick="document.bgColor='#545454';
document.body.style.background='#545454'">gray33</button><button style='background-color:
#545454;' OnClick="document.bgColor='#545454';
document.body.style.background='#545454'">grey33</button><button style='background-color:
#575757;' OnClick="document.bgColor='#575757';
document.body.style.background='#575757'">gray34</button><button style='background-color:
#575757;' OnClick="document.bgColor='#575757';
document.body.style.background='#575757'">grey34</button><button style='background-color:
#595959;' OnClick="document.bgColor='#595959';
document.body.style.background='#595959'">gray35</button><button style='background-color:
#595959;' OnClick="document.bgColor='#595959';
document.body.style.background='#595959'">grey35</button><button style='background-color:
#5c5c5c;' OnClick="document.bgColor='#5c5c5c';
document.body.style.background='#5c5c5c'">gray36</button><button style='background-color:
#5c5c5c;' OnClick="document.bgColor='#5c5c5c';
document.body.style.background='#5c5c5c'">grey36</button><button style='background-color:
#5e5e5e;' OnClick="document.bgColor='#5e5e5e';
document.body.style.background='#5e5e5e'">gray37</button><button style='background-color:
#5e5e5e;' OnClick="document.bgColor='#5e5e5e';
document.body.style.background='#5e5e5e'">grey37</button><button style='background-color:
#616161;' OnClick="document.bgColor='#616161';
document.body.style.background='#616161'">gray38</button><button style='background-color:
#616161;' OnClick="document.bgColor='#616161';
document.body.style.background='#616161'">grey38</button><button style='background-color:
#636363;' OnClick="document.bgColor='#636363';
document.body.style.background='#636363'">gray39</button><button style='background-color:
#636363;' OnClick="document.bgColor='#636363';
document.body.style.background='#636363'">grey39</button><button style='background-color:
#666666;' OnClick="document.bgColor='#666666';
document.body.style.background='#666666'">gray40</button><button style='background-color:
#666666;' OnClick="document.bgColor='#666666';
document.body.style.background='#666666'">grey40</button><button style='background-color:
#696969;' OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">gray41</button><button style='background-color:
#696969;' OnClick="document.bgColor='#696969';
document.body.style.background='#696969'">grey41</button><button style='background-color:
#6b6b6b;' OnClick="document.bgColor='#6b6b6b';
document.body.style.background='#6b6b6b'">gray42</button><button style='background-color:
#6b6b6b;' OnClick="document.bgColor='#6b6b6b';
document.body.style.background='#6b6b6b'">grey42</button><button style='background-color:
#6e6e6e;' OnClick="document.bgColor='#6e6e6e';
document.body.style.background='#6e6e6e'">gray43</button><button style='background-color:
#6e6e6e;' OnClick="document.bgColor='#6e6e6e';
document.body.style.background='#6e6e6e'">grey43</button><button style='background-color:
#707070;' OnClick="document.bgColor='#707070';
document.body.style.background='#707070'">gray44</button><button style='background-color:
#707070;' OnClick="document.bgColor='#707070';
document.body.style.background='#707070'">grey44</button><button style='background-color:
#737373;' OnClick="document.bgColor='#737373';
document.body.style.background='#737373'">gray45</button><button style='background-color:
#737373;' OnClick="document.bgColor='#737373';
document.body.style.background='#737373'">grey45</button><button style='background-color:
#757575;' OnClick="document.bgColor='#757575';
document.body.style.background='#757575'">gray46</button><button style='background-color:
#757575;' OnClick="document.bgColor='#757575';
document.body.style.background='#757575'">grey46</button><button style='background-color:
#787878;' OnClick="document.bgColor='#787878';
document.body.style.background='#787878'">gray47</button><button style='background-color:
#787878;' OnClick="document.bgColor='#787878';
document.body.style.background='#787878'">grey47</button><button style='background-color:
#7a7a7a;' OnClick="document.bgColor='#7a7a7a';
document.body.style.background='#7a7a7a'">gray48</button><button style='background-color:
#7a7a7a;' OnClick="document.bgColor='#7a7a7a';
document.body.style.background='#7a7a7a'">grey48</button><button style='background-color:
#7d7d7d;' OnClick="document.bgColor='#7d7d7d';
document.body.style.background='#7d7d7d'">gray49</button><button style='background-color:
#7d7d7d;' OnClick="document.bgColor='#7d7d7d';
document.body.style.background='#7d7d7d'">grey49</button><button style='background-color:
#7f7f7f;' OnClick="document.bgColor='#7f7f7f';
document.body.style.background='#7f7f7f'">gray50</button><button style='background-color:
#7f7f7f;' OnClick="document.bgColor='#7f7f7f';
document.body.style.background='#7f7f7f'">grey50</button><button style='background-color:
#828282;' OnClick="document.bgColor='#828282';
document.body.style.background='#828282'">gray51</button><button style='background-color:
#828282;' OnClick="document.bgColor='#828282';
document.body.style.background='#828282'">grey51</button><button style='background-color:
#858585;' OnClick="document.bgColor='#858585';
document.body.style.background='#858585'">gray52</button><button style='background-color:
#858585;' OnClick="document.bgColor='#858585';
document.body.style.background='#858585'">grey52</button><button style='background-color:
#878787;' OnClick="document.bgColor='#878787';
document.body.style.background='#878787'">gray53</button><button style='background-color:
#878787;' OnClick="document.bgColor='#878787';
document.body.style.background='#878787'">grey53</button><button style='background-color:
#8a8a8a;' OnClick="document.bgColor='#8a8a8a';
document.body.style.background='#8a8a8a'">gray54</button><button style='background-color:
#8a8a8a;' OnClick="document.bgColor='#8a8a8a';
document.body.style.background='#8a8a8a'">grey54</button><button style='background-color:
#8c8c8c;' OnClick="document.bgColor='#8c8c8c';
document.body.style.background='#8c8c8c'">gray55</button><button style='background-color:
#8c8c8c;' OnClick="document.bgColor='#8c8c8c';
document.body.style.background='#8c8c8c'">grey55</button><button style='background-color:
#8f8f8f;' OnClick="document.bgColor='#8f8f8f';
document.body.style.background='#8f8f8f'">gray56</button><button style='background-color:
#8f8f8f;' OnClick="document.bgColor='#8f8f8f';
document.body.style.background='#8f8f8f'">grey56</button><button style='background-color:
#919191;' OnClick="document.bgColor='#919191';
document.body.style.background='#919191'">gray57</button><button style='background-color:
#919191;' OnClick="document.bgColor='#919191';
document.body.style.background='#919191'">grey57</button><button style='background-color:
#949494;' OnClick="document.bgColor='#949494';
document.body.style.background='#949494'">gray58</button><button style='background-color:
#949494;' OnClick="document.bgColor='#949494';
document.body.style.background='#949494'">grey58</button><button style='background-color:
#969696;' OnClick="document.bgColor='#969696';
document.body.style.background='#969696'">gray59</button><button style='background-color:
#969696;' OnClick="document.bgColor='#969696';
document.body.style.background='#969696'">grey59</button><button style='background-color:
#999999;' OnClick="document.bgColor='#999999';
document.body.style.background='#999999'">gray60</button><button style='background-color:
#999999;' OnClick="document.bgColor='#999999';
document.body.style.background='#999999'">grey60</button><button style='background-color:
#9c9c9c;' OnClick="document.bgColor='#9c9c9c';
document.body.style.background='#9c9c9c'">gray61</button><button style='background-color:
#9c9c9c;' OnClick="document.bgColor='#9c9c9c';
document.body.style.background='#9c9c9c'">grey61</button><button style='background-color:
#9e9e9e;' OnClick="document.bgColor='#9e9e9e';
document.body.style.background='#9e9e9e'">gray62</button><button style='background-color:
#9e9e9e;' OnClick="document.bgColor='#9e9e9e';
document.body.style.background='#9e9e9e'">grey62</button><button style='background-color:
#a1a1a1;' OnClick="document.bgColor='#a1a1a1';
document.body.style.background='#a1a1a1'">gray63</button><button style='background-color:
#a1a1a1;' OnClick="document.bgColor='#a1a1a1';
document.body.style.background='#a1a1a1'">grey63</button><button style='background-color:
#a3a3a3;' OnClick="document.bgColor='#a3a3a3';
document.body.style.background='#a3a3a3'">gray64</button><button style='background-color:
#a3a3a3;' OnClick="document.bgColor='#a3a3a3';
document.body.style.background='#a3a3a3'">grey64</button><button style='background-color:
#a6a6a6;' OnClick="document.bgColor='#a6a6a6';
document.body.style.background='#a6a6a6'">gray65</button><button style='background-color:
#a6a6a6;' OnClick="document.bgColor='#a6a6a6';
document.body.style.background='#a6a6a6'">grey65</button><button style='background-color:
#a8a8a8;' OnClick="document.bgColor='#a8a8a8';
document.body.style.background='#a8a8a8'">gray66</button><button style='background-color:
#a8a8a8;' OnClick="document.bgColor='#a8a8a8';
document.body.style.background='#a8a8a8'">grey66</button><button style='background-color:
#ababab;' OnClick="document.bgColor='#ababab';
document.body.style.background='#ababab'">gray67</button><button style='background-color:
#ababab;' OnClick="document.bgColor='#ababab';
document.body.style.background='#ababab'">grey67</button><button style='background-color:
#adadad;' OnClick="document.bgColor='#adadad';
document.body.style.background='#adadad'">gray68</button><button style='background-color:
#adadad;' OnClick="document.bgColor='#adadad';
document.body.style.background='#adadad'">grey68</button><button style='background-color:
#b0b0b0;' OnClick="document.bgColor='#b0b0b0';
document.body.style.background='#b0b0b0'">gray69</button><button style='background-color:
#b0b0b0;' OnClick="document.bgColor='#b0b0b0';
document.body.style.background='#b0b0b0'">grey69</button><button style='background-color:
#b3b3b3;' OnClick="document.bgColor='#b3b3b3';
document.body.style.background='#b3b3b3'">gray70</button><button style='background-color:
#b3b3b3;' OnClick="document.bgColor='#b3b3b3';
document.body.style.background='#b3b3b3'">grey70</button><button style='background-color:
#b5b5b5;' OnClick="document.bgColor='#b5b5b5';
document.body.style.background='#b5b5b5'">gray71</button><button style='background-color:
#b5b5b5;' OnClick="document.bgColor='#b5b5b5';
document.body.style.background='#b5b5b5'">grey71</button><button style='background-color:
#b8b8b8;' OnClick="document.bgColor='#b8b8b8';
document.body.style.background='#b8b8b8'">gray72</button><button style='background-color:
#b8b8b8;' OnClick="document.bgColor='#b8b8b8';
document.body.style.background='#b8b8b8'">grey72</button><button style='background-color:
#bababa;' OnClick="document.bgColor='#bababa';
document.body.style.background='#bababa'">gray73</button><button style='background-color:
#bababa;' OnClick="document.bgColor='#bababa';
document.body.style.background='#bababa'">grey73</button><button style='background-color:
#bdbdbd;' OnClick="document.bgColor='#bdbdbd';
document.body.style.background='#bdbdbd'">gray74</button><button style='background-color:
#bdbdbd;' OnClick="document.bgColor='#bdbdbd';
document.body.style.background='#bdbdbd'">grey74</button><button style='background-color:
#bfbfbf;' OnClick="document.bgColor='#bfbfbf';
document.body.style.background='#bfbfbf'">gray75</button><button style='background-color:
#bfbfbf;' OnClick="document.bgColor='#bfbfbf';
document.body.style.background='#bfbfbf'">grey75</button><button style='background-color:
#c2c2c2;' OnClick="document.bgColor='#c2c2c2';
document.body.style.background='#c2c2c2'">gray76</button><button style='background-color:
#c2c2c2;' OnClick="document.bgColor='#c2c2c2';
document.body.style.background='#c2c2c2'">grey76</button><button style='background-color:
#c4c4c4;' OnClick="document.bgColor='#c4c4c4';
document.body.style.background='#c4c4c4'">gray77</button><button style='background-color:
#c4c4c4;' OnClick="document.bgColor='#c4c4c4';
document.body.style.background='#c4c4c4'">grey77</button><button style='background-color:
#c7c7c7;' OnClick="document.bgColor='#c7c7c7';
document.body.style.background='#c7c7c7'">gray78</button><button style='background-color:
#c7c7c7;' OnClick="document.bgColor='#c7c7c7';
document.body.style.background='#c7c7c7'">grey78</button><button style='background-color:
#c9c9c9;' OnClick="document.bgColor='#c9c9c9';
document.body.style.background='#c9c9c9'">gray79</button><button style='background-color:
#c9c9c9;' OnClick="document.bgColor='#c9c9c9';
document.body.style.background='#c9c9c9'">grey79</button><button style='background-color:
#cccccc;' OnClick="document.bgColor='#cccccc';
document.body.style.background='#cccccc'">gray80</button><button style='background-color:
#cccccc;' OnClick="document.bgColor='#cccccc';
document.body.style.background='#cccccc'">grey80</button><button style='background-color:
#cfcfcf;' OnClick="document.bgColor='#cfcfcf';
document.body.style.background='#cfcfcf'">gray81</button><button style='background-color:
#cfcfcf;' OnClick="document.bgColor='#cfcfcf';
document.body.style.background='#cfcfcf'">grey81</button><button style='background-color:
#d1d1d1;' OnClick="document.bgColor='#d1d1d1';
document.body.style.background='#d1d1d1'">gray82</button><button style='background-color:
#d1d1d1;' OnClick="document.bgColor='#d1d1d1';
document.body.style.background='#d1d1d1'">grey82</button><button style='background-color:
#d4d4d4;' OnClick="document.bgColor='#d4d4d4';
document.body.style.background='#d4d4d4'">gray83</button><button style='background-color:
#d4d4d4;' OnClick="document.bgColor='#d4d4d4';
document.body.style.background='#d4d4d4'">grey83</button><button style='background-color:
#d6d6d6;' OnClick="document.bgColor='#d6d6d6';
document.body.style.background='#d6d6d6'">gray84</button><button style='background-color:
#d6d6d6;' OnClick="document.bgColor='#d6d6d6';
document.body.style.background='#d6d6d6'">grey84</button><button style='background-color:
#d9d9d9;' OnClick="document.bgColor='#d9d9d9';
document.body.style.background='#d9d9d9'">gray85</button><button style='background-color:
#d9d9d9;' OnClick="document.bgColor='#d9d9d9';
document.body.style.background='#d9d9d9'">grey85</button><button style='background-color:
#dbdbdb;' OnClick="document.bgColor='#dbdbdb';
document.body.style.background='#dbdbdb'">gray86</button><button style='background-color:
#dbdbdb;' OnClick="document.bgColor='#dbdbdb';
document.body.style.background='#dbdbdb'">grey86</button><button style='background-color:
#dedede;' OnClick="document.bgColor='#dedede';
document.body.style.background='#dedede'">gray87</button><button style='background-color:
#dedede;' OnClick="document.bgColor='#dedede';
document.body.style.background='#dedede'">grey87</button><button style='background-color:
#e0e0e0;' OnClick="document.bgColor='#e0e0e0';
document.body.style.background='#e0e0e0'">gray88</button><button style='background-color:
#e0e0e0;' OnClick="document.bgColor='#e0e0e0';
document.body.style.background='#e0e0e0'">grey88</button><button style='background-color:
#e3e3e3;' OnClick="document.bgColor='#e3e3e3';
document.body.style.background='#e3e3e3'">gray89</button><button style='background-color:
#e3e3e3;' OnClick="document.bgColor='#e3e3e3';
document.body.style.background='#e3e3e3'">grey89</button><button style='background-color:
#e5e5e5;' OnClick="document.bgColor='#e5e5e5';
document.body.style.background='#e5e5e5'">gray90</button><button style='background-color:
#e5e5e5;' OnClick="document.bgColor='#e5e5e5';
document.body.style.background='#e5e5e5'">grey90</button><button style='background-color:
#e8e8e8;' OnClick="document.bgColor='#e8e8e8';
document.body.style.background='#e8e8e8'">gray91</button><button style='background-color:
#e8e8e8;' OnClick="document.bgColor='#e8e8e8';
document.body.style.background='#e8e8e8'">grey91</button><button style='background-color:
#ebebeb;' OnClick="document.bgColor='#ebebeb';
document.body.style.background='#ebebeb'">gray92</button><button style='background-color:
#ebebeb;' OnClick="document.bgColor='#ebebeb';
document.body.style.background='#ebebeb'">grey92</button><button style='background-color:
#ededed;' OnClick="document.bgColor='#ededed';
document.body.style.background='#ededed'">gray93</button><button style='background-color:
#ededed;' OnClick="document.bgColor='#ededed';
document.body.style.background='#ededed'">grey93</button><button style='background-color:
#f0f0f0;' OnClick="document.bgColor='#f0f0f0';
document.body.style.background='#f0f0f0'">gray94</button><button style='background-color:
#f0f0f0;' OnClick="document.bgColor='#f0f0f0';
document.body.style.background='#f0f0f0'">grey94</button><button style='background-color:
#f2f2f2;' OnClick="document.bgColor='#f2f2f2';
document.body.style.background='#f2f2f2'">gray95</button><button style='background-color:
#f2f2f2;' OnClick="document.bgColor='#f2f2f2';
document.body.style.background='#f2f2f2'">grey95</button><button style='background-color:
#f5f5f5;' OnClick="document.bgColor='#f5f5f5';
document.body.style.background='#f5f5f5'">gray96</button><button style='background-color:
#f5f5f5;' OnClick="document.bgColor='#f5f5f5';
document.body.style.background='#f5f5f5'">grey96</button><button style='background-color:
#f7f7f7;' OnClick="document.bgColor='#f7f7f7';
document.body.style.background='#f7f7f7'">gray97</button><button style='background-color:
#f7f7f7;' OnClick="document.bgColor='#f7f7f7';
document.body.style.background='#f7f7f7'">grey97</button><button style='background-color:
#fafafa;' OnClick="document.bgColor='#fafafa';
document.body.style.background='#fafafa'">gray98</button><button style='background-color:
#fafafa;' OnClick="document.bgColor='#fafafa';
document.body.style.background='#fafafa'">grey98</button><button style='background-color:
#fcfcfc;' OnClick="document.bgColor='#fcfcfc';
document.body.style.background='#fcfcfc'">gray99</button><button style='background-color:
#fcfcfc;' OnClick="document.bgColor='#fcfcfc';
document.body.style.background='#fcfcfc'">grey99</button><button style='background-color:
#ffffff;' OnClick="document.bgColor='#ffffff';
document.body.style.background='#ffffff'">gray100</button><button style='background-color:
#ffffff;' OnClick="document.bgColor='#ffffff';
document.body.style.background='#ffffff'">grey100</button><button style='background-color:
#a9a9a9;' OnClick="document.bgColor='#a9a9a9';
document.body.style.background='#a9a9a9'">dark
grey</button><button style='background-color: #a9a9a9;'
OnClick="document.bgColor='#a9a9a9';
document.body.style.background='#a9a9a9'">darkgrey</button><button style='background-color:
#a9a9a9;' OnClick="document.bgColor='#a9a9a9';
document.body.style.background='#a9a9a9'">dark
gray</button><button style='background-color: #a9a9a9;'
OnClick="document.bgColor='#a9a9a9';
document.body.style.background='#a9a9a9'">darkgray</button><button style='background-color:
#00008b;' OnClick="document.bgColor='#00008b';
document.body.style.background='#00008b'">dark
blue</button><button style='background-color: #00008b;'
OnClick="document.bgColor='#00008b';
document.body.style.background='#00008b'">darkblue</button><button style='background-color:
#008b8b;' OnClick="document.bgColor='#008b8b';
document.body.style.background='#008b8b'">dark
cyan</button><button style='background-color: #008b8b;'
OnClick="document.bgColor='#008b8b';
document.body.style.background='#008b8b'">darkcyan</button><button style='background-color:
#8b008b;' OnClick="document.bgColor='#8b008b';
document.body.style.background='#8b008b'">dark
magenta</button><button style='background-color: #8b008b;'
OnClick="document.bgColor='#8b008b';
document.body.style.background='#8b008b'">darkmagenta</button><button style='background-color:
#8b0000;' OnClick="document.bgColor='#8b0000';
document.body.style.background='#8b0000'">dark
red</button><button style='background-color: #8b0000;'
OnClick="document.bgColor='#8b0000';
document.body.style.background='#8b0000'">darkred</button><button style='background-color:
#90ee90;' OnClick="document.bgColor='#90ee90';
document.body.style.background='#90ee90'">light
green</button><button style='background-color: #90ee90;'
OnClick="document.bgColor='#90ee90';
document.body.style.background='#90ee90'">lightgreen</button>
</div>
</div>

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


<div id="org4d76c63" class="figure">
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

<li><span style="color:red;"><b>not yet given</b></span></li>
</ol>


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
<p class="date">Created: 2020-09-25 Fri 07:37</p>
<p class="validation"><a href="https://validator.w3.org/check?uri=referer">Validate</a></p>
</div>
</body>
</html>
