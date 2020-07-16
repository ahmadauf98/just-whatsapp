<template>
  <div>
    <b-alert
      class="my-sm-0 my-md-4 mx-md-4 mx-lg-5 py-3"
      variant="warning"
      show
      dismissible
    >
      Important: If you are not using mobile devices, please download Whatsapp
      for Windows/Mac.
      <a href="https://www.whatsapp.com/download" target="_blank">
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
            class="Left mx-auto my-auto col-xs-12 col-lg-6 d-flex justify-content-center justify-content-lg-end"
          >
            <img class="Picture mb-4" src="~/static/pic.svg" alt="Picture" />
          </div>
          <div
            class="mx-auto my-auto col-xs-12 col-lg-6 d-flex justify-content-center justify-content-lg-start"
          >
            <b-row>
              <b-form @submit="onSubmit">
                <b-form-group label="Country Code:">
                  <!-- <b-form-select
                    v-model="form.codeNumber"
                    :options="codes"
                    width="500px"
                    required
                  ></b-form-select> -->
                  <b-form-input
                    list="input-list"
                    v-model="form.codeNumber"
                    placeholder="Select country code"
                  ></b-form-input>
                  <b-form-datalist
                    id="input-list"
                    :options="codes"
                    required
                  ></b-form-datalist>
                </b-form-group>

                <b-form-group label="Phone Number">
                  <b-form-input
                    v-model="form.numberPhone"
                    required
                    placeholder="Ex.1160491153"
                  ></b-form-input>
                </b-form-group>

                <b-button class="btn-submit" type="submit"
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
            >Open your browser, preferable chrome browser on android devices and
            safari browser on iphone/ipad devices.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 2"
          class="card-alternate-2 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Search justwhatsapp.io and make sure all content are perfectly
            loaded on the browser.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 3"
          class="card-alternate-1 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Open <BIconThreeDotsVertical /> on the top-right side of the chrome
            browser and <BIconBoxArrowUp /> on the bottom center of safari
            browser.</b-card-text
          >
        </b-card>

        <b-card
          text-variant="white"
          header="Step 4"
          class="card-alternate-2 font-weight-bold text-center mb-4"
        >
          <b-card-text class="font-weight-normal"
            >Find and select 'Add to homescreen'. Fill in the name of the apps
            and all set. Goodluck!</b-card-text
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
// import axios from 'axios'

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
        "We create a simple progressive web application (PWA) to ease your daily routines. So, you can directly access whatsapp chat without saving phone number of strangers. Super easy isn't?",
      Dev: '- Just Whatsapp Developer',
      form: {
        numberPhone: '',
        codeNumber: null,
      },
      codes: [],
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

  // created() {
  //   axios.get('http://localhost:3000/codes').then((response) => {
  //     this.codes = response.data
  //     console.log(this.codes)
  //   })
  // },
  methods: {
    onSubmit(evt) {
      evt.preventDefault()
      var dialcode = this.form.codeNumber
      var phone = dialcode + this.form.numberPhone

      if (!isNaN(phone)) {
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
