<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button v-on:click="alert1()">First Alert</button>
    <button v-on:click="alert2()">Get a greeting</button>
    <button v-on:click="alert3()">True or false</button>
    <button v-on:click="alert4()">Try this</button>
  </div>
</template>

<script>
import swal from "sweetalert";
export default {
  mounted: function () {
    swal("A wild Pikachu appeared! What do you want to do?", {
      buttons: {
        cancel: "Run away!",
        catch: {
          text: "Throw Pokéball!",
          value: "catch",
        },
        defeat: true,
      },
    }).then((value) => {
      switch (value) {
        case "defeat":
          swal("Pikachu fainted! You gained 500 XP!");
          break;

        case "catch":
          swal("Gotcha!", "Pikachu was caught!", "success");
          break;

        default:
          swal("Got away safely!");
      }
    });
  },
  methods: {
    alert1: function () {
      swal("You should have a nice day");
    },
    alert2: function () {
      swal("How is your day going?", {
        buttons: ["Not bad!", "Could be better"],
      });
    },
    alert3: function () {
      swal("A cat has 9 lives", {
        buttons: [true, true],
      });
    },
    alert4: function () {
      swal("Write something here:", {
        content: "input",
      }).then((value) => {
        swal(`You typed: ${value}`);
      });
    },
  },
};
</script>
