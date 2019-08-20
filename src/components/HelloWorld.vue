<template>
  <div class="q-pa-md">
    <q-stepper
      v-model="step"
      vertical
      color="primary"
      animated
    >
      <q-step
        :name="1"
        title="Personal Information"
        icon="assignment"
        :done="step > 1"
      >
      
      <q-input
        ref="name"
        filled
        v-model="name"
        label="Full Name"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        v-model= "date"
        filled type ="date"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>

      <q-input
        ref="phone"
        filled
        type="number"
        v-model="phone"
        label="Number Handphone"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        ref="email"
        filled
        v-model="email"
        label="Your Email"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
      v-model="text"
      filled
      type="textarea"
      label="Address"
      lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <div>
        <q-btn label="Submit" type="submit" color="primary" />
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>

        <q-stepper-navigation>
          <q-btn @click="step = 2" color="primary" label="Continue" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="2"
        title="Educational Background"
        caption="Optional"
        icon="assignment"
        :done="step > 2"
      >
      <div class="q-gutter-md row items-start">
        <q-input
          v-model= "text"
          filled type= "text"
          hint="School/University"
          lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model= "text"
        filled type="text"
        hint="Major"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model="years"
        filled type="years"
        hint="From"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model="years"
        filled type="years"
        hint="To"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>

        <q-input
        v-model="gpa"
        filled type="gpa"
        hint="GPA"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>

        <div>
        <q-btn label="Submit" type="submit" color="primary" />
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
        </div>
      
      </div>
        <q-stepper-navigation>
          <q-btn @click="step = 3" color="primary" label="Continue" />
          <q-btn flat @click="step = 1" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="3"
        title="Courses and Certifications"
        icon="assignment"
        :done="step > 3"
      >

      <div class="q-gutter-md row items-start">
        <q-input
          v-model= "text"
          filled type= "text"
          hint="Course and Certificates Name"
          lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model= "text"
        filled type="text"
        hint="Organizer"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model="years"
        filled type="years"
        hint="From"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
        />

        <q-input
        v-model="years"
        filled type="years"
        hint="To"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>

        <div>
        <q-btn label="Submit" type="submit" color="primary" />
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
        </div>
      </div>
        <q-stepper-navigation>
          <q-btn @click="step = 4" color="primary" label="Continue" />
          <q-btn flat @click="step = 2" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="4"
        title="Working Experience"
        icon="assignment"
        :done="step > 4"
      >
        <q-stepper-navigation>
          <q-btn @click="step = 5" color="primary" label="Continue" />
          <q-btn flat @click="step = 3" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="5"
        title="Core Skills"
        icon="assignment"
        :done="step > 5"
      >
        <q-stepper-navigation>
          <q-btn @click="step = 6" color="primary" label="Continue" />
          <q-btn flat @click="step = 4" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="6"
        title="Why Do You Want To Join Our Company and How Will You Make a Difference"
        icon="assignment"
        :done="step > 6"
      >
        <q-stepper-navigation>
          <q-btn @click="step = 7" color="primary" label="Continue" />
          <q-btn flat @click="step = 5" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="7"
        title="General Inquiry"
        icon="assignment"
        :done="step > 7"
      >
        <q-stepper-navigation>
          <q-btn @click="step = 8" color="primary" label="Continue" />
          <q-btn flat @click="step = 6" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
        :name="8"
        title="Reference"
        icon="assignment"
      >

        <q-stepper-navigation>
          <q-btn color="primary" label="Finish" />
          <q-btn flat @click="step = 7" color="primary" label="Back" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>
    </q-stepper>
  </div>
</template>

<style>
</style>

<script>
export default {
  data () {
    return {
      step: 1,
      name: null,
      age: null,

      accept: false
    }
  },

  methods: {
    onSubmit () {
      this.$refs.name.validate()
      this.$refs.age.validate()

      if (this.$refs.name.hasError || this.$refs.age.hasError) {
        this.formHasError = true
      }
      else if (this.accept !== true) {
        this.$q.notify({
          color: 'negative',
          message: 'You need to accept the license and terms first'
        })
      }
      else {
        this.$q.notify({
          icon: 'done',
          color: 'positive',
          message: 'Submitted'
        })
      }
    },

    onReset () {
      this.name = null
      this.age = null

      this.$refs.name.resetValidation()
      this.$refs.age.resetValidation()
    }
  }
}
</script>