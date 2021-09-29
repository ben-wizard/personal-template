<template>
  <div class="home">
    <div class="text-center mb-4">
      <h1 id="welcome"></h1>
      <h3 class="uppercase" id="dev"></h3>
    </div>

    <div id="who-div" class="d-none m-2 border-dotted-block quaternary">
      <h2 id="who-title" class="tertiary">Who I am?</h2>
      <p id="who"></p>
    </div>
    <div id="contact-me-div" class="d-none m-2 border-dotted-block quaternary">
      <h2 id="contact-title" class="tertiary">Do you want to contact?</h2>
      <p id="contact"></p>
    </div>
  </div>
</template>

<script>
import Typewriter from "typewriter-effect/dist/core";

export default {
  name: "Home",
  async mounted() {
    new Typewriter("#welcome", {
      loop: false,
      delay: 25,
    })
      .typeString('Hey Selam, Ben <span class="quaternary">Wizard</span>!')
          .callFunction(() => {
            document
              .getElementById("who-div")
              .style.setProperty("display", "block", "important");

            new Typewriter("#who-title", {
              loop: false,
              delay: 25,
            })
              .typeString("Ben Kimim ?")
              .callFunction(() => {
                new Typewriter("#who", {
                  loop: false,
                  delay: 25,
                })
                  .typeString(
                    'Ben <span class="green">Mustafa</span>. 16 yaşındayım kendi çapımda projeler yapıp, Github hesabımda paylaşıyorum. Bildiğim yazılım dilleri; <span class="green">PHP</span>, <span class="green">MySQL</span>, <span class="green">Javascript</span>, <span class="green">HTML</span>, <span class="green">CSS</span>. Yakın bir zamanda <span class="green">Typescript</span> ve <span class="green">Python</span> öğrenmeye başlamayı düşünüyorum.'
                  )
                  .callFunction(() => {
                    document
                      .getElementById("contact-me-div")
                      .style.setProperty("display", "block", "important");

                    new Typewriter("#contact-title", {
                      loop: false,
                      delay: 25,
                    })
                      .typeString("Nasıl Ulaşabilirim?")
                      .callFunction(() => {
                        new Typewriter("#contact", {
                          loop: false,
                          delay: 25,
                        })
                          .typeString(
                            `Benimle iletşim kurmak için <span class="green">Discord</span>'a veya <span class="green">Instagram</span>'a tıklayabilirsin.`
                          )
                          .start();
                  })
                  .start();
              })
              .start();
          })
          .start();
      })
      .start();
  },
};
</script>
