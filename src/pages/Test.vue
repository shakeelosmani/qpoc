<template>
  <q-page class="flex flex-center">
    <CustomMoneyInput :model="formData.amount" @update="amountUpdated"></CustomMoneyInput>
    <CustomInput :model="formData.another" @update="stringUpdated"></CustomInput>
  </q-page>
</template>

<script>
import CustomMoneyInput from '../components/CustomMoneyInput'
import CustomInput from '../components/CustomInput'
export default {
  name: 'PageTest',
  components: {
      CustomMoneyInput,
      CustomInput
  },
  data() {
      return {
          formData: {
              amount: null,
              another: "This one does not show $"
          }
      }
  },
  methods: {
      amountUpdated(val) {
          this.formData.amount = val;
          console.log('value at parent', + val);
      },

      stringUpdated(val) {
          this.formData.another = val;
          console.log('value at parent', + val);
      },

      simulateAsyncUpdate() {
          setTimeout(() => {
            this.formData.amount = 1000; 
          }, 2000);
      }
  },

  mounted() {
      this.simulateAsyncUpdate();
  }

  
}
</script>
