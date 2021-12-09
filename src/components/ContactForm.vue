<template>
  <div class="contact-form">
    <div class="contact-form__form">
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
          type="text"
          name="message"
          placeholder="Your Message"
          v-model="form.message"
        />

        <button @click="submit_form" class="contact-form__message-submit">
          Submit
        </button>
      </div>
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
  padding: 1em;
}

.contact-form__form {
  display: grid;
  width: 28vw;
  background: lightgrey;
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

.contact-form__message input {
  height: 100px;
}

.contact-form__message input ::placeholder {
  position: absolute;
}

.contact-form__message-submit {
  margin-top: 10px;
}
</style>