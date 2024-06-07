<script>
export default {};

document.addEventListener("DOMContentLoaded", () => {
  const contents = document.querySelectorAll(".content");
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
      } else if (!entry.isIntersecting) {
        entry.target.classList.remove("visible");
      }
    });
  });

  contents.forEach((content) => observer.observe(content));
});
</script>

<template>
  <div class="box-wrapper d-flex flex-column align-items-center">
    <div class="content">
      <h1>Introduzione alla Produzione del Gelato</h1>
      <p>
        Il gelato è un dessert amato in tutto il mondo, noto per la sua
        cremosità e il suo sapore delizioso. Ma come viene prodotto esattamente?
        In questo articolo, esploreremo i vari passaggi coinvolti nella
        produzione del gelato.
      </p>
    </div>

    <div class="content">
      <h2>1. Selezione degli Ingredienti</h2>
      <p>
        Il primo passo nella produzione del gelato è la selezione degli
        ingredienti. Gli ingredienti principali includono latte, panna, zucchero
        e aromi. È importante scegliere ingredienti di alta qualità per
        garantire un prodotto finale gustoso.
      </p>
    </div>

    <div class="content">
      <h2>2. Miscelazione</h2>
      <p>
        Una volta selezionati, gli ingredienti vengono miscelati insieme. Questa
        fase è cruciale per garantire che lo zucchero si sciolga completamente e
        che gli ingredienti siano ben combinati. La miscela risultante è
        conosciuta come base del gelato.
      </p>
    </div>

    <div class="content">
      <h2>3. Pastorizzazione</h2>
      <p>
        La base del gelato viene poi pastorizzata, un processo che riscalda la
        miscela a una temperatura elevata per uccidere eventuali batteri nocivi.
        Questo processo garantisce che il gelato sia sicuro da consumare.
      </p>
    </div>

    <div class="content">
      <h2>4. Omogeneizzazione</h2>
      <p>
        Dopo la pastorizzazione, la miscela viene omogeneizzata per rompere i
        globuli di grasso e creare una consistenza più liscia. Questo processo
        aiuta anche a prevenire la formazione di cristalli di ghiaccio durante
        il congelamento.
      </p>
    </div>

    <div class="content">
      <h2>5. Congelamento e Mantecazione</h2>
      <p>
        La miscela viene quindi congelata e mantecata. Durante questo processo,
        aria viene incorporata nella miscela per darle la sua consistenza
        soffice e cremosa. Il gelato viene raffreddato rapidamente per prevenire
        la formazione di grandi cristalli di ghiaccio.
      </p>
    </div>

    <div class="content">
      <h2>6. Confezionamento e Indurimento</h2>
      <p>
        Infine, il gelato viene confezionato e sottoposto a un processo di
        indurimento, dove viene portato a temperature ancora più basse per
        stabilizzarne la struttura. Il gelato è ora pronto per essere
        distribuito e gustato dai consumatori.
      </p>
    </div>
  </div>
</template>

<style scoped lang="scss">
@keyframes appear {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.box-wrapper {
  font-family: Arial, sans-serif;
  background: url("https://images.pexels.com/photos/3970396/pexels-photo-3970396.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500")
    no-repeat center center fixed;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 20px;
}

.content {
  opacity: 0; /* Start hidden */
  transition: opacity 0.5s, transform 0.5s; /* Smooth transition for appearance */
  margin: 20px;
  padding: 20px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 15px;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  color: #fff;
}

.content h1,
.content h2,
.content p {
  margin: 0 0 10px;
}

.content.visible {
  opacity: 1; /* Become visible */
  animation: appear 0.5s linear; /* Apply the animation */
}
</style>
