<script>
  async function allowDrop(e) {
    e.preventDefault();
  }
  async function drag(e) {
    e.dataTransfer.setData("text", e.target.id);
  }
  async function drop(e) {
    e.preventDefault();
    var data = e.dataTransfer.getData("text");
    e.target.appendChild(document.getElementById(data));

    // remove text from dropzone
    var x = document.getElementById("myDropText");
    x.remove();
  }
</script>

<div class="textBox">
  <p class="text" draggable="true" on:dragstart={drag} id="drag1">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas diam nisi,
    aliquam non pulvinar eu, porta non nibh. Maecenas feugiat venenatis
    efficitur. Nunc et purus et eros gravida hendrerit sed in felis. Etiam
    condimentum massa at sollicitudin finibus. Morbi lorem orci, molestie nec
    lacus a, pulvinar porttitor urna. Curabitur quis massa turpis. Pellentesque
    eu ultricies metus. Maecenas finibus ex ex, vitae interdum ante elementum
    in.
  </p>

  <p class="text" draggable="true" on:dragstart={drag} id="drag2">
    Nunc volutpat accumsan mi et varius. Cras nec auctor tellus. Sed in sapien
    turpis. Etiam ultricies, nunc ut pharetra volutpat, ligula purus maximus ex,
    lobortis eleifend ipsum ligula sit amet ipsum. Maecenas vitae erat
    tristique, tristique mauris non, faucibus nisi. Aenean finibus euismod lorem
    vitae bibendum. Cras et metus vitae eros finibus pharetra. Proin justo nisl,
    posuere sit amet fringilla in, posuere ut purus.
  </p>
  <p class="text" draggable="true" on:dragstart={drag} id="drag3">
    Aenean efficitur, elit vitae ultricies tincidunt, magna lectus facilisis
    sapien, quis pharetra arcu justo eget magna. Sed blandit purus dolor, quis
    laoreet arcu pulvinar sit amet. Maecenas et ullamcorper ex. Sed consequat
    ante non interdum sodales. Proin finibus, odio at consectetur iaculis, elit
    nisl pulvinar massa, ac euismod velit eros sit amet sem. In hac habitasse
    platea dictumst. Phasellus id leo ac diam finibus pharetra.
  </p>
</div>

<div class="dropZone" on:drop={drop} on:dragover={allowDrop}>
  <h4 class="dropText" id="myDropText">
    <p>Dropzone</p>
  </h4>
</div>
