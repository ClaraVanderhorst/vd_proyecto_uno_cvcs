<!-- Script JS -->
<script>

import * as d3 from 'd3';

let numbers = [24,33,42,54,63,71,77,87,92,98]
let numbers2= [23,35,45,56,50,43,38,32,28,25]
let años= [2014,2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023]
let diferencia = [+1,-2,-3,-2,+13,+28,+49,+55,+62,+73]

let scale = d3.scaleRadial()
    .domain([0, d3.max(numbers)])
    .range([92, 392]);

let BarScale = d3.scaleLinear()
     .domain([d3.min(diferencia), d3.max(diferencia)])
     .range([-6, 146]);

</script>

<!-- Estructura contenido HTML -->

<div class="main_container">
  <div clasnps="header">
  <h1 class="title">antes de salir... <span class="highlight3">¿Te pusiste protector?</span></h1>
  <h2 class="subtitle">En los últimos diez años, Argentina ha registrado un alarmante aumento en los niveles de radiación ultravioleta (UV), superando incluso a otros países de Sudamérica como Brasil y Chile. El cambio climático, junto con la debilitación de la capa de ozono, ha intensificado este fenómeno.</h2>
</div>

<h3 class="circle_title"> El aumento significativo en <span class="highlight">Argentina</span> y la estabilidad relativa en <span class="highlight2">Sudamérica</span></h3>

<h4 class="dif_title">diferencia <br>(con respecto a Argentina)</h4>

<div class="chart_container">
  {#each numbers as number, i}
  <div class="row">
<div class="circle_container">
  <div class="mascara_circ" style="width: {scale(numbers[i])}px; height: {scale(numbers[i])}px;"></div>
  <div class="mascara_circ2" style="width: {scale(numbers2[i])}px; height: {scale(numbers2[i])}px;"></div>
  <p class="circle_number">{años[i]}</p>
</div>

<div class="bar_container">
  <div class="central_line"></div>
  <div class="bar_wrapper">
    <div class="bar" style="width: {Math.abs(BarScale(diferencia[i]))}px; background-color: {diferencia[i] < 0 ? 'green' : 'red'}; transform: translateX({diferencia[i] < 0 ? -Math.abs(BarScale(diferencia[i])) : 0}px);"></div>
  </div>
</div>
</div>
{/each}
</div>

<div class="image_section">
  <h3 class="image_title">El preocupante cambio de los últimos 10 años, en el índice UV en Argentina</h3>
  <div class="images_container">
    <div class="image_container">
      <iframe src='https://flo.uri.sh/visualisation/19371951/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19371951/?utm_source=embed&utm_campaign=visualisation/19371951' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div></div>
    <div class="image_container">
      <iframe src='https://flo.uri.sh/visualisation/19372132/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19372132/?utm_source=embed&utm_campaign=visualisation/19372132' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
    </div>
</div>
</div>
<h2 class="subtitle">Dentro del país, especialmente en las regiones del norte, se han visto un aumento significativo en el índice UV. Mientras que en Buenos Aires y Córdoba el crecimiento ha sido más moderado, aunque igualmente preocupante. La salud pública está en riesgo, con mayores posibilidades de enfermedades como el cáncer de piel debido a esta exposición creciente.</h2>
</div>

<div class="footer">
  <p>Visualización de Datos - S1</p>
  <p>Por Clara Van Der Horst Skou y María Clara Sisto</p>
</div>


<!-- Estilos CSS -->
<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,200..900;1,200..900&display=swap');

    .main_container {
    font-family: "Source Sans 3", sans-serif;
    text-align: center;
    padding: 20px;
  }

  .title {
    font-size: 60px;
    margin: 0;
    padding: 10px 0;
    color: rgb(94, 7, 7);
    font-weight: 200;
    margin-top: 40px;
    margin-bottom: 40px;
  }

  .highlight3 {
    font-weight: 600;
  }

  .subtitle {
    font-size: 18px;
    color: rgb(0, 0, 0);
    padding: 10px 345px;
    font-weight: 300;
    margin-bottom: 60px;
  }

    .highlight {
    color: #70150e; 
    font-weight: bold;
  }

  .highlight2 {
    color: #e7770f; 
    font-weight: bold;
  }

 

    .circle_title {
    font-size: 24px;
    margin-bottom: 60px;
    text-align: center;
    font-weight: 400;
  }

  .image_title {
    font-size: 24px;
    margin-top: 10px;
    margin-bottom: 30px;
    text-align: center;
    font-weight: 400;
  }

  .dif_title{
    font-size: 16px;
    text-align: center;
    padding-left: 400px;
    font-weight: 300;
  }

    .chart_container {
    display: flex;
    flex-direction: column;
    align-items: flex-start; 
    gap: 20px; 
    padding-left: 300px;
  }

    .circle_container {
    position: relative;
    width: 400px;
    height: 400px;
    background: white;
  }
  
  .mascara_circ,
	.mascara_circ2 {
    position: absolute;
		top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
    background-image: url("/images/vis.datos-03.svg");
    background-size: 300px; 
    background-position: center;
    background-repeat: no-repeat;
    border-radius: 50%; 
  }
	
	.mascara_circ2 {
    background-image: url("/images/vis.datos-04.svg");
  }

   .circle_number {
    font-size: 20px;
    color: black;
    font-weight: 600;
    text-align: center;
  }

  .image_section {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin-top: 60px;
  }

  .images_container {
    display: flex;
    justify-content: center; 
    gap: 200px; 
  }

  .image_container {
    flex: 1;
    width: 100%; 
    height: 100%;
    object-fit: contain;
  }

  .row {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    gap: 200px;
  }

  .bar_container {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.central_line {
  position: absolute;
  top: 0;
  left: 0;
  width: 2px;
  height: 100%;
  background-color: black;
}

.bar_wrapper {
  display: flex;
  align-items: center;
  height: 400px;
}

.bar {
  height: 20px;
  margin: 5px 0;
}

.footer {
  padding: 0px 50px; 
  text-align: left; 
  font-size: 16px; 
  font-weight: 300;
  color: #400101; 
  display: flex;
  flex-direction: row;
  gap: 790px;
}

</style>
