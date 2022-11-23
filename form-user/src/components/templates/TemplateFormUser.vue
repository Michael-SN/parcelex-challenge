<template>
  <section class="mx-auto mt-12 w-full sm:w-[600px] rounded-xl border bg-white border-gray-100 p-8 shadow-lg">
    <AtomTitle tag="h2" content="Create your account" />

    <OrganismForm form-action="" id="formUser" method="POST">
      <MoleculeFormGroup>
        <AtomInputImage @update:image="user.profileImage = $event" />
      </MoleculeFormGroup>
      <MoleculeFormGroup legend="Name" for-input="txtName">
        <AtomInputText type-input="text" name-input="user_name" id="txtName" required="true"
          @update:value="user.name = $event" />
      </MoleculeFormGroup>

      <MoleculeFormGroup legend="E-mail" for-input="txtEmail">
        <AtomInputText type-input="email" name-input="user_email" id="txtEmail" required="true"
          @update:value="user.email = $event" />
      </MoleculeFormGroup>
      <div class="grid grid-cols-2 gap-4">
        <MoleculeFormGroup legend="Telephone" for-input="txtTelephone">
          <AtomInputText type-input="text" name-input="user_telephone" id="txtTelephone" required="true"
            @update:value="user.telephone = $event" />
        </MoleculeFormGroup>

        <MoleculeFormGroup legend="Age" for-input="dataUserBirth">
          <AtomInputText type-input="text" name-input="user_birthdate" id="dataUserBirth" required="false"
            @update:value="user.age = $event" />
        </MoleculeFormGroup>
      </div>
      <AtomButton>
        Submit
      </AtomButton>

    </OrganismForm>
  </section>
</template>

<script>
import MoleculeFormGroup from '@/molecules/MoleculeFormGroup.vue';
import AtomButton from '@/atoms/AtomButton.vue';
import AtomInputText from '@/atoms/AtomInputText.vue';
import AtomTitle from '@/atoms/AtomTitle.vue';
import OrganismForm from '@/organisms/OrganismForm.vue';
import AtomInputImage from '@/atoms/AtomInputImage.vue';

export default {
  name: 'TemplateFormUser',
  data() {
    return {
      user: {
        name: 'SN',
        email: 'teste@teste.com',
        age: '100',
        telephone: '(##) #####-####',
        profileImage: {}
      }
    }
  },
  methods: {
    // 
  },
  components: { MoleculeFormGroup, AtomButton, AtomInputText, AtomTitle, OrganismForm, AtomInputImage }
}
</script>