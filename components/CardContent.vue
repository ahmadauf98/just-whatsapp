<template>
  <div>
    <b-alert
      class="my-sm-0 my-md-4 mx-md-4 mx-lg-5 py-3"
      variant="warning"
      show
      dismissible
    >
      Important: If you do not have Whatsapp Application, please download it
      first.
      <a
        href="https://www.whatsapp.com/download"
        target="_blank"
        rel="noopener"
      >
        Download here</a
      >.
    </b-alert>
    <b-card
      class="card my-sm-0 my-md-4 mx-md-4 mx-lg-5 py-3"
      text-variant="#00473e"
    >
      <b-container fluid="lg">
        <b-row>
          <div
            class="Left mx-auto my-auto col-xs-12 col-lg-6 d-flex justify-content-center"
          >
            <img class="Picture mb-4" src="~/static/pic.svg" alt="Picture" />
          </div>
          <div
            class="mx-auto my-auto col-xs-12 col-lg-6 d-flex justify-content-center justify-content-lg-start"
          >
            <b-row>
              <b-form @submit="onSubmit">
                <b-form-group>
                  <label
                    >Country Code
                    <b-badge variant="warning">{{
                      form.codeNumber
                    }}</b-badge></label
                  >
                  <b-form-select
                    v-model="form.codeNumber"
                    :options="codes"
                    width="500px"
                    required
                  ></b-form-select>
                </b-form-group>

                <b-form-group>
                  <label
                    >Phone Number
                    <b-badge variant="warning">{{
                      form.numberPhone
                    }}</b-badge></label
                  >
                  <b-form-input
                    v-model="form.numberPhone"
                    required
                    placeholder="1160491143"
                  ></b-form-input>
                </b-form-group>

                <b-button class="btn-submit" block size="md" type="submit"
                  ><BIconCursorFill /> Chat now</b-button
                >
              </b-form>
            </b-row>
          </div>
        </b-row>
      </b-container>
    </b-card>

    <b-card
      class="card my-sm-0 my-md-4 mx-md-4 mx-lg-5 py-3"
      text-variant="#00473e"
    >
      <h5 class="font-weight-bold text-uppercase text-center">
        <BIconInfoCircleFill /> How to add to homescreen
      </h5>
      <b-card-group deck class="mt-4">
        <b-card
          text-variant="white"
          header="Step 1"
          class="card-alternate-1 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Open your browser, preferable chrome browser on Android devices,
            and safari browser on iPhone/iPad devices.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 2"
          class="card-alternate-2 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Go to
            <a
              class="hyperlink"
              href="https://just-whatsapp.web.app"
              target="_blank"
              rel="noopener"
            >
              just-whatsapp.web.app</a
            >
            and make sure all content is perfectly loaded on the
            browser.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 3"
          class="card-alternate-1 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Open <BIconThreeDotsVertical /> on the top-right side of the chrome
            browser and <BIconBoxArrowUp /> the bottom center of the safari
            browser.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 4"
          class="card-alternate-2 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Find and select 'Add to home screen' and all set. Good
            luck!</b-card-text
          >
        </b-card>
      </b-card-group>
    </b-card>

    <b-card
      class="card my-sm-0 my-md-4 mx-md-4 mx-lg-5 py-3"
      text-variant="#00473e"
    >
      <blockquote class="card-blockquote text-uppercase mt-3">
        <h6 class="font-weight-bold">
          {{ Info }}
        </h6>
        <footer>
          <small
            ><cite>{{ Dev }}</cite>
          </small>
        </footer>
      </blockquote>
    </b-card>
  </div>
</template>

<script>
import {
  BIconCursorFill,
  BIconInfoCircleFill,
  BIconThreeDotsVertical,
  BIconBoxArrowUp,
} from 'bootstrap-vue'
import CountryCode from '~/static/CountryCode.json'

export default {
  components: {
    BIconCursorFill,
    BIconInfoCircleFill,
    BIconThreeDotsVertical,
    BIconBoxArrowUp,
  },
  data() {
    return {
      title: 'Just Whatsapp',
      Info:
        'A fast, quick approach to send text messages to Whatsapp directly without saving the phone number. It supports Progressive Web Application (PWA). It can be saved to the home screen using a chrome browser and safari browser.',
      Dev: '- Just Whatsapp Developer',
      form: {
        numberPhone: '',
        codeNumber: null,
      },
      codes: CountryCode.codes,
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'My custom description',
        },
      ],
    }
  },

  methods: {
    onSubmit(evt) {
      evt.preventDefault()
      var dialcode = this.form.codeNumber
      var phone = dialcode + this.form.numberPhone

      if (!isNaN(phone)) {
        this.progress = true
        window.location = 'whatsapp://send?text=' + '&phone=' + phone
      } else {
        alert('Please enter a valid phone number.')
      }
      return false
    },
  },
}
</script>

<style scoped>
.card {
  background-color: #f2f7f5;
}

.card-alternate-1 {
  background-color: #00473e;
}

.card-alternate-2 {
  background-color: #faae2b;
}

.btn-submit {
  background-color: #00473e;
  font-weight: bold;
  border-style: none;
  margin-top: 12px;
}

.hyperlink {
  text-decoration: none;
  color: white;
}

.hyperlink:hover {
  color: #00473e;
  font-weight: 500;
}

/* Extra small devices (portrait phones, less than 576px) */
@media only screen and (max-width: 575px) {
  .Picture {
    height: 150px;
  }
}

/* Small devices (landscape phones, 576px and up) */
@media only screen and (min-width: 576px) and (max-width: 767.98px) {
  .Picture {
    height: 160px;
  }
}

/* Medium devices (tablets, 768px and up) */
@media only screen and (min-width: 768px) and (max-width: 991.98px) {
  .Picture {
    height: 170px;
  }
}

/* Large devices (desktops, 992px and up) */
@media only screen and (min-width: 992px) and (max-width: 1199.98px) {
  .Picture {
    height: 180px;
  }
}

/* Extra large devices (large desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {
  .Picture {
    height: 250px;
  }
}
</style>
