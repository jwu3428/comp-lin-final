# LIN 177 Final Project
Jerry Wu\
Section A03

## Introduction
For the final project, I am expanding on the `japanese.swipl` program from Homework 1. Here, I am exploring some (but not all) verb conjugations. The main form I am looking at is the indicative form, with a little bit of the progressive form as extra.

In the original `japanese.swipl`, we had:\
> _Adamu ga waraimasu._\
> Adam laughs.

For this assignment, we just declared _waraimasu_ as the verb, but it stems from the root word _warau_.
Much like in English, we can say "Adam laughs" to show present tense, and "Adam laughed" in past tense.
Japanese also does this by modifying the root word and doing a suffixation.
In the case of _warau_, _u_ is dropped and _imasu_ is added to the end.
Here is another set of examples:\
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

Here is a set of examples featuring a _RU_-verb:\
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
To approach this problem, first, the verbs are now split into syllables. This helps with the conjugation process. In addition, more identifiers like `root` and `u` are added, so it now looks like `[verb,root,u,intransitive]` to help identify the verb. I believe this is the main approach to this problem because of the nature of the Japanese verb identification and how the verb forms can be ambiguous as shown in the introduction. Additionally, I have separated the irregular verbs from the _U_- and _RU_-verbs. Some parts such as the formation of sentences are left mostly the same, except for some formality additions and the conjugation. I also added additional verbs and an additional noun that corresponds with one of the verbs, _kaeru_ (to return). Just for looks, I used `atomic_list_concat` to make the verbs look nicer when printed out to the terminal.

The majority of the code is in the actual conjugation. To aid in the conjugation process, I added a few helper functions.

`delete_char` takes an atom and deletes characters specified by `Input`. This is for deleting characters from the verbs/syllables.\
`suffix` takes an atom (transformed from a list) and concatenates it with the specified `Input`. This is useful for adding characters to the syllables during conjugation.\
`extract_last` gets the last element in a list. This is useful for grabbing the last syllable in the verb. It also calls `delete_last`, which deletes the last element in a list. When the syllable is extracted, we want to replace the last syllable with new ones based on the conjugation.

`conjugate` conjugates the verbs. There are six functors, each dealing with the different verb types. I took advantage of a branching technique, surrounding snippets of code in parentheses and using `;`, which signifies "OR". This is useful for dealing with the different verb forms. Each branch takes care of manipulating the last syllable of the verb and appending the correct Japanese verb ending and its English definition. I made some workarounds for the English definitions, which will be discussed in the issues section below. For the irregular verbs, I felt it was appropriate to just hardcode the conjugations of how unique they are. Of course, this will also take into account verbs that use _suru_ and _kuru_ as part of the word like _benkyousuru_ and _aisuru_, which use the _suru_ conjugations. This is done by examining the last two syllables and see if they match `[su,ru]` and `[ku,ru]`.

I also expanded a little more to include one more sentence type. I wanted to see how I could model a directional verb like returning home. Therefore, I added `[uchi]` and let it mean "the house" and declared it `[place]`. This noun would be used with _kaeru_ meaning to return somewhere. I added an additional noun phrase with regard to place. In Japanese, the _ni_ particle is similar to saying "to" in English. Thus, I modeled something like:\
> _Adamu wa uchi ni kaerimasu._ Adam returns to the house.

## Issues
One of the issues I've encountered was doing the English definitions. English has its own rules regarding verb conjugations and could result in some inconsistencies. However, for the sake of the project and the problem I'm actually doing, disregarding the translations, I feel the program is principled in handling Japanese verb conjugations. As a result, I didn't pay the English translations much mind because that is another problem for another day, and simply hardcoded a few of the translations like "sleep" to "slept" and "come" to "came".
