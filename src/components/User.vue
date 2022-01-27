<template>
  <b-card
    img-src="https://picsum.photos/1000/400?grayscale"
    class="card-profile mb-5"
  >
    <div class="card-profile-image">
      <b-img v-bind:src="userData.avatar" rounded="circle" thumbnail />
    </div>
    <b-card-body class="pt-2 pb-4 pl-4 pr-4">
      <div class="text-center">
        <span>User ID: {{ userData.id }}</span>
        <b-form-input @focus="$event.target.select()" class="custom-input" v-model="userData.first_name" placeholder="Enter your first name"></b-form-input>
        <b-form-input @focus="$event.target.select()" class="custom-input" v-model="userData.last_name" placeholder="Enter your last name"></b-form-input>
        <b-form-input @focus="$event.target.select()" class="custom-input" v-model="userData.email" placeholder="Enter your email"></b-form-input>
      </div>
    </b-card-body>
  </b-card>
</template>

<script>
export default {
  props: {
    userData: Object,
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.card-profile {
  border: 1px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.5rem;
  background: #ebebeb;
  box-shadow: none;
  transition: all 0.2s ease;
}
.card-profile:hover {
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}
.card-profile .card-profile-image img {
  min-height: 138px;
  max-width: 138px;
  min-height: 138px;
  max-width: 138px;
  object-fit: cover;
  transform: scale(1);
  transition: all 0.2s ease;
}
.card-profile:hover .card-profile-image img {
  transform: scale(0.9);
}
.card-profile img {
  max-width: 100%;
  border-radius: 0.5rem 0.5rem 0 0;
}
.card-profile-image {
  margin-top: -69px;
}
.custom-input {
  background: none;
  border: none;
  text-align: center;
}
.custom-input:hover {
  background: rgba(192, 192, 192, 0.2);
}
.custom-input:focus {
  background: white;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}
</style>
