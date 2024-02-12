# StAnki

Collection of Anki notes for repetition/summary of Richard McElreath's Statistical Rethinking textbook.

**For now, these are personal notes. I spent little time on checking for errors and may misunderstand parts of the book, which would be transferred into these cards!**


## Rules of Thumb

- Stick to best practices as described [here](https://super-memory.com/articles/20rules.htm), as long as sensibly possible ;)

- Most notes follow the cloze deletion formatting, i.e., surround to-be-asked text with a structure like this:

```
"The University of Göttingen was established in {{c1::1734}}.
"; 
```

    Envelope a note's text with double quotation marks and tell Anki the note is done via a semicolon (` <body text with cloze deletions>";). This way, Anki will respect linebreaks as they occur in the text.

- You can use multiple cloze deletions in one note. Using different numbers, e.g.

```
"The University of {{c2::Göttingen}} was established in {{c1::1734}}.
";
```

    yields two different cards for review, each card eliding text in `{{c1:: ... }}` or `{{c2:: ... }}` structures, respectively.

- You can also stack cloze deletion structures to get both single and multiple parts of the text elided:

```
"The University of {{c1::{{c2::Göttingen}} }} was established in {{c1::1734}}.
";
```

- For maths or ~~nerdy~~ nice symbols, you can include latex environments:

```
"According to Einstein's special relativity, [$] E = m_0 {{c1:: c^2 }} [/$].
";
```

- If you are using curved brackets within a cloze deletion, I consider it best practice to ad whitespaces around each bracket not belonging to the cloze deletion structure. Otherwise, two (e.g., Latex-syntac related) curved brackets without whitespaces could wrongly tell Anki there is a start/end of a cloze deletion:

```
"You can print bold AND cursive text in latex via [$] {{c1::\textbf{ \textit{ } }  [/$]}}
";
```


