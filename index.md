<p align="justify">
This project maps <strong>speech</strong> and <strong>music</strong> to the same embedding space and supports music item search for speech query by calculating the similarity between them. The detail of the methodology for building the dataset please refer to our paper
</p>

### Overview
<p align="justify">
Automatic speech emotion recognition (SER) can be used as a music recommendation application for content creators.
In this paper, our goal is to assist content creators in finding music that matches the emotion of their speech.
We focus on a cross-modal speech-to-music retrieval framework to simultaneously perform feature extraction and bridge the modality gap using emotion labels. Moreover, we propose a novel masking fusion method, which obtains the ensemble effect by stochastic modality feature selection.
Our experiments show that we can successfully bridge the gap between modalities to facilitate cross-modal retrieval.
In addition, comprehensive experimental results compared with four retrieval methods on five speech modality representations verify the effectiveness of our masking fusion method.
</p>

![Model Architecture Ver 5 small artboard 2](./assets/img/main.png)
<p align="center">Figure.1 Speech to Music</p>

### In the wild demo
<p align="justify">
To demonstrate real industrial scenarios, we use samples from social media contents (tiktok #actingscene tag) and audio books contents (youtube). 
It also searches for music using only the audio modality because it assumes no transcription. It also makes use of the <a href='https://www.jyu.fi/hytk/fi/laitokset/mutku/en/research/projects2/past-projects/coe/materials/emotion/soundtracks/Index'>soundtrack360 dataset</a> as a high-quality audio database.
</p>
<iframe className="blog_contents" width="560" height="600" src="https://www.youtube.com/embed/K2Aent-pRnM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>

### Retrieval Result
<p> We report the results for IEMOCAP and Audioset, which are test datsets reported in the paper. The samples below were extracted based on the <a href='https://github.com/SeungHeonDoh/speech_to_music/blob/master/notebook/demo.ipynb'>code</a>.</p>

<script>
function pauseOthers(ele) {
    $("audio").not(ele).each(function (index, audio) {audio.pause();});
}
</script>

<style>
.main-content table {
    display: inline-table;
}
table {
    table-layout:fixed;
    width: 100%;
    overflow: hidden;
}
#player{
    width: 100%;
}
</style>


<table>
    <tr>
        <th>  </th>
        <th> Speech Query </th>
        <th> Similar Music 1 </th>
        <th> Similar Music 2 </th>
        <th> Similar Music 3 </th>
    </tr>
    <tr> 
        <th> angry </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/angry/angry.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/angry/angry (1).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/angry/angry (2).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/angry/angry (3).wav" type="audio/mpeg"></audio> </th>
    </tr>
    <tr> 
        <th> happy </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/happy/happy.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/happy/happy (1).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/happy/happy (2).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/happy/happy (3).wav" type="audio/mpeg"></audio> </th>
    </tr>
    <tr> 
        <th> sad </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/sad/sad.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/sad/sad (1).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/sad/sad (2).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/sad/sad (3).wav" type="audio/mpeg"></audio> </th>
    </tr>
    <tr> 
        <th> neutral </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/neutral/neutral.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/neutral/neutral (1).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/neutral/neutral (2).wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/neutral/neutral (3).wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>