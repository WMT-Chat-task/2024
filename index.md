---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

# Welcome to the WMT 2024 Chat Shared Task!

## Updates

### March 15th, 2024

``❗`` Training data is available [here]().

``❗`` Please also register to the chat-shared-task [google-group](https://groups.google.com/g/wmt-chat-task) in order to be able to receive immediate updates announcements and ask us questions! 

``❗`` Devsets along with baselines scores on them will be available soon! 

<br />

## Overview

<p class="message">  
  Translating conversational text, in particular customer support chats, is an important and challenging application for machine translation technology. This type of content has so far not been extensively explored in prior MT research, largely due to the lack of publicly available data sets. Prior related work has mostly focused on movie subtitles and European Parliament speeches.<br />

  In contrast to the translation of the news stories, software manuals, biomedical text, etc. in which the text is carefully authored and well formated, chat conversations are less planned, more informal, and often ungrammatical.
  Further, such conversations are usually characterized by shorter and simpler sentences and contain more pronouns.<br />
  In effect, the task of translating chat conversations can be regarded as a two-in-one task, modelling both dialogue and translation at the same time.<br />
</p>

Machine translation systems trained for chat conversations are expected to deal with the task's inherent challenges and characteristics, such as (among others):
- The importance of using extended context for translating the segments and modelling dialogue. E.g. Agreement and anaphora resolution requiring inter-sentential modelling:
  - `I had a flight with AirLiberty for next Saturday from Lisbon to Abu Dhabi. Could you please change it to next Monday?`
- Robustness to noisy input. Chat text is usually noisier, containing misspelled words, wrong casings, incomplete sentences, etc.,
- Consistent and coherent translation throughout the entire conversation, and
- Modeling of all the speakers and language directions involved in the conversation, where each can be regarded as a different sub-domain (depending on the task).

The primary goal of this Chat shared task is to encourage participants to train and test models specific for bilingual chat conversations in a corpus composed of original bilingual costumer support conversations.

This year we expanded the language pairs to en⇔de, en⇔fr, en⇔pt_br, en⇔ko and en⇔nl.

We encourage participants to use the **bilingual context** in the translation models submissions.<br />

Have questions or suggestions? Feel free to <a href="mailto:wmt.chat.task@gmail.com">Contact Us</a>!

## Chat Task Important Dates
<style scoped>
table {
  font-size: 14px;
}
</style>

|  | Date |
| ----------- | :-----------: |
| Training set ready to download | March 2024 |
| Validation set ready to download | May 2024 |
| Test set ready to download | June/July 2024 |
| Submission deadline for Chat task | July 2024 |
| Paper submission deadline to WMT | TBA around 12th August (follows EMNLP) |
| WMT Notification of acceptance | TBA (follows EMNLP) |
| WMT Camera-ready deadline | TBA around 23rd September (follows EMNLP) |
| Conference | 12-13 November, 2024 |

## Goals

The goals of chat translation shared task are to provide the common ground for:

- Studying the applicability of machine translation systems for translating conversational text;
- Investigating the impact of context in a conversation's translation;
- Studying the feasibility of an all-in-one multi-lingual system;

## Task Description

A critical challenge faced by international companies today is delivering customer support in several different languages. One solution to this challenge is centralizing support with English speaking agents and having a translation layer in the middle to translate from the customer's language into the agent's (English) and vice versa.

## Data

The data used in this shared task is composed of genuine bilingual costumer support conversations.
One of the main challenges of this domain is the lack of real bilingual training data available.



Please note, that all the data released for the WMT24 Chat Translation task is under the license of [CC-BY-NC-4.0](https://creativecommons.org/licenses/by-nc/4.0)
 and can be freely used for research purposes only. Please note that, as the license states, no commercial uses are permitted for this corpus. We just ask that you cite the WMT24 Chat Translation Task overview paper. Any other use is not permitted unless previous written authorization is given by Unbabel.
   
## Datasets

The Training sets of all the language pairs are available in the [github]() repository.
The files contain the bilingual conversations by a customer and an agent in their original language.
Here is an example of such a conversation:


| **source_language** | **mt_language** | **source_segment**                                                                                                                                                       | **pe_segment**                                                                                                                                                                                           | translation_direction |
|-----------------|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| fr              | en          | Bonjour je ne peut pas utiliser mes jetons accumuler pour acheter un livre audio                                                                                         | Hello, I can't use the tokens I accumulated to buy an audio book.                                                                                                                                 | customer              |
| en              | fr          | Thank you for contacting #PRS_ORG#, it was my pleasure to assist you today.                                                                                              | Merci d'avoir contacté #PRS_ORG#, ce fut un plaisir de vous aider aujourd'hui.                                                                                                                    | agent                 |
| en              | fr          | I hope you have an excellent day.                                                                                                                                        | J'espère que vous passez une excellente journée.                                                                                                                                                  | agent                 |
| en              | fr          | Please allow me a moment to verify the account.                                                                                                                          | Veuillez m'accorder un moment pour vérifier le compte.                                                                                                                                            | agent                 |
| en              | fr          | I am sorry that you are experiencing this issue, I will do my best to assist you.                                                                                        | Je suis désolé que vous rencontriez ce problème, je ferai de mon mieux pour vous aider.                                                                                                           | agent                 |
| en              | fr          | What is the error message or problem you are getting when trying to use your audio book credits?                                                                         | Quel est le message d'erreur ou le problème que vous rencontrez lorsque vous essayez d'utiliser vos crédits de livres audio ?                                                                     | agent                 |
| fr              | en          | Je ne peu pas effectuer l achat je peu juste le faire avec #PRS_ORG# ou par carte                                                                                        | I am unable to make the purchase, I can only do it with #PRS_ORG# or by card.                                                                                                                     | customer              |
| en              | fr          | Are your credit s from an #PRS_ORG# subscription?                                                                                                                        | Vos crédits proviennent-ils d'un abonnement #PRS_ORG# ?                                                                                                                                           | agent                 |
| fr              | en          | Oui                                                                                                                                                                      | Yes.                                                                                                                                                                                              | customer              |
| en              | fr          | I understand, at the moment we no longer work with #PRS_ORG#, they are not partnered with us anymore, probably that is the error, please let me confirm this information | Je comprends, pour le moment nous ne travaillons plus avec #PRS_ORG#, ils ne sont plus en partenariat avec nous, c'est probablement la raison de l'erreur, laissez-moi confirmer ces informations | agent                 |
| fr              | en          | Mais ça me met que j ai 13 jetons à utiliser                                                                                                                             | But it shows that I have 13 tokens.                                                                                                                                                               | customer              |
| en              | fr          | I am confirming the information with my team, thanks for your patience                                                                                                   | Je confirme les informations avec mon équipe, merci pour votre patience                                                                                                                           | agent                 |

<br /><br />
As you can see, the source sentences (i.e. *source_segment*) are in the original language of the speaker, i.e. French in the case of *customer* and English in the case of *agent*. And the translations (i.e. *pe_segment*).
Moreover, since the data is anonymised, we have the entities replaced by the following special tokens:

| **Token**         | **Description**                          |
|-------------------|------------------------------------------|
| #NAME#            | Person’s names                           |
| #PRS_ORG#         | Products and Services, and Organizations |
| #ADDRESS#         | Address                                  |
| #EMAIL#           | E-mail address                           |
| #IP#              | IP Address                               |
| #PASSWORD#        | Password                                 |
| #PHONENUMBER#     | Phone number                             |
| #CREDITCARD#      | Credit card number                       |
| #URL#             | URL Address                              |
| #IBAN#            | IBAN number                              |
| #NUMBER#          | Any number (all digits)                  |
| #ALPHANUMERIC_ID# | Any alphanumeric ID                      |

<br />

<span style="color:red">**Note**</span> that for training and validation purposes you can use the training data of the general task (including the data of the previous editions), the data of the other tracks (eg. biomedical) if you find them useful for this task, and the other corpora (either parallel or monolingual) that are publicly available for the research purposes, like most of the corpora available on OPUS, as well as the data of the previous edition of the Chat Translation Task.

<br />

## Baseline Scores on DevSets

Baseline scores on Dev data will be avaiable by May 2024.

<br />

## Test Sets (Evaluation Data)

Test Sets will be available by June/July 2024.

### Submission Format
TBD
<br />

## Evaluation
The Systems' performance will be evaluated along two domensions:

1) Human evaluation
   - Human evaluation that utilizes the conversational context to rate the translation quality on a direct assessment scale of [0-100].
     
2) Automatic evaluation
   - Overall translation quality via [chrF](https://github.com/mjpost/sacrebleu?tab=readme-ov-file#chrf--chrf), [BLEU](https://github.com/mjpost/sacrebleu?tab=readme-ov-file#bleu), [COMET-22](https://github.com/Unbabel/COMET) and Contextual-Comet-QE.
   - Accuracy performance ([F1 scores](https://github.com/CoderPat/MuDA/tree/main)) of system's outputs compared to the reference for words tagged with context-dependent phenomena (lexical cohesion, formality, pronoun resolution and verb forms).


The human document-level evaluation will be performed only on the primary submission and will be used for the official rankings of the participating teams accounting for both directions.
The automatic will be used as the secondary metric.

<br />

## Paper Describing Your MT Systems
Participants are invited to submit a short paper (4 to 6 pages) to WMT describing their MT system. Information on how to submit is available [here](https://www.statmt.org/wmt22).<br />
Please note that the shared task submission description papers are non-archival, and it is not mandatory to submit a paper if you do not want to.

## Organization:

- Wafaa Mohammed, UvA
- Ana C. Farinha, Unbabel
- M. Amin Farajian, Unbabel
- José Souza, Unbabel
- Sweta Agrawal, Instituto de Telecomunicações
- Vera Cabarrão, Unbabel
- Bryan Eikema, UvA

## Sponsors

<style>
	.column {
	  float: left;
	  padding: 20px;
	}
	
</style>
<div style="position: relative; width: 700px; height: 100px; min-height: 200px">    
    <div style="position: relative; bottom: 0px;">
	   <div class="column">
	     <img src="/public/css/uva.png" height=100px width=auto>
	   </div>
	</div>
 <div style="position: relative; width: 700px; height: 100px; min-height: 200px">    
    <div style="position: relative; bottom: 0px;">
	   <div class="column">
	     <img src="/public/css/unbabel.png" height=100px width=auto>
	   </div>
	</div>

