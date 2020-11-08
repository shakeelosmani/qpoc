<template>
  <div class="q-pa-md">
    <div class="q-gutter-md" style="max-width: 300px">
      <CustomInput :model="model" @update="valueUpdated" :showDollar="showDollar">
      </CustomInput>
    </div>
  </div>
</template>

<script>
import CustomInput from './CustomInput';
export default {
    name: 'CustomMoneyInput',
    components: {
        CustomInput
    },
    props: {
        model: {type : [String, Number]}
    },

    data() {
        return {
            showDollar: true
        }
        
    },

    methods: {
        valueUpdated(val) {
            this.$emit('update', val);
        }
    }

}
</script>