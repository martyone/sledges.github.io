---
IMPORTANT NOTE: DO NOT EDIT THIS FILE, instead edit its .mdpp then run ./precheckin.sh
title: Italian
permalink: Develop/L10n/Style_Guides/Italian/
parent: Style Guides
grand_parent: L10n
layout: default
---

# Style guidelines and principles

This document provides generic style guidelines for Sailfish OS. The
target audience for this documentation is everyone translating Sailfish
OS-related material. The goal is to create contemporary translations
that provide a high-quality user experience.

Sailfish OS audience and target group for the translations is young,
active users accustomed to social media and therefore its language.

# Basics of good writing style

  - Write in a personal style, engaging and involving the user.
  - Use active style and present tense. Use imperatives and talk to the
    user.
  - Make sure the text is consistent and clear and correct in grammar
    and spelling.
  - Write in short sentences.
  - Use a positive tone, avoid negative expressions.
  - Avoid ambiguity. Make sure that pronouns point clearly to the
    relevant nouns, and avoid long strings of modifiers or nouns.

Remember we are sailing on a jolly boat. Have fun\! Play with the
language. Be innovative and guide the readers onto a journey. Do not
attempt to use humor, but use fresh and fun tone where it naturally
fits. Remember that the most important part is delivering a clear
message.

Note that in technical writing, descriptions and instructions should not
include text that is written from a marketing point of view.

# Language and culture

Because our communication is targeted to international use and part of
it will be translated, try to keep the language culturally unambiguous,
be careful of religious references, and avoid using idiomatic
expressions or slang. The key aspects are clarity and simplicity.
Consider these targets when adapting the jolly tone to the texts. In
software UI translations: Respect the source text, but do not create
word for word translations. Take the context into account when
translating.

# Grammar

## Articles

When possible, leave out articles.

## Person

Please try to be informal if that feels natural in your language. Avoid
mentioning pronouns.

Keep addressing consistent: e.g. if a paragraph was started using the
second person, retain it throughout all its sentences (as opposed to
switching to third person or neutral mood).

## Gender

Use gender-neutral or all-inclusive terms to refer to human beings,
rather than terms that include man, woman, and similar masculine and
feminine terms.

## Tense

Use the present tense. E.g.:

  - Correct: **Media player consente di scegliere brani musicali.**
  - Incorrect: **Media player consentirà di scegliere brani musicali.**

## Voice

Whenever possible, use the active voice. Keep the message clear and the
sentences short.

For example:

  - Correct: **Crea Impostazioni account in...**
  - Incorrect: **Le Impostazioni account devono essere creati in...**

## Mood

Use the imperative form.

For example:

  - Correct: **Vai a Impostazioni**
  - Incorrect: **Andare su Impostazioni**

## Orthography

The most current rule about "d eufoniche" is that they should only be
appended to "e" and "a" if the word that follows begins with the same
letter. This is no real grammar rule, so deviations are tolerated, but
it is important to stay consistent in recurring formulations that
contain the term, and sticking to the rule can be of help.

Conjunction "o" NEVER takes a "d eufonica" ("od"). If it is followed by
a word beginning with "o" and the clash is unbearable, use "oppure".

Apply standard grammar rules of accentuation. In normal situation, the
only accented letter that can ever be capitalized is È, however it is
possible that you will need to enter other accented characters when
translating a text that is in all capitals. Never use an apostrophe to
add an accent to a capital letter.

## Capitalisation

Capitalise application names and company names.

In the UI, start the first word with a capital letter.

Respect capitalisation rules of the language in question.

Do NOT capitalise start of phrase following a paragraph title such as
Example:, Note: Important:, etc. For example:

  - Correct: **Nota: un elenco puntato**
  - Incorrect: **Nota: Un elenco puntato**

Do NOT capitalise the words menu, screen, window, dialog box, chapter,
button, list, regardless of the capitalization used in the source. E.g.:

  - Correct: **Viene visualizzato il menu File**
  - Incorrect: **Viene visualizzato il Menu File**

When describing a functionality that has a name in the interface, use
appropriate capitalisation, e.g. **Vai a Home**.

## Menu style in the UI

User Interface menu items are named using verbs.

## Empty states in the UI

User Interface empty states are typically written in the 2-sentence
form, using verbs and active tone and, where possible, guiding the user
towards the next possible steps to take. Keep sentences short and
content informative. Where possible, guide user to reflect the good
sides of an application or service (like referring to friends instead of
contacts in the People app). For example:\
(tell the situation, what items are missing) (point user to next actions)\
No contacts yet. Pull down to add your friends.

App covers (that are shown in the Home) for empty states aim to be short
informative messages. Length is typically two words.

# Punctuation

## End punctuation

In UI strings, do not use a full stop at the end of a sentence if
there’s only one sentence. If there are two or more sentences, use
full stops normally.

If the segment ends with the colon or ellipsis, the translation should
follow the source.

## Abbreviations

In technical writing, use common abbreviations. Do not use Latin
abbreviations.

In the UI, use common abbreviations, including Latin abbreviations. Make
sure text clarity does not suffer. If in doubt, do not use an
abbreviation.

Do not use a full stop in or after acronyms or initialisms, e.g.:

  - Correct: **WLAN**
  - Incorrect: **W.L.A.N.**

Do not use a full stop with unit (measurement) symbols, e.g.:

  - Correct: **kg**
  - Incorrect: **kg.**

Use a full stop with Latin abbreviations, e.g.:

  - Correct: **e.g., ca., etc.**
  - Incorrect: **eg, ca, etc**

## Contractions

Do not use contractions (e.g. aren't, should've) in technical writing.

In the UI, contractions can be used when needed if the space is limited.
Make sure that information given to the user is not lost because of such
shortcuts.

Before using a contraction, try to rephrase the text so that contraction
can be avoided. Omit words that are not essential for delivering the
message clearly. If contracting cannot be avoided, minimize the number
of words contracted. It is better to contract one word more than to
contract several words a little.

## Plurals

Do not create plurals with parentheses. Consult translation tool user
guide for handling the plurals.

If a singular/plural option is provided, please prefer the plural. E.g.:

  - Correct: **Aprire i documenti**
  - Incorrect: **Aprire il documento (i documenti)** or **Aprire il
    documento(i)**

## Quotation marks

Respect language's quotation rules. A comprehensive list of marks can be
found here:
<https://en.wikipedia.org/wiki/Quotation_mark#Summary_table_for_various_languages>

Regardless of English using curly, straight, double, or single quotes,
always use double straight quotation marks (") both for opening and
closing the quoted sentence. Use a straight apostrophe whenever one
apostrophe is needed (**l'ID, un'unità**). Some text editors have an
AutoCorrect feature that will automatically insert curly quotes when a
straight quote is typed, please make sure that this feature is off.

## Hyphenation

Compound words are usually merged into one word in Italian.

Try to avoid using hyphenation, even though this is accepted in some
cases. Example:

  - Correct: **Online**
  - Incorrect: **On-line**

## Comma

Several rules of thumb about commas don't correspond to an actual
grammar rule. In general, please do apply the rule of not using a comma
before "e", but do use one if it helps to create the right logical
connection between different parts of a sentence. The most frequent case
is if the sentence beginning with "e" is preceded by a parenthetical
sentence enclosed in commas.

## Lists

In technical writing, write lists with bullets.

In the UI, write lists without bullets or colons.

## Headings

In technical writing, create structured, consistent and accurate
headings. Consider verb structures in headings.

In Italian, when the English uses the "-ing" form, the substantivated
form is to be preferred for the translation of heading text; instead, if
a verbal infinitive form is used, please check if it introduces a
procedure. If this is the case, please use the infinitive also in
Italian, otherwise use the noun. In English some headings may appear
with all uppercase initials. In Italian only the initial letter of the
initial word must be capitalised.

## Text modules

In technical writing, make sure each module can be read independently,
containing all the needed information so that modules do not need to be
read in any certain order.

## Procedures

In technical writing, when describing procedures, make sure to describe
the steps clearly with only one task per step. Describe the expected
results of those steps.

# Numerals

## Numbers

Write numbers as digits, including numbers below 10.

For example:

  - Correct: **1 nuovo messaggio**
  - Incorrect: **Un nuovo messaggio**

Use a dot (.) as the thousand separator only when English uses their
separator as well. Use a comma (,) as the decimal separator.

## Measurements

Use numerals for measurements.

Use a space between the numeral and the unit, except with degree and
percentage sign. E.g.:

  - Correct: **5 cm, 20°, 20 °C**
  - Incorrect: **5cm, 20 °, 20°C**

# Terminology

Sailfish OS has a separate Terminology project to maintain consistency.
Use that approved terminology when available.

## Company names

Do not translate company names unless there is an official, translated
name available.

## Product names and trademarks

Do not translate product names or trademarks.

## Safety information and legal texts

Warnings, cautions, and notes are legal texts that need to be confirmed
with legal department. In case of legal texts, follow the instructions
carefully and ask for more information if needed.

# Checklist

When finalising translations for the UI, check the following:

  - Everything has been translated to your best knowledge.
  - Spell check is done.
  - Check consistency with the other translations done for the language.
  - Ensure correct Sailfish OS terminology is used. If needed, propose
    new term entries.
  - Confirm legal texts are consistent with the source.
  - Company and product names, trademarks, symbols, and measurements
    have not been hyphenated.
  - Ensure regional formats are retained, such as date, time, numeric
    and quotation literals.

When finalising texts for the technical writing, check these points as
well:

  - Titles and headings are structured and accurate.
  - Language is clear and consistent.
  - Sentences vary in length and have a clear form.

