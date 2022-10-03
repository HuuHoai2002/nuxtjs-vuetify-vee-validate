<template>
  <div>
    <demo title="Demo v-btn">
      <v-btn color="primary">Primary</v-btn>
      <v-btn color="secondary">Secondary</v-btn>
      <v-btn color="success">Success</v-btn>
      <v-btn color="info">Info</v-btn>
      <v-btn color="warning">Warning</v-btn>
      <v-btn color="error">Error</v-btn>
    </demo>

    <demo title="Demo v-checkbox">
      <v-checkbox label="Checkbox 1" />
      <v-checkbox label="Checkbox 2" />
      <v-checkbox label="Checkbox 3" />
    </demo>

    <demo title="Demo v-combobox">
      <v-combobox
        v-model="selected"
        :items="items"
        label="Select an item"
        multiple
        chips
        deletable-chips
      ></v-combobox>
    </demo>

    <demo title="Demo v-text-field">
      <v-text-field label="Text" />
      <v-text-field label="Text" type="password" />
      <v-text-field label="Text" type="date" />
    </demo>

    <demo title="Demo v-alert">
      <v-alert type="success">Hello</v-alert>
      <v-alert type="warning">Hello</v-alert>
      <v-alert type="info">Hello</v-alert>
      <v-alert type="error">Hello</v-alert>
    </demo>

    <demo title="Demo v-dialog">
      <v-dialog v-model="dialog" width="500">
        <template #activator="{ on, attrs }">
          <v-btn color="blue" dark v-bind="attrs" v-on="on"> Click Me </v-btn>
        </template>

        <v-card>
          <v-card-title class="text-h5 green lighten-2">
            Privacy Policy
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false">
              I accept
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </demo>
  </div>
</template>

<script>
import Demo from '@/components/Demo.vue'
export default {
  name: 'LearnVuetifyPage',
  components: {
    Demo,
  },
  data() {
    return {
      selected: [],
      items: ['Item 1', 'Item 2', 'Item 3', 'Item 4'],
      dialog: false,
    }
  },
}
</script>

<style lang="scss" scoped></style>
