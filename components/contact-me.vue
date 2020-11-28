<template>
  <div class="contact-me-wrapper">
    <div v-if="!emailSentSuccessfully" class="contact-me-body">
      <div data-aos="fade-left"
           data-aos-offset="100"
           data-aos-delay="50"
           data-aos-duration="1000"
           data-aos-once="true"
           data-aos-easing="ease-in-out"
           class="contact-me-title">
        <div>Contact me</div>
        <div class="contact-me-title-text">Feel free to message me using the form<br> below or the following contact
          info:
        </div>
        <div class="contact-me-title-text"><a target="_blank" href="mailto:mphunter4@gmail.com">mphunter4@gmail.com</a>
        </div>
        <div class="contact-me-title-text"><a href="tel:6142960696">614-296-0696</a></div>

      </div>
      <div class="email-fields-wrapper">
        <div class="form__group field">
          <input type="input" v-model="userName" class="form__field" placeholder="Name" name="name" id='name' required/>
          <label for="name" class="form__label">Name</label>
        </div>
        <div class="form__group field">
          <input type="input" v-model="userEmail"
                 class="form__field"
                 placeholder="Email"
                 name="email"
                 id='email'
                 required/>
          <label for="email" class="form__label">Email</label>
        </div>

        <textarea class="message-section"
                  v-model="message"
                  placeholder="Message">
        </textarea>
        <button data-aos="fade-up"
                data-aos-offset="100"
                data-aos-delay="50"
                data-aos-duration="1000"
                data-aos-once="true"
                data-aos-easing="ease-in-out" class="sendEmailButton" @click="sendEmail">SEND
        </button>
        <div v-show="displayErrorMessageWrapper" class="errorMessageWrapper">{{ errorMessage }}</div>
      </div>
      <div></div>
    </div>
    <div v-else class="thank-you-message-wrapper">
      <div class="thank-you-message">Thanks for the message!</div>
    </div>

  </div>
</template>

<script>
import emailjs from 'emailjs-com/dist/email.js'

export default {
  name: 'contact-me',
  data () {
    return {
      userName: '',
      userEmail: '',
      message: '',
      serviceId: 'service_t6d6162',
      templateId: 'template_i8nl2jw',
      errorMessage: '',
      emailSending: false,
      emailSentSuccessfully: false,
    }
  },
  computed: {
    displayErrorMessageWrapper () {
      return this.errorMessage !== ''
    },
  },
  methods: {
    async sendEmail () {
      if (this.userName === '' || this.message === '' || this.userEmail === '') {
        this.showErrorMessage()
      } else {
        this.emailSending = true
        try {
          const { status, text } = await emailjs.send(this.serviceId, this.templateId, {
            from_name: this.userName,
            message: this.message,
            to_name: 'Max',
            reply_to: this.userEmail,
          })
          if (status === 200) {
            this.emailSentSuccessfully = true
          }
        } catch (e) {
          debugger;
          this.showErrorMessage('Something went wrong. Your message could not be sent.')
        }
        this.emailSending = false
      }
    },
    showErrorMessage (message = '') {
      if (message !== '') {
        this.errorMessage = message
      } else {
        this.errorMessage = ''
        if (this.userName === '') {
          this.errorMessage += 'Please enter your name.'
        } else if (this.userEmail === '') {
          this.errorMessage += ' Please enter an email.'
        } else if (this.message === '') {
          this.errorMessage += ' Please enter a message.'
        }
      }

    },
  },
}
</script>

<style scoped>

textarea.contact-me-text-wrapper {
  height: 100%;
}

.contact-me-title-text {
  font-size: .35em;
  font-weight: 400;
  text-align: center;
}

.contact-me-title-text a {
  color: white;
  text-decoration: none;
  color: #D35074;
}

.thank-you-message {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
  font-size: 3em;
  font-weight: 700;
  height: 100%;
}

.errorMessageWrapper {
  background: #D60000;;
  color: white;
  padding: .3em;
  padding-left: .5em;
}

.sendEmailButton {
  border: 2px solid white;
  background-color: Transparent;
  color: white;
  cursor: pointer;
  padding-top: .3em;
  padding-bottom: .3em;
  width: 10em;
  justify-self: flex-end;
}

input, textarea {
  border-radius: .1em;
  border: none;
  font-size: 1em;
  font-family: "Fira Sans", sans-serif;
}

input:focus, textarea:focus, button:focus {
  outline: none;
}

.contact-me-title {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  font-size: 3em;
  font-weight: 600;
  color: white;
  margin-top: 1em;
}

.contact-me-body {
  display: grid;
  grid-template-columns:1fr;
  grid-template-rows:1.5fr 2fr .5fr;
  height: 100%;
}

.email-fields-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: .7fr .7fr 3fr .7fr;
  width: 30em;
  justify-self: center;
  grid-gap: .4em;
}

.contact-me-wrapper {
  font-family: "Fira Sans", sans-serif;
  height: 40em;
  width: 100%;
  background-color: #2c2540;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.form__group {
  position: relative;
  padding: 15px 0 0;
  width: 100%;
}

.form__field {
  font-family: inherit;
  width: 100%;
  border: 0;
  border-bottom: 2px solid #9b9b9b;
  outline: 0;
  font-size: 1.3rem;
  color: #fff;
  padding: 7px 0;
  background: transparent;
  transition: border-color 0.2s;
}

.message-section {
  background-color: white;
  color: #D35074;
  padding: .5em;
  margin-top: .5em;
  margin-bottom: .5em;
}

.form__field::placeholder {
  color: transparent;
}

.form__field:placeholder-shown ~ .form__label {
  font-size: 1.3rem;
  cursor: text;
  top: 20px;
}

.form__label {
  position: absolute;
  top: 0;
  display: block;
  transition: 0.5s;
  font-size: 1rem;
  color: #9b9b9b;
}

.form__field:focus {
  padding-bottom: 6px;
  font-weight: 700;
  border-width: 3px;
  border-image: linear-gradient(to right, #D35074, #A31B5E);
  -moz-border-image: linear-gradient(to right, #D35074, #A31B5E);
  -webkit-border-image: linear-gradient(to right, #D35074, #A31B5E);
  -o-border-image: linear-gradient(to right, #D35074, #A31B5E);
  border-image-slice: 1;
  -o-border-image-slice: 1;
}

.form__field:focus ~ .form__label {
  position: absolute;
  top: 0;
  display: block;
  transition: 0.2s;
  font-size: 1rem;
  color: #D35074;
  font-weight: 700;
}

/* reset input */
.form__field:required, .form__field:invalid {
  box-shadow: none;
}

/* demo */
/*body {*/
/*  font-family: 'Poppins', sans-serif;*/
/*  display: flex;*/
/*  flex-direction: column;*/
/*  justify-content: center;*/
/*  align-items: center;*/
/*  min-height: 100vh;*/
/*  font-size: 1.5rem;*/
/*  background-color: #222222;*/
/*}*/

@media screen and (max-width: 992px) {

  .email-fields-wrapper {
    width: 20em;
  }

}
</style>
