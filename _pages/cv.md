<script src="https://mozilla.github.io/pdf.js/build/pdf.js"></script>
<div id="pdf-viewer" style="width:100%; height:100vh; overflow: hidden;"></div>
<script>
  var url = 'http://Umair-JMC.github.io/files/Umair_Academic_CV_August_24.pdf';

  var pdfjsLib = window['pdfjs-dist/build/pdf'];
  pdfjsLib.GlobalWorkerOptions.workerSrc = 'https://mozilla.github.io/pdf.js/build/pdf.worker.js';

  var loadingTask = pdfjsLib.getDocument(url);
  loadingTask.promise.then(function(pdf) {
    pdf.getPage(1).then(function(page) {
      var scale = 0.5; // Adjust scale to fit your needs
      var viewport = page.getViewport({ scale: scale });

      var canvas = document.createElement('canvas');
      var context = canvas.getContext('2d');
      canvas.height = viewport.height;
      canvas.width = viewport.width;

      document.getElementById('pdf-viewer').appendChild(canvas);

      var renderContext = {
        canvasContext: context,
        viewport: viewport
      };
      page.render(renderContext);
    });
  });
</script>
