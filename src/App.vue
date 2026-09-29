```vue
<script setup>
import { ref } from 'vue'

import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

import HomeView from './components/HomeView.vue'
import PackagesView from './components/PackagesView.vue'
import AboutView from './components/AboutView.vue'
import ContactForm from './components/ContactForm.vue'


const currentPage = ref('home')

const submittedForm = ref(null)


const initialFormData = {
  eventType: '',
  eventDate: '',
  guestCount: null,
  locationType: '',
  style: '',
  colourTheme: '',
  products: [],
  budget: '',
  requirements: '',
  name: '',
  email: '',
  mobile: ''
}


const formConfig = {
  maxGuests: 1000,
  maxRequirementsLength: 500
}


function handleNavigation(page) {

  currentPage.value = page

  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })

}


function handleFormSubmit(formData) {

  submittedForm.value = {
    ...formData
  }

}


function getEventLabel(eventType) {

  const eventLabels = {
    birthday: 'Birthday',
    wedding: 'Wedding',
    graduation: 'Graduation',
    corporate: 'Corporate Event',
    'baby-shower': 'Baby Shower',
    festival: 'Festival / Community Event',
    other: 'Other Celebration'
  }

  return eventLabels[eventType] || eventType

}


function getBudgetLabel(budget) {

  const budgetLabels = {
    'under-150': 'Under $150',
    '150-300': '$150 – $300',
    '300-500': '$300 – $500',
    '500-1000': '$500 – $1,000',
    '1000-plus': '$1,000+'
  }

  return budgetLabels[budget] || budget

}
</script>


<template>

  <div class="app">

    <AppHeader
      :current-page="currentPage"
      @navigate="handleNavigation"
    />


    <HomeView
      v-if="currentPage === 'home'"
      @navigate="handleNavigation"
    />


    <PackagesView
      v-else-if="currentPage === 'packages'"
      @navigate="handleNavigation"
    />


    <AboutView
      v-else-if="currentPage === 'about'"
      @navigate="handleNavigation"
    />


    <main v-else-if="currentPage === 'planner'">

      <ContactForm
        :initial-data="initialFormData"
        :config="formConfig"
        @submit-form="handleFormSubmit"
      />


      <section
        v-if="submittedForm"
        class="section"
      >

        <div class="page-container">

          <div class="acknowledgement-card">

            <span class="about-section-label">
              Plan received
            </span>

            <h2>
              Celebration Plan Received
            </h2>

            <p>
              <strong>
                Thank you, {{ submittedForm.name }}!
              </strong>
              We have received your celebration details and
              created a planning summary based on your preferences.
            </p>


            <ul>

              <li>
                <strong>Event:</strong>
                {{ getEventLabel(submittedForm.eventType) }}
              </li>

              <li>
                <strong>Event Date:</strong>
                {{ submittedForm.eventDate }}
              </li>

              <li>
                <strong>Guests:</strong>
                {{ submittedForm.guestCount }}
              </li>

              <li>
                <strong>Location:</strong>
                {{ submittedForm.locationType }}
              </li>

              <li>
                <strong>Style:</strong>
                {{ submittedForm.style }}
              </li>

              <li>
                <strong>Colour Theme:</strong>
                {{ submittedForm.colourTheme }}
              </li>

              <li>
                <strong>Budget:</strong>
                {{ getBudgetLabel(submittedForm.budget) }}
              </li>

              <li>
                <strong>Requirements:</strong>
                {{ submittedForm.products.join(', ') }}
              </li>

            </ul>


            <p v-if="submittedForm.requirements">

              <strong>
                Additional Requirements:
              </strong>

              {{ submittedForm.requirements }}

            </p>


            <p class="form-note">

              We can use these details as the starting point
              for building your celebration plan.

            </p>

          </div>

        </div>

      </section>

    </main>


    <AppFooter
      @navigate="handleNavigation"
    />

  </div>

</template>
```