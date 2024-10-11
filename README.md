# DOCS-Alpine.js
Catatan random penggunaan alpine js :v


```html
showing model using alpine js and tailwind css

<html x-data="{variableA = null}">

  <button @click="$dispatch('showMyCustomModal', {url: 'https://www.custom-link.com/', username: 'jhon doe'})">open modal</button>

  <div x-data="{isModalOpen: false, url: null, username: null}" x-show="isModalOpen" @open-showMyCustomModal.window "isModalOpen: true, url : $event.detail.url, username : $event.detail.username">
  <!-- tambahan @keydown.escape="isModalOpen = false" x-transition:enter="transition ease-out duration-150" x-transition:enter-start="opacity-0" x-transition:enter-end="opacity-100" x-transition:leave="transition ease-in duration-150" x-transition:leave-start="opacity-100" x-transition:leave-end="opacity-0" -->
    <div @click.away="isModalOpen=false">
    <!-- x-transition:enter="transition ease-out duration-150" x-transition:enter-start="opacity-0 transform translate-y-1/2" x-transition:enter-end="opacity-100" x-transition:leave="transition ease-in duration-150" x-transition:leave-start="opacity-100" x-transition:leave-end="opacity-0  transform translate-y-1/2"  -->
      <form @set-form-action.window="action = $event.detail.url" method="POST" >
        <input x-model="username"/>
      </form>
    </div>
  </div>
</html>

```
