---
layout: default
title: 'MIA Lab: Report writing with LaTeX'
---

# Report writing with LaTeX

**LaTeX** (pronounced "LAY-tek" or "LAH-tek") is a tool for creating professional-looking documents. Unlike programs like Microsoft Word or LibreOffice Writer, where you type and style text directly on the page, LaTeX works differently. You write your document as a plain text file with special commands to format it. Read more about typesetting here: [Learn LaTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes).

For a LaTeX cheat-sheet, including most commonly used commands, see [latexsheet.pdf](/files/latexsheet.pdf).

## Templates

There are templates available for academic conference and journal papers, many of which are available on the Overleaf templates page. The final report template we recommend is the [IEEE conference template on Overleaf](https://www.overleaf.com/latex/templates/ieee-conference-template/grfzhhncsfqn).

If you prefer to use a local installation, here is a [.zip file containing the IEEE 4 page conference paper template](/files/ieee-conference-template.zip) for the report. Please do this at your own risk, we highly recommend using Overleaf otherwise.

## Tips

Quotation marks are a bit tricky: for an opening quote use two backticks (``` `` ```) rather than two apostrophes (`''`).

`\` is a special "escape" character (bonus points if you are familiar with C strings for the reference), and many symbols you would like to include in the text will depend on proper usage of the backslash.

The `$` sign is used to format mathematical content, and can be used in-text too. Please consider using these while including any numbers, equations, or simple formulae which are not within the equation space.

Please also consider using the `\centering` command while including graphics and tables, so they are properly justified.

Please also consider using the `\cite`, `\label` and `\ref` commands appropriately while citing papers or resources from the references, and also to other parts of your report (refer to Section `\ref{section-one}`, where "section-one" is properly labeled, for example).

If you have tables in the report, please consider using [this table generator](https://www.tablesgenerator.com/) instead of hand-rolling one.

We require that anything you use from other papers/resources online is appropriately cited. We recommend using a citation manager like Mendeley, which works very well [with Overleaf](https://www.overleaf.com/learn/how-to/How_to_link_your_Overleaf_account_to_Mendeley_and_Zotero).

This is the easiest (if you find an easier way, let us know!) way to work with references as a group as well. Alternatively, [bibtex](https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex) is the traditional way, which works quite well when [exported from Google Scholar](https://digitalmeasures.oregonstate.edu/training/export-bibtex-google-scholar).
