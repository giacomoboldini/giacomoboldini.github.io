To build the CV, use the following command:

```sh
xelatex cv.tex
```

To remove auxiliary files generated during the build process, use the following command:

```sh
rm *.aux *.log *.out *.toc
```

The `awesome-cv.cls` file for the Awesome theme is sourced from
[Awesome-CV](https://github.com/posquit0/Awesome-CV/blob/master/awesome-cv.cls).
My modifications include:
- Adjustments based on [this unmerged pull request](https://github.com/posquit0/Awesome-CV/pull/539) to fix spacing issues (line 749).
<!-- - Reordering to place the ORCID entry before LinkedIn (lines 530-541). -->
- Break line before ORCID entry (line 540).
