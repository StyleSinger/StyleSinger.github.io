{:.no_toc}
* toc
{:toc}

# Abstract

Singing Voice Synthesis (SVS) is devoted to the artistry of crafting exquisite vocal melodies by harnessing the power of lyrics and musical notations. Existing SVS methods encounter a decline in the quality of synthesized vocal renditions in out-of-domain (OOD) scenarios. Moreover, there is a scarcity of methodologies proficient in capturing the intricate and dynamic nature of vocal styles. To address the demand for OOD style transfer in singing voice, we propose StyleSinger, the first model for high-fidelity zero-shot style transfer of out-of-domain voices. It primarily encompasses two approaches to enhance the effectiveness: 1) the Detail Style Adaptator (DSA) is employed to meticulously model the inherent attributes of vocal performances, thereby encapsulating the intricate subtleties of diverse style characteristics. 2) the Uncertainty Modeling Layer Norm (UMLN) is utilized as a method to bolster the model's overall resilience and adaptability. Our comprehensive evaluations in zero-shot style transfer unequivocally establish that StyleSinger outperforms baseline models in terms of quality and similarity to reference audio. 

# Parallel Style Transfer Samples

In the context of out-of-domain (OOD) scenarios, where the content of the reference voice remains unchanged

<ruby>1. Reference/Target Text: 风花雪月的诗句里我在年年的成长breathe</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/ref/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styler/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/speech/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<table style='width: 100%;'>
	<thead>
		<tr>
      			<th style="text-align: center">YourTTS</th>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/yourtts/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/rms/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/stylesinger/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>


# Non-Parallel Style Transfer Samples

In out-of-domain (OOD) scenarios, we utilize unseen reference audio with target notes and lyrics to synthesize the target singing voice. 

# Ablation Studies
