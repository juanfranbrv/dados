<script>
  let dadoIzquierda = "./img/dice1.png";
  let dadoDerecha = "./img/dice2.png";
  let numero1 = 1;
  let numero2 = 2;

  function tirarDados() {
    for (let j = 0; j <= 10; j++) {
      numero1 = Math.floor(Math.random() * 6) + 1;
      numero2 = Math.trunc(Math.random() * 6) + 1;
      console.log(numero1, numero2);
      dadoIzquierda = "./img/dice" + numero1 + ".png";
      dadoDerecha = `./img/dice${numero2}.png`;
    }
  }
</script>

<main>
  <div class="jumbotron text-center">
    <button class="btn btn-success btn-lg" on:click={tirarDados}
      >Tirar dados</button
    >
    <br />
    <img src={dadoIzquierda} alt="" class="img" />
    <img src={dadoDerecha} alt="" class="img" />
    {#if numero1 == numero2}
      <h1>
        <span class="badge bg-success">Ganaste</span>
      </h1>
    {/if}
  </div>
</main>

<style>
  .jumbotron {
    padding: 2rem 1rem;
    margin-bottom: 2rem;
    background-color: #e9ecef;
    border-radius: 0.3rem;
  }

  .img {
    max-width: 300px;
    max-height: 300;
    background-color: red;
    border-radius: 20px;
    margin: 30px;
  }
</style>
