<template>
  <section class="mx-auto mt-12 w-full sm:w-[600px] rounded-xl border bg-white border-gray-100 p-8 shadow-lg">
    <AtomTitle tag="h2" content="Create your account" />

    <OrganismForm id="formUser" method="POST" @submit.prevent="submit">
      <MoleculeFormGroup>
        <AtomInputImage @update:image="getTheImage($event)" />
      </MoleculeFormGroup>
      <MoleculeFormGroup legend="Name:" for-input="txtName">
        <AtomInputText type-input="text" name-input="user_name" id="txtName" required="true"
          @update:value="user.name = $event" />
      </MoleculeFormGroup>

      <MoleculeFormGroup legend="E-mail:" for-input="txtEmail">
        <AtomInputText type-input="email" name-input="user_email" id="txtEmail" required="true"
          @update:value="user.email = $event" />
      </MoleculeFormGroup>
      <div class="grid grid-cols-2 gap-4">
        <MoleculeFormGroup legend="Phone Number:" for-input="txtTelephone">
          <AtomInputText type-input="tel" v-mask="['(##) ####-####', '(##) #####-####']" name-input="user_telephone"
            id="txtTelephone" required="true" @update:value="user.phone = $event" />
        </MoleculeFormGroup>

        <MoleculeFormGroup legend="Age:" for-input="dataUserBirth">
          <AtomInputText type-input="date" name-input="user_birthdate" id="dataUserBirth" required="false"
            @update:value="user.age = $event" />
        </MoleculeFormGroup>
      </div>
      <AtomButton typed="submit">
        Submit
      </AtomButton>
    </OrganismForm>
    <OrganismsFeedback v-if="successForm" :user="user" />
  </section>
</template>

<script>
import MoleculeFormGroup from '@/molecules/MoleculeFormGroup.vue';
import AtomButton from '@/atoms/AtomButton.vue';
import AtomInputText from '@/atoms/AtomInputText.vue';
import AtomTitle from '@/atoms/AtomTitle.vue';
import OrganismForm from '@/organisms/OrganismForm.vue';
import OrganismsFeedback from '@/organisms/OrganismsFeedback.vue';
import AtomInputImage from '@/atoms/AtomInputImage.vue';
import { mask } from 'vue-the-mask'

export default {
  name: 'TemplateFormUser',
  data() {
    return {
      user: {
        name: '',
        email: '',
        age: '',
        phone: '',
        profileImage: {}
      },
      successForm: false
    }
  },
  methods: {
    getTheImage(e) {
      let { name, size } = e
      this.user.profileImage = { fileName: name, sizeImage: size }
    },
    checkForm({ name, email }) {
      return (name.length && email.length) ? true : false
    },
    submit() {
      try {
        let formChecked = this.checkForm(this.user)
        if (formChecked) {
          setTimeout(() => {
            this.successForm = true
          }, 1000)
        }
      } catch (error) {
        console.log(error)
      }
    }
  },
  directives: { mask },
  components: { MoleculeFormGroup, AtomButton, AtomInputText, AtomTitle, OrganismForm, OrganismsFeedback, AtomInputImage }
}
</script>