<template>
  <div class="contact-form">
    <h3>Contact Us!</h3>

    <div class="contact-form__firstname">
      <input
        type="text"
        name="firstname"
        placeholder="First Name"
        v-model="form.firstname"
      />
    </div>
    <div class="contact-form__lastname">
      <input
        type="text"
        name="lastname"
        placeholder="Last Name"
        v-model="form.lastname"
      />
    </div>
    <div class="contact-form__email">
      <input
        type="text"
        name="email"
        placeholder="Email"
        v-model="form.email"
      />
    </div>
    <div class="contact-form__message">
      <input
        class="contact-form__message--textbox"
        type="text"
        name="message"
        placeholder="Your Message"
        v-model="form.message"
      />
      <button @click="submit_form" class="contact-form__message--submit">
        Submit
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        firstname: null,
        lastname: null,
        email: null,
        message: null,
      },
    };
  },

  methods: {
    submit_form() {
      alert(
        `Thank you for your message, ${this.form.firstname}. We will get back to you as soon as possible!`
      );
    },
  },
};
</script>

<style>
h3 {
  text-align: center;
}

.contact-form {
  margin-left: 1em;
  margin-top: 1em;
  width: 30vw;
}

.contact-form__form {
  display: grid;
}

.contact-form input {
  min-height: 25px;
}

.contact-form div {
  padding: 10px;
  display: grid;
}

.contact-form__message {
  display: flex;
  align-items: flex-end;
}
.contact-form__message--textbox {
  height: 28vh;
  position: relative;
}

/*.contact-form__message--textbox input[type="text"::placeholder] {
  position: absolute;
  height: 100%;
  top: 0;
}*/

.contact-form__message--submit {
  margin-top: 10px;
}
</style>