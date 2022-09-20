#Introduction
Tools :-Microsoft Azure 
We propose a end-to-end system which makes use of a recurrent encoder-decoder deep neural network to translate speech from the Hindi (Fourth most spoken language in the world) directly to the text in English(First most spoken language). We apply a slightly modified sequence-to-sequence with attention architecture that has previously been used for speech recognition and show that it can be repurposed for this more complex task. To address the lack of Hindi Audio to English Text, we create our own dataset using Speech and Text from Hindi media files. We demonstrate that our developed model successfully outperforms the traditional cascade of ASR and MT models. Although the model can learn the utterance of common words, it fails to learn uncommon words and the underlying grammar. Thus, we also propose methods to mitigate this challenge.


#Why Speech Translation?
Valuable for documentation of low-resource languages. Helpful in crisis relief; Can help workers to respond to requests made in a foreign language. Extend access of regional media resources to global crowd( Ex: Youtube Auto-Caption).

#Why End-to-End Model?
Automatic Speech Recognition + Machine Translation is expensive in terms of resource. Source Audio, Source Transcription and Target Translation is required. Error gets compounded between the cascaded models

#Audio Pre-Processing:
Audio was split to clips based on timestamps provided in subtitles file.
Clip corresponding to Music was eliminated
80-Dimensional Mel Fbank, Delta, and Delta-Delta Features were extracted for windows of 25ms and Stride of 10ms. (Decomposition of Audio based on frequency(Hz).)
#Text Pre-Processing:
Basic Cleaning: Removed Punctuations and Lowercase each character.
Lemmatized words using NLTK package. (Vocab Reduction: 2k Words)
Eliminated Words with Less than 10 Occurrences and replaced them with placeholder in the text.( Vocab Reduction: 6k words; Occurence Reduction: ~15k)
