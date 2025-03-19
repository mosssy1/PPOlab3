<template>
  <div class="container">
    <header>
      <div class="header-content">
        <img class="profile-image" src="https://avatars.dzeninfra.ru/get-zen_doc/9278169/pub_641d5026a56f6a4d500857d1_641e385b7eb49d4e1823543a/scale_1200" alt="Фото" />
        <div class="header-info">
          <h1>{{ resume.name }}</h1>
          <p class="position">{{ resume.position }}</p>
          <div class="contacts">
            <p><strong>Телефон:</strong> {{ resume.contacts.phone }}</p>
            <p><strong>Электронная почта:</strong> <a :href="'mailto:' + resume.contacts.email">{{ resume.contacts.email }}</a></p>
          </div>
        </div>
      </div>
    </header>
    <section>
      <h2>Опыт работы</h2>
      <ul>
        <li v-for="job in resume.experience" :key="job.company">
          <strong>{{ job.company }}</strong> — {{ job.position }} ({{ job.years }})
        </li>
      </ul>
    </section>
  </div>
</template>

<script setup>
  const resume = {
    name: "Комиссарова Арина Григорьевна",
    position: " НЕ frontend-разработчик",
    experience: [
      { company: "Meta Network", position: "Frontend-разработчик", years: "2021-2025" },
      { company: "Ispring", position: "Дизайн-разработчик, стажёр", years: "2020-2021" }
    ],
    contacts: {
      phone: "+7 (900) 123-45-67",
      email: "arina@example.com",
    }
  };
</script>

<style scoped>
  .container {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background: rgba(246, 213, 229, 0.7);
    height: 100vh;
    text-align: center;
    font-family: 'Arial', sans-serif;
  }

  .header-content {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 30px;
  }

  .profile-image {
    border-radius: 50%;
    width: 150px;
    height: 150px;
    margin-right: 20px;
  }

  .header-info {
    text-align: left;
  }

  h1 {
    color:rgb(0, 0, 0);
    font-size: 2rem;
    margin: 0;
  }

  .position {
    font-size: 1.2rem;
    color: #555;
    margin-top: 5px;
  }

  .contacts {
    margin-top: 15px;
    font-size: 1rem;
  }

  .contacts a {
    color:rgb(0, 0, 0);
    text-decoration: none;
  }

  .contacts a:hover {
    text-decoration: underline;
  }

  section {
    margin-top: 40px;
  }

  h2 {
    font-size: 1.6rem;
    color: #333;
  }

  ul {
    list-style: none;
    padding: 0;
  }

  li {
    font-size: 1.1rem;
    color: #555;
    margin-bottom: 10px;
  }

  li strong {
    color: #333;
  }
</style>
