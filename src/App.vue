<script setup>
import { ref } from 'vue';

let items = ref(['Piim', 'Viin', 'Sai', 'Mac']);
let newItem = ref('');

function add(){
  if(newItem.value.trim() !== '') {
    items.value.push(newItem.value.trim());
  }
  newItem.value = '';
}

</script>

<template>
  <div class="container content mt-3">
    <div class="field has-addons">
        <div class="control is-expanded">
            <input @keydown.enter="add" v-model="newItem" class="input" type="text" placeholder="Find a repository">
        </div>
        <div class="control">
            <button @click="add" class="button is-info">
                Add
            </button>
        </div>
    </div>
    <ul>

      <li v-for="item in items">{{ item }}</li>

    </ul>
  </div>
</template>

<style></style>