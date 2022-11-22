<template>
  <section class="mx-auto mt-12 w-full sm:w-[600px] rounded-xl border bg-white border-gray-100 p-8 shadow-lg">
    <AtomTitle tag="h2" content="Create your account" />

    <OrganismForm form-action="/endpoint" id="formUser" method="POST">

      <MoleculeFormGroup legend="Name" for-input="txtName">
        <AtomInputText type-input="text" name-input="user_name" id="txtName" required="true" />
      </MoleculeFormGroup>

      <MoleculeFormGroup legend="E-mail" for-input="txtEmail">
        <AtomInputText type-input="email" name-input="user_email" id="txtEmail" required="true" />
      </MoleculeFormGroup>

      <MoleculeFormGroup legend="Telephone" for-input="txtTelephone">
        <AtomInputText type-input="text" name-input="user_telephone" id="txtTelephone" required="true" />
      </MoleculeFormGroup>

      <MoleculeFormGroup legend="Age" for-input="dataUserBirth">
        <AtomInputText type-input="text" name-input="user_birthdate" id="dataUserBirth" required="false" />
      </MoleculeFormGroup>
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

export default {
  name: 'TemplateFormUser',
  components: { MoleculeFormGroup, AtomButton, AtomInputText, AtomTitle, OrganismForm }
}
</script>