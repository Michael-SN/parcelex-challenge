<template>
  <div class="mx-auto mt-12 w-[600px] rounded-xl border bg-white border-gray-100 p-8 shadow-lg">
    <!-- <section class="card-info-container">
      <div class="card-info">
        <div class="w-3/4 antialiased">
          <h3 class="h-32 text-xl font-semibold tracking-wider">Untitled.</h3>
          <div class="mb-2 flex items-center justify-between">
            <div class="font-mono text-xl uppercase">Michael Nascimento</div>
            <div class="font-mono text-xl">08/29</div>
          </div>
          <div class="flex justify-between font-mono text-2xl">
            <span>XXXX</span>
            <span>XXXX</span>
            <span>XXXX</span>
            <span>XXXX</span>
          </div>
        </div>
      </div>
    </section> -->

    <h3 class="mb-8 text-2xl tracking-wider text-center">Create your account</h3>

    <form action="">
      <div>
        <FormInput legend="Name" for-input="txtName">
          <input type="text" id="txtName" name="user_name" class="form-input" required />
        </FormInput>

        <FormInput legend="E-mail" for-input="txtEmail">
          <input type="text" id="txtEmail" name="user_email" class="form-input" required />
        </FormInput>

        <FormInput legend="Telephone" for-input="txtTelephone">
          <input type="text" id="txtTelephone" name="user_telephone" class="form-input" required />
        </FormInput>

        <FormInput legend="Age" for-input="dataUserBirth">
          <input type="text" id="dataUserBirth" name="user_birthdate" class="form-input" required />
        </FormInput>
      </div>
      <SubmitButton btn-text="Submit" />
    </form>
  </div>

</template>

<script>
import FormInput from './components/FormInput.vue';
import SubmitButton from './components/SubmitButton.vue';



export default {
  components: { FormInput, SubmitButton }
}
</script>