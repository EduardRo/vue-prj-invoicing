<template>
  <div>
    <input v-model="name" type="text" placeholder="Enter your name" />
    <p>Hello, {{ name }}!</p>

    <label for="email">Email:</label>
    <input v-model="email" type="email" id="email" />

    <label for="age">Age:</label>
    <input v-model.number="age" type="number" id="age" />

    <label for="gender">Gender:</label>
    <select v-model="gender" id="gender">
      <option value="male">Male</option>
      <option value="female">Female</option>
      <option value="other">Other</option>
    </select>

    <label>Interests:</label>
    <div v-for="interest in interests" :key="interest.id">
      <input
        type="checkbox"
        v-bind:id="interest.id"
        v-bind:value="interest.name"
        v-model="selectedInterests"
      />
      <label :for="interest.id">{{ interest.name }}</label>
    </div>

    <button v-on:click="submitForm">Submit</button>

    <div>{{ name }} {{ email }} {{ age }} {{ gender }}</div>
    <div v-for="interest in interests" v-bind:key="interest.id">
      <li>{{ interest.name }}</li>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      age: 0,
      gender: "",
      interests: [
        { id: 1, name: "Sports" },
        { id: 2, name: "Music" },
        { id: 3, name: "Art" },
      ],
      selectedInterests: [],
    };
  },
  methods: {
    submitForm() {
      // Process form data or send it to the server
      console.log("Form submitted!");
      console.log("Name:", this.name);
      console.log("Email:", this.email);
      console.log("Age:", this.age);
      console.log("Gender:", this.gender);
      console.log("Interests:", this.selectedInterests);
    },
  },
};
</script>
