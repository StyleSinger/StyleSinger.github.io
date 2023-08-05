{:.no_toc}
* toc
{:toc}

# Abstract

Singing Voice Synthesis (SVS) is devoted to the artistry of crafting exquisite vocal melodies by using lyrics and musical notations. 
The increasing demand for singing voice style transfer in out-of-domain (OOD) scenarios poses a challenge for SVS systems.
Existing SVS methods encounter a decline in the quality of synthesized vocal renditions in OOD scenarios. 
Moreover, there is a scarcity of methodologies proficient in capturing the intricate and dynamic nature of singing voice style (such as timbre, emotion, pronunciation and articulation skills). 
To overcome these challenges, we propose StyleSinger, the first singing voice synthesis model for high-fidelity zero-shot style transfer of out-of-domain reference samples. 
It primarily encompasses two approaches to enhance the effectiveness: 
1) the Residual Style Extractor (RSE) is employed to meticulously model the diverse style characteristics. 
2) the Uncertainty Modeling Layer Norm (UMLN) is utilized to bolster the model's overall resilience and adaptability. 
Our comprehensive evaluations in zero-shot style transfer unequivocally establish that StyleSinger outperforms baseline models in quality and similarity to reference audio. 

# Parallel Style Transfer Samples

In the context of out-of-domain (OOD) scenarios, where the content of the reference voice remains unchanged.

<ruby>1. Reference/Target: 风花雪月的诗句里我在年年的成长 AP</ruby>
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
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styesinger/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>2. Reference/Target: 为春风吹落 AP SP AP 只是简简单单的爱过我还</ruby>
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
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/ref/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styler/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/speech/002.wav" type="audio/wav"></audio></td>
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
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/yourtts/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/rms/002.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styesinger/002.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>3. Reference/Target: 我还在逞强 AP 说着谎 AP 也没能力遮挡你去的方向</ruby>
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
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/ref/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styler/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/speech/003.wav" type="audio/wav"></audio></td>
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
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/yourtts/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/rms/003.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/parallel/styesinger/003.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

# Non-Parallel Style Transfer Samples

In out-of-domain (OOD) scenarios, we utilize unseen reference audio with target notes and lyrics to synthesize the target singing voice. 

<ruby>1. Reference: 风花雪月的诗句里我在年年的成长 AP</ruby>
<ruby>Effectively capturing the timbre, pitch transitions, vocal techniques, and the delicate articulation skill.</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/ref/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>Target: 吹向我脸庞 AP 想起你轻柔的话语 AP 曾打湿我眼眶 AP</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>2. Reference: 为春风吹落 AP SP AP 只是简简单单的爱过我还</ruby>
<ruby>Successfully transferring the timbre, vocal techniques, and the subtle elongation in articulation skill.</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/ref/002.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>Target: 幸福没有那么容易 AP 才会特别让人着迷 AP 什么都不懂的年纪 AP</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/002.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/002.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/002.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>3. Reference: 我还在逞强 AP 说着谎 AP 也没能力遮挡你去的方向</ruby>
<ruby>Successfully transferring the timbre, vocal techniques, and the subtle elongation in articulation skill.</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/ref/003.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<ruby>Target: 我就这样告别山下的家 SP AP</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/003.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/003.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/003.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

# Ablation Studies

We undertake ablation studies to showcase the efficacy of various designs incorporated within StyleSinger.

<ruby>1. Reference/Target: 是我唯一沉溺 AP 你是爱我的 AP 就不怕有缝隙 SP</ruby>
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Reference</th>
			<th style="text-align: center">StyleSinger</th>
			<th style="text-align: center">wo UMLN</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/ref/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/stylesinger/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/wo umln/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<table style='width: 100%;'>
	<thead>
		<tr>
      			<th style="text-align: center">wo RSE</th>
			<th style="text-align: center">wo Pitch</th>
			<th style="text-align: center">wo Decoder</th>
		</tr>
	</thead>
	<tbody>
		<tr>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/wo dsa/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/wo ppdp/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/ablation/wo decoder/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>
