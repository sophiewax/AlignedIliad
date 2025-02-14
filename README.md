# Introduction to Aligned Translations with Pope and Butler

<a title="Sebastiano del Piombo
, Public domain, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:El_papa_Clemente_VII,_por_Sebastiano_del_Piombo.jpg"><img width="256" alt="Pope Clement VII" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/El_papa_Clemente_VII%2C_por_Sebastiano_del_Piombo.jpg/256px-El_papa_Clemente_VII%2C_por_Sebastiano_del_Piombo.jpg?20190609153516"></a>

<a title="National Portrait Gallery
, Public domain, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:Samuel_Butler_by_Charles_Gogin.jpg"><img width="256" alt="Samuel Butler by Charles Gogin" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/Samuel_Butler_by_Charles_Gogin.jpg/256px-Samuel_Butler_by_Charles_Gogin.jpg?20090329130233"></a>

## To which version of the _Iliad_ should I align Pope's translation?

Use the perseus-eng4 (Butler) version found here: https://github.com/PerseusDL/canonical-greekLit/blob/master/data/tlg0012/tlg001/tlg0012.tlg001.perseus-eng4.xml.

## How to proceed

1. Fork this repository.

2. Create a file called `tlg0012.tlg001.perseus-eng4.pope-alignments:1.[START]-1.[END].py`, where `[START]` and `[END]` stand for the starting and ending lines in the Butler translation. That is, `[START]` will correspond to the `n` number in one `<milestone>` tag, and `[END]` will correspond to `n - 1` in the next `<milestone>`.

I have created tlg0012.tlg001.perseus-eng4.pope-alignments:1.1-1.4.py as an example.

3. In that file, create a dictionary called `alignments`. At the first level, add the book and line citations (your start and end numbers). Then, create a sub-dictionary with keys `"butler"` and `"pope"`, and add the corresponding text for each. Your result should look something like the example:

```python
alignments = {
    "1.90–1.94": {
        "butler": """no, not though you name Agamemnon himself, who
                     is by far the foremost of the Achaeans." Thereon the seer [<term xml:lang="grc"
                        >mantis</term>] spoke boldly. "The god," he said, "is angry neither about
                     vow nor hecatomb, but for his priest's sake, whom Agamemnon has dishonored,""",
        "pope": """Whence rose these woes, and whence this dire debate?
                     From Jove and Thetis sprang the stern decree,
                     That urged Achilles’ wrath and doomed to fate
                     The chiefs untimely, in the martial fray.
                     For priest despised, and ransom cast away."""
    }
}
```

4. Commit your results and open a pull request against this repository.
