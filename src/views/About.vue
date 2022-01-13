<template>
  <div class="about">
    <h1>Objetivo deste projeto</h1>
    <p>
      Pretendo desenvolver algo como um blog, que poderá vir a servir como um
      portfólio. Quero ir implementando aos poucos e postando sobre como está
      sendo o desenvolvimento do sistema ou sobre que reflexões tenho me
      debruçado. Será uma plataforma onde eu poderei contar ao mundo quem é o
      Caio, como pessoa e como profissional.
    </p>
    <p>
      Pretendo utilizar de ferramentas e estratégias de desenvolvimentos Agile
      durante os trabalhos, como forma de me familiarizar com esse universo, e
      espero aperfeiçoar meu repertório de programação, internalizando a
      preocupação com as diversas boas práticas.
    </p>
    <h1>Sobre mim</h1>
    <div class="profile">
      <img alt="My photo" src="../assets/profile-pic.png" class="my-photo" />
      <ul class="enum-about-me">
        <li>Nome: Caio Henrique</li>
        <li>Idade: {{ myAge }} anos</li>
        <li>Titulação: Tecnólogo em Sistemas de Computação pela UFF</li>
        <li>
          Hobbies: Jogar vídeogame, ler, assistir animes, fazer trilhas, raves,
          jardinagem e ver meus gatos brincando.
        </li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>
function differenceBetweenTwoDatesInYears(oldestDate, newestDate) {
  let years = newestDate.getFullYear() - oldestDate.getFullYear();

  let monthNotPassed = oldestDate.getMonth() > newestDate.getMonth();

  let monthIsNow = oldestDate.getMonth() == newestDate.getMonth();

  let dayNotPassed = oldestDate.getDay() > newestDate.getDay();

  if (monthNotPassed || (monthIsNow && dayNotPassed)) {
    years--;
  }

  return years;
}

export default {
  name: "About",
  components: {},
  computed: {
    myAge: function () {
      const birthDay = new Date(1993, 8, 14);

      let today = new Date();

      return differenceBetweenTwoDatesInYears(birthDay, today);
    },
  },
};
</script>

<style scoped>
.about {
  text-align: justify;
}
.profile {
  display: flex;
}

.my-photo {
  width: 200px;
  height: auto;
}

.enum-about-me {
  list-style: none;
}
</style>