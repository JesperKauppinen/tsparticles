[![banner](https://particles.js.org/images/banner3.png)](https://particles.js.org)

# jquery-particles

[![npm](https://img.shields.io/npm/v/jquery-particles)](https://www.npmjs.com/package/jquery-particles) [![npm](https://img.shields.io/npm/dm/jquery-particles)](https://www.npmjs.com/package/jquery-particles) [![GitHub Sponsors](https://img.shields.io/github/sponsors/matteobruni)](https://github.com/sponsors/matteobruni)

Virallinen [tsParticles](https://github.com/matteobruni/tsparticles) jQuery lisäosa

[![Slack](https://particles.js.org/images/slack.png)](https://join.slack.com/t/tsparticles/shared_invite/enQtOTcxNTQxNjQ4NzkxLWE2MTZhZWExMWRmOWI5MTMxNjczOGE1Yjk0MjViYjdkYTUzODM3OTc5MGQ5MjFlODc4MzE0N2Q1OWQxZDc1YzI) [![Discord](https://particles.js.org/images/discord.png)](https://discord.gg/hACwv45Hme) [![Telegram](https://particles.js.org/images/telegram.png)](https://t.me/tsparticles)

[![tsParticles Product Hunt](https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=186113&theme=light)](https://www.producthunt.com/posts/tsparticles?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-tsparticles") <a href="https://www.buymeacoffee.com/matteobruni"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a beer&emoji=🍺&slug=matteobruni&button_colour=5F7FFF&font_colour=ffffff&font_family=Arial&outline_colour=000000&coffee_colour=FFDD00"></a>

## Asennus

```shell
$ npm install jquery-particles
```

tai

```shell
$ yarn add jquery-particles
```

tai jsDelivr:n kautta

[![jsDelivr](https://data.jsdelivr.com/v1/package/npm/jquery-particles/badge)](https://www.jsdelivr.com/package/npm/jquery-particles)

```html
<!-- lisää ensimmäiseksi tsParticles moottori -->
<script src="https://cdn.jsdelivr.net/npm/tsparticles-engine"></script>

<!-- sitten lisää tarvittavat tsParticles lisäosat -->
<script src="https://cdn.jsdelivr.net/npm/tsparticles/tsparticles.bundle.min.js"></script>

<!-- lopuksi lisää jquery wrapper -->
<script src="https://cdn.jsdelivr.net/npm/jquery-particles"></script>
```

## Käyttöohjeet

HTML

```html
<div id="tsparticles"></div>
```

```javascript
// tämä lataa tsparticles paketin ja on helpoin tapa saada kaikki valmiiksi
// alkaen versiosta 2 voit lisätä vain tarvitsemasi ominaisuudet ja vähentää paketin kokoa
$(document).ready(async function () {
  await loadFull(tsParticles);

  $("#tsparticles")
    .particles()
    .init(
      {
        background: {
          color: {
            value: "#0d47a1",
          },
        },
        fpsLimit: 120,
        interactivity: {
          events: {
            onClick: {
              enable: true,
              mode: "push",
            },
            onHover: {
              enable: true,
              mode: "repulse",
            },
            resize: true,
          },
          modes: {
            push: {
              quantity: 4,
            },
            repulse: {
              distance: 200,
              duration: 0.4,
            },
          },
        },
        particles: {
          color: {
            value: "#ffffff",
          },
          links: {
            color: "#ffffff",
            distance: 150,
            enable: true,
            opacity: 0.5,
            width: 1,
          },
          collisions: {
            enable: true,
          },
          move: {
            direction: "none",
            enable: true,
            outModes: {
              default: "bounce",
            },
            random: false,
            speed: 6,
            straight: false,
          },
          number: {
            density: {
              enable: true,
              area: 800,
            },
            value: 80,
          },
          opacity: {
            value: 0.5,
          },
          shape: {
            type: "circle",
          },
          size: {
            value: { min: 1, max: 5 },
          },
        },
        detectRetina: true,
      },
      function (container) {
        // säiliö on partikkeli säiliö jossa play/pause tai stop/start.
        // säiliö on jo käynnissä, joten sinun ei tarvitse käynistää sitä manuaalisesti.
      }
    );

  // tai

  $("#tsparticles")
    .particles()
    .ajax("particles.json", function (container) {
        // säiliö on partikkeli säiliö jossa play/pause tai stop/start.
        // säiliö on jo käynnissä, joten sinun ei tarvitse käynistää sitä manuaalisesti.
    });
});
```

## Demot

Demo verkkosivu löytyy [täältä](https://particles.js.org)

<https://particles.js.org>

Aktiivisesti ylläpidetty ja päivitetty CodePen kokoelma löytyy [täältä](https://codepen.io/collection/DPOage)

<https://codepen.io/collection/DPOage>
