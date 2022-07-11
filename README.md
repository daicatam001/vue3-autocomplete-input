
# vue3-typeahead-input

A simple Vue 3 type-ahead input component that shows a list of suggested items based on the user input

## Table of contents

  - [Installation](#installation)
  - [Usage](#usage)

## Installation

Using npm
```
npm install vue3-typeahead-input
```

Using yarn
```
yarn add vue3-typeahead-input
```

## Usage
Import vue3-typeahead-input component globally. You can import default CSS of the component if you want.

```ts
import App from './App.vue';
import TypeaheadInput from 'vue3-typeahead-input';
import 'vue-typeahead-input/dist/style.css'; //Optional default CSS

let app = createApp(App)
app.component('TypeaheadInput', TypeaheadInput)
app.mount('#app')
```

...Or import vue3-typeahead-input component locally in component you want. 

```ts
import TypeaheadInput from 'vue3-typeahead-input'
import 'vue-typeahead-input/dist/style.css'; //Optional default CSS

export default {
    name: 'YourComponentName',
    components: {
        TypeaheadInput
    }
}
```
Use component in template
```html
<template>
    <div>
        <TypeaheadInput
            :items="items"
            @change="onChange"
            >
        </TypeaheadInput>    
    </div>
</template>

```
```html
<script setup>
    const items = [
        {
            text:'Item 1',
            value: 'item-1'
        },
        {
            text:'Item 2',
            value: 'item-2'
        },
        {
            text:'Item 3',
            value: 'item-3'
        },
    ]
    const onChange = (value)=>{
        console.log(value)
    }
</script>

```

## Properties

| Property  | Type | Description | Default |
|---|---|---|---|
| items | Array | An array of objects. It will look for a text and value keys. This can be changed using the item-text, item-value | [] |
| item-text | string | Set property of items’s text value | text |
| item-value | string | Set property of items’s value | value |

## Events

| Name | Description |
| ---- | ----------- |
| @input | The updated bound model |
| @change | Emitted when the input is changed by user interaction |
