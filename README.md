# LIN 177 Final Project
Jerry Wu

Section A03

## Introduction
For the final project, I am expanding on the `japanese.swipl` program from Homework 1. Here, I am exploring some (but not all) verb conjugations. The main form I am looking at is the indicative form, with a little bit of the progressive form as extra.

In the original `japanese.swipl`, we had:
> _Adamu ga waraimasu._\
> Adam laughs.

For this assignment, we just declared _waraimasu_ as the verb, but it stems from the root word _warau_.
Much like in English, we can say "Adam laughs" to show present tense, and "Adam laughed" in past tense.
Japanese also does this by modifying the root word and doing a suffixation.
In the case of _warau_, _u_ is dropped and _imasu_ is added to the end.
Here is another set of examples:
> _Adamu wa waraimasu._ Adam laughs.\
> _Adamu wa waraimashita._ Adam laughed.\
> _Adamu wa waraimasen._ Adam won't laugh.\
> _Adamu wa waraimasendeshita._ Adam did not laugh.\
> _Adamu wa waratteimasu._ Adam is laughing.

The conjugation also depends on the root word itself, so it is not a matter of simply dropping the _u_ letter as seen above.
Japanese is a syllabic language, so it comes down to the syllables.
There are two main types of verbs in Japanese, _U_-verbs and _RU_-verbs.
As shown above, _warau_ is an U-verb. Separate the word into syllables and we get _wa-ra-u_. It ends with _u_, it is classified as such.
A word like _ne-ru_ (to sleep) ends in _ru_ so it is a _RU_-verb.
There are also words that look like _RU_-verbs, such as _sha-be-ru_ (to speak), but it's actually an _U_-verb.
It doesn't help that words like _ne-ru_ have multiple meanings (can also mean "to knead") and can be both an _U_-verb and a _RU_-verb.

Here is a set of examples featuring a _RU_-verb.
> _Iivu wa nemasu._ Eve sleeps.\
> _Iivu wa nemashita._ Eve slept.\
> _Iivu wa nemasen._ Eve won't sleep.\
> _Iivu wa nemasendeshita._ Eve did not sleep.\
> _Iivu wa neteimasu._ Eve is sleeping.

In addition, there are two irregular verbs, _suru_ (to do) and _kuru_ (to come). On the outside, they look like _RU_-verbs, but they have their own unique conjugations. Here is a set of examples featuring _benkyousuru_ (to study, literally meaning, to do study):
> _Kurisu wa benkyoushimasu._ Chris studies.\
> _Kurisu wa benkyoushimashita._ Chris studied.\
> _Kurisu wa benkyoushimasen._ Chris won't study.\
> _Kurisu wa benkyoushimasendeshita._ Chris did not study.\
> _Kurisu wa benkyoushiteimasu._ Chris is studying.

To add more, Japanese also has verb conjugations for formality. The examples above are formal, but here are what informal looks like:
> _Furanku wa neru._ Frank sleeps.\
> _Furanku wa neta._ Frank slept.\
> _Furanku wa nenai._ Frank won't sleep.\
> _Furanku wa nenakatta._ Frank did not sleep.\
> _Furanku wa neteiru._ Frank is sleeping.

## Approach and Argumentation
