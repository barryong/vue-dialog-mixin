# vue-dialog-mixin

[![Version](https://img.shields.io/npm/v/vue-dialog-mixin)](https://www.npmjs.com/package/vue-dialog-mixin)

Vue mixin for dialog components to enable dialog closing on browser's back button clicked

## Install
```
$ npm install vue-dialog-mixin
```

## Requires

Vuex store to store the dialogs state.

## Usage

I use vuetify ui framework as an example below:

```vue
<template>
  <v-row justify="center">
    <v-btn @click.stop="dialog = true">
      Open Dialog
    </v-btn>

    <v-dialog v-model="dialog">
      <v-card>
        <v-card-title class="headline">Example</v-card-title>
        <v-card-text>
          Click browser's back button to close me.
        </v-card-text>
        <v-card-actions>
          <v-btn @click="closeDialog">Close</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>
<script>
import dialogMixin from "vue-dialog-mixin"

export default {
  mixins: [dialogMixin]
}
</script>
```

#### Step 1
Import vue-dialog-mixin in the script section
#### Step 2
Define vue-dialog-mixin variable in the mixins hook
#### Step 3
Must use `dialog` for the dialog v-model directive

## Methods

### showDialog()
You can use `showDialog()` method to show the dialog instead of using `dialog = true`

### closeDialog()
It's the same to closing the dialog, you can use `closeDialog()` instead of `dialog = false` to close the dialog

