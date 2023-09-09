<script lang="ts">
  import axios from "axios";
  var advice: string = "Click on the button below to get an advice";
  async function GET() {
    axios
      .get("https://api.adviceslip.com/advice")
      .then(function (response) {
        advice = response.data.slip.advice.toLowerCase();
      })
      .catch(function (error) {
        console.log(error);
      });
    return advice;
  }
</script>

<main>
  <h1 class="advice">{advice}</h1>
  <br /><br />
  <button type="button" on:click={GET}>Want advice ?</button>
  <p>Only one advice for life !</p>
</main>

<style>
  button:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .advice:hover {
    filter: drop-shadow(0 0 100rem #ff3e00aa);
  }
  h1 {
    text-decoration: wavy;
    font-family: cursive;
    font-size: xx-large;
  }
</style>
