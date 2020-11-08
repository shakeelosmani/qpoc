<template>
  <div class="q-pa-md">
    <div class="q-gutter-md" style="max-width: 300px">
      <q-input :value="model" @input="updated">
        <template v-if="showDollar" v-slot:prepend>
            $
        </template>
      </q-input>
    </div>
  </div>
</template>

<script>
export default {
    name: 'CustomInput',
    props: {
        model: {type : [String, Number]},
        showDollar: {type: Boolean, default: false}
    },

    methods: {
        updated(val) {
            this.$emit('update', val);
        }
    }

}
</script>