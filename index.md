{:.no_toc}
* toc
{:toc}

# Abstract

Style transfer for out-of-domain (OOD) Sing Voice Synthesis (SVS) focuses on generating high-quality singing samples with unseen style (such as timbre, emotion, pronunciation and articulation skills) derived from a reference audio. However, existing SVS methods encounter a decline in the quality of synthesized singing voices in OOD scenarios, as they rest upon the assumption that the target vocal attributes are discernible during the training phase. Moreover, the endeavor to model the intricate nuances of singing voice styles is an arduous task, as singing voices possess a remarkable degree of expressiveness. To overcome these challenges, we propose StyleSinger, the first singing voice synthesis model for zero-shot style transfer of out-of-domain reference samples. StyleSinger incorporates two key approaches for enhanced effectiveness: 1) the Uncertainty Modeling Layer Norm (UMLN) to perturb the style attributes within the content representation during the training phase so improve the model generalization, and 2) the Residual Style Adaptor (RSA) which employs the Residual Quantization (RQ) module to capture diverse style characteristics in singing voices. Our comprehensive evaluations in zero-shot style transfer unequivocally demonstrate that StyleSinger surpasses baseline models in terms of quality and similarity to the reference audio.

# Parallel Style Transfer Samples

In the context of out-of-domain (OOD) scenarios, where the content of the reference voice remains unchanged.

1. Reference/Target: 风花雪月的诗句里我在年年的成长 AP
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

2. Reference/Target: 为春风吹落 AP SP AP 只是简简单单的爱过我还
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

3. Reference/Target: 我还在逞强 AP 说着谎 AP 也没能力遮挡你去的方向
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

1. Reference: 风花雪月的诗句里我在年年的成长 AP

Effectively capturing the timbre, pitch transitions, vocal techniques, and the delicate articulation skill.
<table style='width: 33.3%;'>
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

Target: 吹向我脸庞 AP 想起你轻柔的话语 AP 曾打湿我眼眶 AP
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/001.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<table style='width: 66.7%;'>
	<thead>
		<tr>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/001.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/001.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

2. Reference: 为春风吹落 AP SP AP 只是简简单单的爱过我还

Successfully transferring the timbre, vocal techniques, and the subtle elongation in articulation skill.
<table style='width: 33.3%;'>
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

Target: 幸福没有那么容易 AP 才会特别让人着迷 AP 什么都不懂的年纪 AP
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/002.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/002.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/002.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<table style='width: 66.7%;'>
	<thead>
		<tr>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/002.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/002.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

3. Reference: 圈圈圆圆圈圈天天年年天天的我深深看你的脸 AP 生气的温柔埋怨的温柔 SP

Successfully transferring the timbre, vocal techniques, vibrato skill and the subtle elongation in articulation skill.
<table style='width: 33.3%;'>
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

Target: 修炼爱情的心酸 AP 学会放好以前的渴望 AP 我们那些信仰要忘记多难
<table style='width: 100%;'>
	<thead>
		<tr>
			<th style="text-align: center">Styler</th>
			<th style="text-align: center">GenerSpeech</th>
      			<th style="text-align: center">YourTTS</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/styler/003.wav" type="audio/wav"></audio></td>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/generspeech/003.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/yourtts/003.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>

<table style='width: 66.7%;'>
	<thead>
		<tr>
			<th style="text-align: center">MS RMSSinger</th>
			<th style="text-align: center">StyleSinger</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/rmssinger/003.wav" type="audio/wav"></audio></td>
      			<td style="text-align: center"><audio controls style="width: 150px;"><source src="wavs/nonparallel/stylesinger/003.wav" type="audio/wav"></audio></td>
		</tr>
	</tbody>
</table>


# Ablation Studies

We undertake ablation studies to showcase the efficacy of various designs incorporated within StyleSinger.
UMLN and RSA is the Uncertainty Modeling Layer Norm and the Residual Style Adaptor, while Pitch and Decoder means the pitch diffusion predictor and the diffusion decoder.

1. Reference/Target: 是我唯一沉溺 AP 你是爱我的 AP 就不怕有缝隙 SP
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
      			<th style="text-align: center">wo RSA</th>
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
