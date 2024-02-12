# StAnki

Collection of Anki notes for repetition/summary of Richard McElreath's Statistical Rethinking textbook.

**For now, these are personal notes. I spent little time on checking for errors and may misunderstand parts of the book, which would be transferred into these cards!**

## Usage

I recommend setting up a 'Import Test Deck' for importing to your Anki, so you can 1.) Always import into this deck, 2.) Browse through this deck to see if everything looks good, 3.) Edit potential errors/typos, 4.) Finally, select all cards and move them into their destination deck.

This way, if something in the import is wrong, you will not have to look for the cards in a already filled deck.


1. Install the excellent [Anki](https://apps.ankiweb.net/) flashcard program 
2. Download files of choice from this repository
    1. from `stable` directories for using ready-made files 
    2. From `testing` directories if you want to proofread untested files 
3. Open Anki, press `Ctrl`+`Shift`+`P` (or navigate to & click `File`->`Import`)
4. Find the downloaded file
5. Adapt the import settings to fit the file format.
    (Usually, all there is to it is changing `Field separator` from `Pipe` to `Semicolon`.)
    1. Double-check that you import the notes into the correct deck
6. Import!


## Contributing: Rules of Thumb

- Stick to best practices as described [here](https://super-memory.com/articles/20rules.htm), as long as sensibly possible ;)

- Most notes follow the cloze deletion formatting, i.e., surround to-be-asked text with a structure like this:

```
"The University of Göttingen was established in {{c1::1734}}.
"; 
```

- As above, envelope a note's text with double quotation marks and tell Anki the note is done via a semicolon (` <body text with cloze deletions> `;). This way, Anki will respect line breaks as they occur in the text.

- You can use multiple cloze deletions in one note. Using different numbers yields two different cards for review, each card eliding text in `{{c1:: ... }}` or `{{c2:: ... }}` structures, respectively.

```
"The University of {{c2::Göttingen}} was established in {{c1::1734}}.
";
```

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

- If you are using curved brackets within a cloze deletion, I consider it best practice to add blank spaces around each bracket not belonging to the cloze deletion structure. Otherwise, two (e.g., LaTeX-syntax related) curved brackets without blank spaces could wrongly tell Anki there is a start/end of a cloze deletion:

```
"You can print bold AND cursive text in latex via [$] {{c1::\textbf{ \textit{ } }  [/$]}}
";
```

