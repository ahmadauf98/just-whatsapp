<template>
  <div>
    <b-card class="card mt-4 mr-5 mb-4 ml-5 pt-3" text-variant="#00473e">
      <b-container fluid="lg">
        <b-row>
          <div class="mx-auto my-auto col-xs-12 col-lg-6">
            <img class="Picture" src="~/static/pic.svg" alt="Picture" />
          </div>
          <div class="mx-auto my-auto col-xs-12 col-lg-6">
            <b-row-form>
              <b-form @submit="onSubmit">
                <b-form-group label="Country Code:">
                  <b-form-select
                    v-model="form.code"
                    :options="codes"
                    required
                  ></b-form-select>
                </b-form-group>

                <b-form-group label="Phone Number">
                  <b-form-input
                    v-model="form.name"
                    required
                    placeholder="Enter phone number"
                  ></b-form-input>
                </b-form-group>

                <b-button class="btn-submit" type="submit"
                  >Chat now <b-icon-arrow-up></b-icon-arrow-up
                ></b-button>
              </b-form>
            </b-row-form>
          </div>
        </b-row>
      </b-container>
    </b-card>

    <b-card class="card mt-4 mr-5 mb-4 ml-5 pt-3" text-variant="#00473e">
      <blockquote class="card-blockquote text-uppercase">
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
export default {
  data() {
    return {
      Info:
        'We create simple progressive web application to ease your daily routines. So, you can directly access whatsapp chat without saving phone number of strangers.',
      Dev: '- Just Whatsapp Developer',
      form: {
        email: '',
        name: '',
        code: null,
        checked: [],
      },
      codes: [
        { text: 'Select Country Code', value: null },
        'Carrots',
        'Beans',
        'Tomatoes',
        'Corn',
      ],
      show: true,
    }
  },
  method: {
    onSubmit(evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset(evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.food = null
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    },
  },
}
</script>

<style scoped>
.card {
  background-color: #f2f7f5;
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
