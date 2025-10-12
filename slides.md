# Javascript fait du bruit (mais en rythme)

## Tremplin de Snowcamp

neo speaker : Baptiste Lyet

coach : Sylvain Coudert

---

# Plan

- Intro
   - Musique et rythme
   - Séquenceurs et boites à rythmes
- Création d'un séquenceur en JavaScript
  - Utilisation du timing JavaScript
  - Utilisation de la WebAudioAPI et de la synchronisation d'horloges
- Conclusion

---

# Intro : musique et rythme

### Qu'est ce que la musique ?

La musique est un art et une activité culturelle consistant à **combiner sons et silences au cours du temps**.

Les paramètres principaux sont le **rythme** (façon de combiner les sons dans le temps), la hauteur (combinaison dans les fréquences), les nuances et le timbre.

### Qu'est ce que le rythme ?

Le rythme en musique est l'organisation dans le temps des événements musicaux.

<!--
Définitions de wikipedia
https://fr.wikipedia.org/wiki/Rythme_(musique)
https://fr.wikipedia.org/wiki/Musique
-->

---

#  Intro : Musique électronique : séquenceurs et boites à rythmes

Image orgue de barbarie

Rythme encore créé par un.e humain mais on voit les motifs apparaitres

Image séquenceur

Image guitar hero

Image logiciel de musique

<!-- https://upload.wikimedia.org/wikipedia/commons/thumb/7/71/Orgue_de_barbarie.jpg/2880px-Orgue_de_barbarie.jpg -->

---

# Construction d'une boite à rythme simpliste : setTimeout()

## Code
```ts
const pattern: string[] = ["X"," "," "," ","X"," "," "," ","X"," "," "," ","X"," "," "," "];
const audio: HTMLAudioElement = new Audio("kick.wav");

const bpm: number = 120;
const stepTime: number = (60 / bpm) / 4 * 1000; // duration of a 16th note in ms

let step: number = 0;

(function loop(): void {
  if (pattern[step] === "X") {
    audio.currentTime = 0;
    audio.play();
  }

  step = (step + 1) % pattern.length;
  setTimeout(loop, stepTime);
})();
```

---

# Construction d'une boite à rythme simpliste : setTimeout()

## Démonstration

---

# Construction d'une boite à rythme simpliste : setTimeout()

## Inconvénients
- Précision à la milliseconde
- Horloge JavaScript
  - Thread UI
  - Garbage collector





