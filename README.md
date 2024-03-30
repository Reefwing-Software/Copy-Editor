
Copy Editor Help
================

Contents
--------

*   [1\. Overview](#section1)

    *   [1.1. Supported File Types](#file-types)

*   [2\. Control/Edit Window](#section2)
    *   [2.1. The Control Tab](#control-tab)
    *   [2.2. The Edit Tab](#edit-tab)
*   [3\. Display/Render Window](#section3)
*   [4\. Status Bar](#section4)
    *   [4.1 File Name](#file-name)
    *   [4.2. Word Count](#word-count)
    *   [4.3 Readability](#readability)
    *   [4.4 Average Sentence Length](#sentence-length)
    *   [4.5 Passive Score](#passive-score)
    *   [4.6 AI Phrase Percentage](#ai-percentage)
    *   [4.7 File Edited Flag](#edited)
*   [5\. Menu/Toolbar Commands](#section5)
    *   [5.1 Word Wrap](#word-wrap)
    *   [5.2 AI Phrase Detection](#ai-phrase-detection)
    *   [5.3 Adverbs and Adjectives (Adv/Adj)](#adjectives)
    *   [5.4 Long Sentences](#long-sentences)
    *   [5.5 Passive Sentences](#passive-sentences)
    *   [5.6 Spell Check](#spell-check)
    *   [5.7 Lexical Richness and Word Frequency](#word-frequency)
    *   [5.8 Statistics](#statistics)
    *   [5.9 Settings](#settings)
*   [Appendix A - NLTK Python Library](#appendixA)
*   [Appendix B - Grammatical Errors Best Detected by AI](#appendixB)
*   [Appendix C - The Vader Sentiment Python Library](#appendixC)

1\. Overview
------------

Copy Editor is a tool designed to enhance the writing process by providing real-time text analysis and editing suggestions. This app leverages advanced natural language processing techniques to offer a wide range of features, including grammar and spelling corrections, style improvements, and readability assessments. Key functionalities of the Copy Editor app include:

*   **AI Phrase Detection:** Identifies and highlights phrases commonly overused in AI-generated content, helping users to refine their writing to ensure originality.
*   **Grammar and Spelling Checker:** Utilizes an integrated spell checker to identify and suggest corrections for misspelled words or grammatical errors, improving the overall quality of the text.
*   **Readability Score:** Calculates and presents a readability score based on sentence length and complexity, offering insights into how accessible the text is to its intended audience.
*   **Passive Voice Detection:** Detects sentences written in passive voice and suggests active voice alternatives to make the writing more direct and engaging.
*   **Long Sentence Highlighting:** Highlights long sentences that could potentially confuse readers, suggesting breaks or simplifications to enhance clarity.

The app is designed with a user-friendly interface, making it accessible to writers of all levels, from professionals to students. It aims to not only correct but also educate users on better writing practices, thus improving their writing skills over time. The integration of BeeWare's Toga as a GUI framework allows the app to run on multiple platforms, providing a seamless experience across different operating systems.

This tool stands out by offering a comprehensive suite of editing tools in one package, emphasizing both the technical and stylistic aspects of writing. It's an invaluable resource for anyone looking to polish their text to perfection.

### 1.1 Supported File Types

Copy Editor supports a variety of file types, catering to different needs and use cases for our users. Below is a comprehensive guide to the file types that can be opened, viewed, and edited within Copy Editor, along with specifics on how certain file types are handled and limitations regarding saving files.

#### Text Files (.txt)

Text files are the simplest form of document that can be edited in Copy Editor. These files contain plain text with no formatting or special characters outside of basic ASCII. Ideal for notes, programming code, or any content where formatting is not a concern.

#### Markdown Files (.md)

Markdown files are used for writing content in Markdown language, which allows for simple formatting using plain text symbols. This format is widely used for README files, documentation, and content writing that requires basic formatting like headers, lists, bold, and italics.

#### HTML Files (.html, .htm)

HTML files are structured documents used to create web pages. Copy Editor supports opening and editing HTML files, allowing users to work directly on web content. The editor retains the HTML structure and formatting, enabling users to edit web pages or any HTML-based content.

#### Word Documents (.docx)

The `.docx` file format is a Microsoft Word document format that uses XML and ZIP compression to organize and store the document's content and formatting. Introduced with Microsoft Word 2007, it represents a shift from the proprietary binary formats (`.doc`) used in earlier versions to an open standard known as Office Open XML (OOXML).

Copy Editor supports opening and viewing `.docx` files through the `docx2python` library. When a `.docx` file is opened, the editor displays the content rendered as HTML in the render window, retaining font size, color, bold, italics, and underscore formatting. It's important to note that while Copy Editor can display `.docx` content with some formatting preserved, it cannot save files back into the `.docx` format.

#### Log Files (.log)

Log files, with the extension `.log`, are treated similarly to plain text files. These are typically used by applications to record events, errors, or other operational information. Copy Editor log files are located in the apps `logs` sub-directory. In Copy Editor, `.log` files can be opened and edited as plain text, making it convenient for users to view and modify log output.

#### Limitations on Saving Files

While Copy Editor supports viewing and editing a range of file types, it has limitations on how files can be saved:

*   **Text and Markdown**: Users can save their work as plain text (`.txt`) or Markdown (`.md`), preserving the content and basic formatting (for Markdown) as entered in the editor.
*   **HTML**: Content can also be saved as HTML files (`.html`), which is ideal for web page content or other HTML-formatted documents.
*   **No Support for Saving as `.docx`**: Currently, Copy Editor does not support saving files in the `.docx` format. Users working on `.docx` files will need to save their edits as text, Markdown, or HTML files.

2\. Control/Edit Window
-----------------------

The **Control/Edit Window** is located on the left side of the Copy Editor app. It includes two tabs: the **Control Tab** and the **Edit Tab**. At launch the **Control Tab** will be showing.

### 2.1 The Control Tab

The **Control Tab** assists with the management of grammar and spelling issues detected in the loaded document. Immediately below the **Control/Edit Tab** is the **Issue Selection** control.

The **Issue Selection** control allows you to target specific spelling or grammar issues (e.g., Spelling, Long Sentences, Passive Sentences, Possible AI Phrases, Adverbs, and Adjectives). Detected issues can be found in the **Issue List**, a table which has four headings (Type, Text, Options, and ID).

If you select **All**, a summary of the issue types are provided (e.g., `Total Issues: 27 - [SP: 8, LS: 0, PS: 1, AI: 0, ADV: 6, ADJ: 18, IGN: 6]`). The summary codes are:

*   **SP** - Spelling
*   **LS** - Long Sentences
*   **PS** - Passive Sentences
*   **AI** - Possible AI Phrases
*   **ADV** - Adverbs
*   **ADJ** - Adjectives
*   **IGN** - Ignored

Selecting an issue will expand the issue tree branch of that particular issue, if there are any. Types with one or more issues will have a ">" before the name (e.g., > Spelling). Left clicking on the ">" will toggle revealing all issues associated with that type.

Issues can be selected by left clicking on them in the **Issue List.** On a Mac, press ⌘ or Shift, then click to select multiple items. For Windows and Linux, press Ctrl or Shift, then click to select multiple items.

Below the **Issue List** are four buttons:

*   **Add:** This button is only enabled if you have selected one or more Spelling issues. Clicking this button will add the selected unknown words to the spelling dictionary. These words will then no longer be picked up by the Spell Checker. These additions are valid for all future spell checks on all documents.
*   **Correct:** This button is only enabled if you have selected one Spelling issue. Clicking on the button will open up the Word Correction dialog, which will attempt to suggest replacement words. You can select one of these in the table or just type the word directly in the `Replacement` box. Then click on `Use Word` to replace it where ever found in the document. If you want the replacement to ignore case, tick the check box in the top right corner.
*   **Clear Ignored:** Will remove the attached metadata for ignored issues for this document. It will also reset the state of these issues in the Issue Table.
*   **Ignore:** This button will tag the selected issues as _ignored_, and these wont be highlighted in the Render window. Unlike **Add**, this button is document specific. The ignored issues are saved as metadata for the file and wont apply to other documents.

### 2.2 The Edit Tab

When you open a file or type text into the Edit tab, the following analysis will run in real-time:

*   AI Phrase Detection
*   Adverb and Adjective Detection
*   Long Sentence Detection
*   Passive Sentence Detection

The spell checker is the only Analysis function that needs to be run manually.

Any issues which are picked up will be added to the Issue List in the Control Tab.

3\. Display/Render Window
-------------------------

The Render or right-hand Window in Copy Editor, provides a real-time display for content using markdown or HTML tags, allowing for rich text formatting. Plain text remains unchanged.

4\. Status Bar
--------------

### 4.1 File Name

The File Name indicator in the status bar provides immediate feedback on the current document's status. Initially empty for new sessions, it updates to display the name of the currently opened file. While the full file path is stored in the Recent File list for quick access, the status bar only shows the file name and extension. Actions such as opening a new file or saving changes trigger updates to this indicator.

If **File** -> **New File** is selected in the menu, the Edit and Render screens will be cleared and "File: New File" is displayed in the status bar. When you save a file, the status bar will be updated with the new saved file name.

### 4.2. Word Count

The word count feature offers a quantitative measure of document length. However, achieving an accurate word count can be challenging due to variations in what constitutes a "word" across languages and formatting issues. For example, handling hyphenated compounds, numbers, abbreviations, and other non-standard word forms, complicate the task.

For these reasons, word counts should be considered indicative.

### 4.3 Readability

Understanding readability and how it affects your writing is crucial. It determines how easily readers can comprehend your text. The key to readability is using simple, clear language and a logical structure.

### What is the Flesch Reading Ease Score?

The Flesch reading ease test measures the readability of a text. It uses two variables to determine the readability score:

*   The average length of your sentences (measured by the number of words)
*   The average number of syllables per word

Then, it provides you with a score between 0 and 100. A score of 100 means your copy is very easy to read. And, a score of 0 means your text is very difficult to read. You can see the exact interpretation of all the scores on the scale in the table below.

The readability parser that we use requires a minimum of 100 words to produce a readability score.

#### Score

- **90-100**: Very easy to read, easily understood by an average 11-year-old student

- **80-90**: Easy to read

- **70-80**: Fairly easy to read

- **60-70**: Easily understood by 13- to 15-year-old students

- **50-60**: Fairly difficult to read

- **30-50**: Difficult to read, best understood by college graduates

- **0-30**: Very difficult to read, best understood by university graduates

### 4.4 Average Sentence Length

Average sentence length refers to the average number of words in the sentences of a given text. It is calculated by dividing the total number of words by the total number of sentences. For example, if a text has 100 words distributed over 10 sentences, the average sentence length is 10 words per sentence.

[Research](https://prsay.prsa.org/2009/01/14/how-to-make-your-copy-more-readable-make-sentences-shorter/) shows that when average sentence length is 14 words, readers understand more than 90% of what they’re reading. At 43 words, comprehension drops to less than 10%.

[Studies](https://strainindex.wordpress.com/2012/04/30/longer-the-sentence-greater-the-strain/) also show that sentences of 11 words are considered easy to read, while those of 21 words are fairly difficult. At 25 words, sentences become difficult, and 29 words or longer, very difficult.

The colour coding in the status bar is based on the 11, 21, 25 and 29, guidelines for average sentence length.

Average sentence length is an important aspect of writing for several reasons:

1.  Readability and Comprehension: Sentence length significantly affects the readability of a text. Longer sentences are often more complex and can be harder to follow, potentially leading to confusion or misunderstanding. Shorter sentences, on the other hand, tend to be clearer and more direct. Balancing sentence lengths can help ensure that a text is both engaging and understandable to the reader.
2.  Audience Appropriateness: Different audiences have different reading preferences and capabilities. For example, texts for children or for readers for whom English is a second language typically benefit from shorter, simpler sentences. Academic or professional documents, however, may use longer, more complex sentences to convey detailed information or nuanced arguments.
3.  Pacing and Rhythm: Variation in sentence length can affect the pacing and rhythm of a text. Short sentences can quicken the pace and add urgency or emphasis, while longer sentences can slow the pace and add descriptive detail or complexity. Good writers often vary sentence length to control the flow of the narrative or argument and to keep the reader's interest.
4.  Tone and Style: Sentence length is an element of a writer's style. Different genres and types of writing tend to favor different average sentence lengths. For instance, fiction might have more varied sentence lengths to create a more vivid and engaging narrative, while non-fiction might lean towards a more uniform sentence length for clarity and consistency.
5.  Writing Quality: Overuse of long sentences can make text seem verbose or convoluted, while overuse of short sentences can make it choppy or simplistic. A balanced approach to sentence length can enhance the overall quality of writing.

### 4.5 Passive Score

To calculate a "passive score" for a block of text we analyze the text to determine the frequency of passive voice usage. Passive voice occurs when the subject of a sentence is acted upon by the verb, rather than performing the action. For instance, "The ball was thrown by John" is in passive voice, while "John threw the ball" is in active voice.

The passive score calculated is a rough measure of how frequently passive voice is used in a given block of text.

The passive score is expressed as a percentage. It represents the proportion of sentences in the text that are identified as being in the passive voice.

Passive sentences are identified by a past participle (tagged as 'VBN') following a form of 'to be' ('VBZ' for present tense, 'VBD' for past tense). This is a heuristic and may not catch all passive constructions, especially in complex sentences.

A higher percentage (closer to 100%) suggests that a large portion of the sentences are written in passive voice. This might indicate a writing style that is more formal, bureaucratic, or academic, where passive constructions are often more prevalent.

A lower percentage (closer to 0%) indicates that fewer sentences are in passive voice, suggesting a writing style that relies more on active voice. Active voice is generally considered more direct and easier to read, and is often preferred in many writing contexts.

Setting a target percentage for passive voice usage in a novel isn't straightforward, as the ideal amount can vary greatly depending on the style, genre, and narrative technique. Unlike more formal writing like academic or scientific texts where passive voice might be more prevalent, novels typically benefit from a more active voice. The active voice tends to make the narrative more dynamic, direct, and engaging for readers.

However, this doesn't mean that passive voice should be entirely avoided. It can be effectively used in certain contexts, such as to create a particular tone, emphasize certain elements of a scene, or in dialogue that reflects how people naturally speak.

In general terms, a lower percentage of passive voice is often recommended for novels. As a rough guideline, you might aim for a passive voice usage of less than 20%, but this is very flexible. The key is to use passive voice purposefully and sparingly. More important than strictly adhering to a percentage is ensuring that each sentence serves your narrative effectively, whether it's in active or passive voice.

Ultimately, the "right" amount of passive voice depends on your unique voice as an author and the specific needs of your story. It's often more beneficial to focus on crafting clear, compelling prose and strong, vivid scenes rather than aiming for a specific passive voice percentage. Regular feedback from editors or beta readers can also provide valuable insights into whether the balance of active and passive voice in your novel is effective.

See also the section on [Passive Sentences.](#passive-sentences)

### 4.6 AI Phrase Percentage

There are two parts to AI Phrase Detection. The detector runs automatically when you load or edit a file. If any AI phrases are detected, these will be added to AI Phrases in the Control tab.

If you click on AI Detect in the menu or toolbar, those phrases will then be highlighted in the render window.

This tool is designed to distinguish AI-generated content from human-written text. This feature compares text for patterns and phrases that are commonly overused by generative AI models. By comparing the content against our database of phrases, the software can flag sections that exhibit a high likelihood of being AI-generated.

The list of phrases is stored in copyeditor/data/ai\_phrases.txt. Feel free to modify this and include additional phrases.

See also the section on [AI Phrase Detection](#ai-phrase-detection) in Menu/Tollbar Commands.

### 4.7 File Edited Flag

The file edited flag in the status bar serves as a visual indicator of document modification. Initially black, the flag turns red upon any text change within the Edit tab, signaling unsaved edits. This feature ensures users are aware of unsaved changes, prompting a save confirmation when attempting to close the app with a red flag, thus safeguarding against accidental data loss.

5\. Menu/Toolbar Commands
-------------------------

We have provided information on items in the menu which are different or unique to the Copy Editor app. The remaining items (e.g., **File** -> **Open**) should operate as you expect.

When you open a file or type text into the Edit tab, the following analysis will run in real-time:

*   AI Phrase Detection
*   Adverb and Adjective Detection
*   Long Sentence Detection
*   Passive Sentence Detection

The spell checker needs to be run manually, every time you want to check the spelling of your text.

Clicking on the any of the Analysis items (**AI Detect, Adv/Adj, Long, Passive,** or **Spell Check**), will highlight those issues in the Render Window.

The Menu Tool items ([Frequency](#word-frequency) and [Statistics](#statistics)), will bring up a separate window containing the analysis described below.

### 5.1 Word Wrap

Word wrap is a feature in Copy Editor that automatically moves words that do not fit on the current line to the start of the next line. This ensures that the text fits within the defined width of the document page, without the need for the user to manually insert line breaks. Word wrap improves readability and maintains a clean, organized appearance of text by preventing horizontal scrolling and keeping all content visible within the viewport or page margins.

The **Word Wrap** toggle command in the toolbar and View menu, only applies to text files. Other supported file types like Markdown and HTML have styling tags which already control this function.

### 5.2 AI Phrase Detection

There are two parts to AI Phrase Detection. The detector runs automatically when you load or edit a file. If any AI phrases are detected, these will be added to AI Phrases in the Control tab.

If you click on **AI Detect** in the menu or toolbar, those phrases will then be highlighted in the render window.

This tool is designed to distinguish AI-generated content from human-written text. This feature compares text for patterns and phrases that are commonly overused by generative AI models. By comparing the content against our database of phrases, the software can flag sections that exhibit a high likelihood of being AI-generated.

The list of phrases is stored in copyeditor/data/ai\_phrases.txt. Feel free to modify this and include additional phrases. The phrase list was compiled from our own research and the following sources:

*   [Which Phrases are the Most “ChatGPT” of All?](https://medium.com/@jordan_gibbs/which-phrases-are-the-most-chatgpt-of-all-b0911e3faf6b)
*   [These ChatGPT Words Get On My Nerves.](https://medium.com/illumination/these-chatgpt-words-get-on-my-nerves-ae8594367bf4)
*   [ChatGPT's Favorite Phrases.](https://sapling.ai/devblog/chatgpt-phrases/)

### 5.3 Adverbs and Adjectives (Adv/Adj)

An **adverb** is a part of speech that modifies verbs, adjectives, or other adverbs, typically expressing manner, place, time, frequency, degree, level of certainty, etc., and usually ends in "-ly". For example, in the sentence "She sings beautifully," "beautifully" is an adverb modifying the verb "sings" to describe how she sings.

An **adjective** is a word used to describe or modify a noun or pronoun, giving more information about the object's size, shape, age, color, etc. For example, in "The tall building," "tall" is an adjective describing the noun "building."

#### Why Adverbs and Adjectives Can Be Problematic in Writing

**Overuse:** Reliance on adverbs and adjectives can lead to overuse, making writing appear cluttered or overly elaborate. It's often more effective to choose stronger, more precise verbs or nouns instead of propping up weaker ones with adverbs and adjectives. For instance, saying _"she sprinted"_ instead of _"she ran quickly"_ makes the sentence stronger and more direct.

**Vagueness:** Adjectives and adverbs can sometimes be vague or subjective without adding significant information. Words like _"very," "really,"_ or _"beautiful"_ can be overused without truly enhancing the reader's understanding of the subject.

**Weakening the Impact:** Especially with adverbs, their use can weaken the impact of a verb by diluting its force. Strong writing often suggests choosing a verb that doesn't need modification.

**Redundancy:** Sometimes adverbs and adjectives state the obvious, leading to redundancy. For example, in _"whisper quietly,"_ the adverb _"quietly"_ is redundant since whispering is inherently quiet.

In moderation, adverbs and adjectives enrich language, adding detail and nuance. However, when overused or used inappropriately, they can detract from the clarity and strength of writing. Effective writers often review their use of adverbs and adjectives to ensure each word contributes meaningfully to their narrative or argument, considering if stronger nouns or verbs could serve better.

### 5.4 Long Sentences

Long sentences can pose numerous challenges for readers and overall clarity. They can be difficult to parse, leading to comprehension issues and reduced emphasis on key points. Additionally, they can create a monotonous reading experience, hinder scannability, and feel overly formal in casual contexts. These problems become particularly concerning for audiences with reading difficulties or cultural preferences for concision. While long sentences may be suitable in certain formal settings or for expressing complex ideas, it's crucial to prioritize readability and engagement by using varied sentence lengths and avoiding excessive complexity whenever possible. This ensures your writing effectively delivers its message and connects with your target audience.

The Long Sentences (**Long**) command in the Analysis menu and toolbar will highlight sentences with over 21 words. Depending on context these may be worth reviewing and are added to the issues list in the Control tab.

Refer also to the description about [average sentence length.](#section3)

### 5.5 Passive Sentences

The Passive Sentences (**Passive**) command in the Analysis menu and toolbar will highlight sentences with passive voice. Depending on context these may be worth reviewing and are added to the issues list in the Control tab.

Active and passive voice represent two distinct ways of structuring sentences, each impacting clarity and reader engagement. Active sentences place the subject at the forefront, performing the action directly. This results in a clear understanding of who or what is doing what, fostering a more direct and impactful message. In contrast, passive sentences downplay the doer, shifting the focus to the action itself. This can lead to ambiguity, as the true actor becomes obscured, and weaken the overall impact. When it comes to copy editing, prioritizing active voice is crucial for ensuring clarity and engaging the reader.

While passive voice can sometimes be appropriate, it often creates obstacles to clear and engaging content. Passive sentences tend to obscure the doer of the action, making it unclear who or what is responsible. This can lead to ambiguity and reduce the impact of your writing. Additionally, passive sentences often require more words than active sentences, hindering readability and potentially diluting the main message. Opting for active voice generally fosters stronger writing by putting the focus on the subject performing the action and ensuring a more direct and concise delivery of your ideas. Remember, prioritizing clarity and active voice helps your writing communicate effectively and resonate with your readers.

An example to illustrate the difference between active and passive voice:

*   **Active sentence:** The dog chased the ball across the park. (Subject "dog" actively performs the action "chased.")
*   **Passive sentence:** The ball was chased across the park by the dog. (Subject "ball" is passive, focus shifts to the action "chased," and the doer "dog" appears later.)

### 5.6 Spell Check

**Spell Check** is powered by the Pure Python spellchecker library. It identifies and highlights unrecognized words in red within the render window. When activated from the menu or toolbar, it also populates the Spelling Issues table under the Control tab with these highlighted words, aiding users in quick identification and correction of potential spelling errors in their text.

The Python library uses uses a Levenshtein Distance algorithm to find permutations within an edit distance of 2 from the original word. It then compares all permutations (insertions, deletions, replacements, and transpositions) to known words in a word frequency list. Those words that are found more often in the frequency list are more likely the correct results.

The Levenshtein Distance algorithm measures the difference between two sequences by counting the minimum number of operations required to change one sequence into the other. In the context of spell checking, it helps identify and suggest corrections for misspelled words by finding words with the smallest Levenshtein Distance to the misspelled one, indicating they are likely candidates for what was intended, making it a powerful tool for improving text accuracy.

### 5.7 Lexical Richness and Word Frequency

Clicking on the **Frequency** Analysis Menu or Toolbar item will bring up the lexical analysis and word frequency window.

Lexical Richness measures the diversity and complexity of vocabulary in text, providing insights into vocabulary usage and writing style. It's useful for language learning, plagiarism detection, and text analysis.

#### Purpose of Analysis

*   Quantify lexical richness in the loaded text.
*   Offer insights into the writer's vocabulary usage and writing style.
*   Can be used for language learning, and text analysis.

#### Indicators displayed in the Word Frequency Window

*   **Unique Word Count (UWC):** The number of distinct words used in the text. Higher UWC generally indicates broader vocabulary usage. However, it's crucial to consider text length.
*   **Type-Token Ratio (TTR):** UWC divided by the total number of words (tokens). A TTR closer to 1 suggests greater vocabulary diversity, while lower values signify more frequent repetition of a few words.
*   **Corrected Type-Token Ratio (CTTR):** Adjusted TTR based on text length to minimize bias towards shorter texts. Similar to TTR, but considered more reliable across varying text lengths. Typically, CTTR values range from 0 to 1, with higher values indicating greater vocabulary diversity. However, values exceeding 1 might suggest unusual word choices or technical jargon depending on the context.
*   **Measure of Textual Lexical Diversity (MTLD):** A robust metric considering word frequencies and accounting for text length. Typical MTLD ranges vary depending on the source, but generally fall between 0 and 100, with higher values indicating greater diversity. Again, the interpretation depends on the specific context and genre.

#### The Word Frequency Table

The Word Frequency Table organizes and displays all words from a loaded document, sorted by their frequency of use. This feature allows users to easily see which words are used most often, aiding in identifying overused words or assessing vocabulary diversity within the document.

There's no single magic number for identifying overused words. It depends on several factors such as text length, genre, word function, and writing style.

##### Text length and type

*   Shorter texts (<500 words) are more sensitive to word repetition compared to longer ones (e.g., novels).
*   Technical writing is more tolerant of repeated terminology than creative writing.

##### Word function and part of speech

*   Function words (articles, prepositions, pronouns) naturally recur more frequently than content words (nouns, verbs, adjectives).
*   Repetition of content words is more noticeable and potentially problematic.

##### Specific word and context

*   Some words like "the" or "a" are expected to be used frequently.
*   Overuse of unique or unusual words can stand out even at lower frequencies.

##### Writing style and purpose

*   Deliberate repetition for emphasis or rhythm can be effective in certain contexts.
*   Repetitive language in formal writing often indicates lack of variation.

##### General guidelines for word frequency

*   For short texts: Words exceeding **5-7%** frequency might raise concerns.
*   For longer texts: **3-5%** could be a starting point, with adjustments based on the factors mentioned above.
*   Focus on qualitative judgment: Don't rely solely on percentages. Consider if the repetition sounds awkward, detracts from clarity, or limits vocabulary usage.

### 5.8 Statistics

The **Statistics** window provides insights into the document's textual characteristics. It displays the file name for reference and offers a detailed analysis including word and sentence counts, the average length of sentences, and the frequency of long and passive sentences, with percentages for easier interpretation. Additionally, it identifies potential AI-generated sentences and their proportion, alongside counts of adverbs and adjectives. The Flesch reading ease score is presented for readability assessment. Graphical representations include sentence length distribution and sentiment analysis, offering visual insights into the text's structure and emotional tone.

Sentiment analysis evaluates the emotional tone behind a series of words, used to gain an understanding of the attitudes, opinions, and emotions expressed within the text. The core scores include positive, negative, and neutral, indicating the sentiment's direction. The compound score combines these into a single metric that ranges from -1 (extremely negative) to +1 (extremely positive), providing a holistic view of the sentiment's overall positivity or negativity.

### 5.9 Settings

The "Settings" menu item, provides users with the flexibility to customize their experience with the app according to their preferences. Within the "Settings" panel, users have access to two configurable options, both managed through checkboxes for easy toggling.

The first option allows users to enable or disable word wrap on the render screen. By default, word wrap is activated, ensuring that text automatically adjusts to fit within the window's width, eliminating the need for horizontal scrolling to read long lines. This feature enhances readability and provides a smoother user experience.

The second option available in the "Settings" menu pertains to the behavior of the word replacement function, specifically regarding case sensitivity. The default setting is to consider case when replacing words, meaning that replacements must match the case of the original word exactly for the replacement to occur. Users who prefer a more flexible approach can disable this option, allowing word replacements to ignore case differences.

Appendix A - NLTK Python Library
--------------------------------

The Natural Language Toolkit (NLTK) is a powerful Python library used for working with human language data (natural language processing or NLP). It provides interfaces to over 50 corpora and lexical resources such as WordNet, along with a suite of text processing libraries for classification, tokenization, stemming, tagging, parsing, and semantic reasoning.

We use the NLTK library to calculate our readability and passive scores. These scores will be consistent every time you load a body of text.

The program also allows you to use ChatGPT to provide similar analysis, but due to its generative nature, you wont always get the same result.

Key features and uses of NLTK include:

*   Tokenization: Splitting text into words and sentences.
*   Part-of-Speech Tagging: Assigning parts of speech to each word, like noun, verb, adjective, etc.
*   Named Entity Recognition (NER): Identifying names of people, places, organizations, etc., in text.
*   Syntax Parsing: Analyzing sentence structure.
*   Sentiment Analysis: Determining the emotional tone behind a body of text.
*   Stemming and Lemmatization: Reducing words to their base or root form.
*   Corpora Access: NLTK provides access to many text corpora and lexical resources.
*   Text Classification: Assigning categories or labels to text.

NLTK is a comprehensive library for natural language processing, providing tools for a wide array of textual analysis and language processing tasks.

Appendix B - Grammatical Errors Best Detected by AI
---------------------------------------------------

**Misplaced Modifiers:** These occur when a word or phrase intended to describe a noun or verb is placed too far away from it in the sentence, leading to ambiguity or a change in meaning. For example, "Flying over the ocean, the city looked beautiful" improperly suggests that the city is flying. Detecting them automatically is challenging because it requires understanding the intended meaning of the sentence.

**Verb Tense Errors:** These errors happen when the verb tense used in a sentence does not accurately reflect the time frame of the action or when inconsistent tenses disrupt the sentence's coherence. For instance, "She eats breakfast and then went to work" mixes past and present tenses incorrectly. Detecting incorrect verb tense usage involves understanding the sequence of events in a text and ensuring the verb tenses are consistent with that sequence. This is also a complex task requiring contextual understanding.

**Subject-Verb Agreement Errors:** These occur when the verb does not grammatically agree in number with its subject, leading to sentences that sound incorrect. An example is "The list of items are on the desk," where "list" is singular but is incorrectly matched with the plural verb "are."

### Why LLMs are Better at Analyzing These Errors

**Contextual Understanding:** LLMs are trained on vast amounts of text, enabling them to understand context and nuance in language much better than rule-based systems. This contextual understanding allows LLMs to more accurately identify when a modifier is misplaced or a verb tense is incorrect based on the surrounding text.

**Advanced Pattern Recognition:** LLMs use deep learning to recognize complex patterns in language that can indicate grammatical errors. This capability goes beyond simple part-of-speech tagging and allows for more nuanced detection of errors.

**Error Correction:** Beyond identifying errors, LLMs can suggest corrections that are grammatically sound and stylistically appropriate within the context of the sentence, something that rule-based systems struggle with without human-like understanding of language.

**Flexibility and Adaptability:** LLMs can handle variations in language use, including idiomatic expressions, slang, and evolving language norms, making them more adaptable to different writing styles and genres.

**Integrated Knowledge:** LLMs not only analyze text based on grammatical rules but also incorporate real-world knowledge and common usage patterns into their analysis, improving the accuracy of error detection.

While libraries like NLTK are powerful tools for specific NLP tasks and offer great educational value, the depth and breadth of understanding provided by LLMs make them more suited for comprehensive language analysis, including the complex task of identifying and correcting grammatical errors in natural language text.

Appendix C - The Vader Sentiment Python Library
-----------------------------------------------

The `vaderSentiment` library is a Python package designed for sentiment analysis. It utilizes the VADER (Valence Aware Dictionary and sEntiment Reasoner) model, which excels at identifying sentiments expressed through idioms, slang, emoticons, and colloquial language.

### VADER:

VADER is a rule-based sentiment analysis model that combines a sentiment-oriented lexicon with a set of linguistic rules. This lexicon comprises words and emoticons labeled by their sentiment orientation—positive, negative, or neutral. VADER evaluates not only the sentiment of individual words but also their contextual impact, taking into account modifiers, conjunctions, and punctuation to determine the overall sentiment of the text.

### Understanding the Return Scores:

The `polarity_scores` method of the `vaderSentiment` library returns a dictionary with four key sentiment scores:

*   **neg (Negative):** Represents the proportion of text classified as negative. Scores near 1 indicate strong negative sentiment.
*   **neu (Neutral):** Indicates the proportion of text considered neutral. Higher scores suggest a predominantly neutral sentiment.
*   **pos (Positive):** The proportion of text with a positive sentiment. Like the negative score, a score close to 1 signifies strong positive sentiment.
*   **compound:** A normalized composite score ranging from -1 (extremely negative) to +1 (extremely positive), offering an overall sentiment measure by considering the intensity of both positive and negative elements.

These scores provide a nuanced view of sentiment, especially useful for analyzing short, expressive texts common in modern digital communication. The **compound** score, in particular, serves as a comprehensive sentiment indicator, useful for text classification or sentiment comparison across texts.
