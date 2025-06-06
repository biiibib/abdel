<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Générateur IA</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 800px; margin: 0 auto; padding: 20px; }
    .tab { margin-bottom: 20px; }
    button { padding: 10px 15px; cursor: pointer; }
    textarea { width: 100%; height: 100px; margin: 10px 0; }
    #result { margin-top: 20px; }
    #result img { max-width: 100%; border: 1px solid #ddd; }
  </style>
</head>
<body>
  <h1>Générateur IA Créatif</h1>
  
  <div class="tab-buttons">
    <button onclick="showTab('image')">Générer une Image</button>
    <button onclick="showTab('video')">Créer une Vidéo</button>
  </div>

  <!-- Tab Image -->
  <div id="image-tab" class="tab">
    <h2>Génération d'Image</h2>
    <textarea id="image-prompt" placeholder="Décrivez l'image..."></textarea>
    <select id="image-style">
      <option value="realistic">Style Réaliste</option>
      <option value="anime">Style Anime</option>
    </select>
    <button onclick="generateImage()">Générer</button>
    <div id="image-result" class="result"></div>
  </div>

  <!-- Tab Vidéo -->
  <div id="video-tab" class="tab" style="display:none;">
    <h2>Génération de Vidéo</h2>
    <textarea id="video-prompt" placeholder="Décrivez la vidéo..."></textarea>
    <button onclick="generateVideo()">Créer</button>
    <div id="video-result" class="result"></div>
  </div>

  <script>
    // Fonctions basiques (à remplacer par de vraies APIs)
    function showTab(tabName) {
      document.getElementById('image-tab').style.display = 'none';
      document.getElementById('video-tab').style.display = 'none';
      document.getElementById(`${tabName}-tab`).style.display = 'block';
    }

    async function generateImage() {
      const prompt = document.getElementById('image-prompt').value;
      const style = document.getElementById('image-style').value;
      
      // Simulation d'appel API (remplacez par un vrai appel)
      document.getElementById('image-result').innerHTML = 
        `<p>Génération en cours... (Simulation avec: "${prompt}", style: ${style})</p>`;
      
      // Exemple avec une image placeholder
      setTimeout(() => {
        document.getElementById('image-result').innerHTML = `
          <img src="https://via.placeholder.com/1024x1024/cccccc/000000?text=${encodeURIComponent(prompt)}" 
               alt="Résultat IA">
          <p>Prompt: ${prompt} | Style: ${style}</p>
        `;
      }, 1500);
    }

    function generateVideo() {
      const prompt = document.getElementById('video-prompt').value;
      document.getElementById('video-result').innerHTML = 
        `<p>Génération vidéo en cours... (Simulation avec: "${prompt}")</p>`;
      
      setTimeout(() => {
        document.getElementById('video-result').innerHTML = `
          <video controls width="100%">
            <source src="https://samplelib.com/lib/preview/mp4/sample-5s.mp4" type="video/mp4">
          </video>
          <p>Prompt: ${prompt}</p>
        `;
      }, 2000);
    }
  </script>
</body>
</html>
