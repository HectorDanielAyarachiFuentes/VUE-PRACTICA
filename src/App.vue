<template>
  <div id="cv">
    <header>
      <h1>{{ personalInfo.name }}</h1>
      <p>{{ personalInfo.title }}</p>
      <p>{{ personalInfo.address }}</p>
      <p>{{ personalInfo.email }}</p>
    </header>

    <section class="experience">
      <h2>Experiencia Laboral</h2>
      <ul>
        <li v-for="job in experience" :key="job.id">
          <h3>{{ job.position }}</h3>
          <p>{{ job.company }}, {{ job.year }}</p>
          <p>{{ job.description }}</p>
        </li>
      </ul>
    </section>

    <section class="education">
      <h2>Educación</h2>
      <ul>
        <li v-for="edu in education" :key="edu.id">
          <h3>{{ edu.degree }}</h3>
          <p>{{ edu.school }}, {{ edu.year }}</p>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      personalInfo: {
        name: 'Tu Nombre',
        title: 'Desarrollador Web',
        address: 'Tu Dirección',
        email: 'tu@email.com'
      },
      experience: [
        {
          id: 1,
          position: 'Desarrollador Web',
          company: 'Empresa ABC',
          year: '2022-2024',
          description: 'Trabajé en...'
        },
        // Más experiencias laborales aquí
      ],
      education: [
        {
          id: 1,
          degree: 'Licenciatura en Informática',
          school: 'Universidad XYZ',
          year: '2018-2022'
        },
        // Más información educativa aquí
      ]
    };
  }
};
</script>

<style scoped>
#cv {
  font-family: 'Arial', sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f3f4f6;
}

header {
  text-align: center;
  margin-bottom: 40px;
}

h1 {
  font-size: 32px;
  margin-bottom: 8px;
}

p {
  margin: 4px 0;
}

.experience,
.education {
  margin-bottom: 40px;
}

h2 {
  color: #333;
  font-size: 24px;
  margin-bottom: 16px;
}

ul {
  padding: 0;
}

li {
  margin-bottom: 20px;
}

h3 {
  color: #555;
  font-size: 20px;
  margin-bottom: 8px;
}

p {
  color: #666;
  margin: 4px 0;
}
</style>
