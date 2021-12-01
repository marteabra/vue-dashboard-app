<template>
  <div class="contact-form">
    <h3>Contact Us!</h3>

    <div class="contact-form__firstname">
      <label>First Name</label>
      <input
        type="text"
        name="firstname"
        placeholder="First Name"
        v-model="form.firstname"
      />
    </div>
    <div class="contact-form__lastname">
      <label>Last Name</label>
      <input
        type="text"
        name="lastname"
        placeholder="Last Name"
        v-model="form.lastame"
      />
    </div>
    <div class="contact-form__email">
      <label>Email</label>
      <input
        type="text"
        name="email"
        placeholder="Email"
        v-model="form.email"
      />
    </div>
    <div class="contact-form__message">
      <label>Message</label>
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

      methods: {
        submit_form() {
          alert(`Thank you for your message, ${this.firstname}!`);
        },
      },
    };
  },
};
</script>

<style>
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
  height: 30vh;
}

.contact-form__message--submit {
  margin-top: 10px;
}
</style>