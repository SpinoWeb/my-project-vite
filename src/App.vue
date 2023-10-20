<script setup lang="ts"></script>

<template>
  <div class="container mx-auto rounded-xl shadow border p-2 m-4">
    <div class="navbar bg-base-300 rounded-box">
      <div class="flex-1 px-2 lg:flex-none">
        <a class="text-lg font-bold">daisyUI</a>
      </div>
      <div class="flex justify-end flex-1 px-2">
        <div class="flex items-stretch">
          <a class="btn btn-ghost rounded-btn">Button</a>

          <div class="dropdown">
            <label tabindex="0" class="btn m-1">Click</label>
            <div
              tabindex="0"
              class="dropdown-content z-[1] card card-compact w-64 p-2 shadow bg-primary text-primary-content"
            >
              <div class="card-body">
                <h3 class="card-title">Card title!</h3>
                <p>you can use any element as a dropdown.</p>
              </div>
            </div>
          </div>
          <div class="dropdown dropdown-end">
            <label tabindex="0" class="btn btn-ghost rounded-btn"
              >Dropdown</label
            >
            <ul
              tabindex="0"
              class="menu dropdown-content z-[1] p-2 shadow bg-base-100 rounded-box w-52 mt-4"
            >
              <li><a>Item 1</a></li>
              <li><a>Item 2</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <details class="dropdown mb-32">
      <summary class="m-1 btn">open or close</summary>
      <ul
        class="p-2 shadow menu dropdown-content z-[1] bg-base-100 rounded-box w-52"
      >
        <li><a>Item 1</a></li>
        <li><a>Item 2</a></li>
      </ul>
    </details>
    <button class="btn btn-primary">One</button>
    <button class="btn btn-secondary">Two</button>
    <button class="btn btn-accent">Three</button>
    <button class="btn btn-outline">Default</button>
    <button class="btn btn-outline btn-primary">Primary</button>
    <button class="btn btn-outline btn-secondary">Secondary</button>
    <button class="btn btn-outline btn-accent">Accent</button>
    <button class="btn btn-square">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        />
      </svg>
    </button>
    <button class="btn btn-square btn-outline">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        />
      </svg></button
    ><button class="btn">
      <span class="loading loading-spinner"></span>
      loading
    </button>
  </div>

  <div class="container mx-auto rounded-xl shadow border p-2 m-4">
    <div class="card-body mx-auto rounded-xl shadow border">
      <h3 class="card-title">Card title!</h3>
      <select class="select w-full max-w-xs">
        <option disabled selected>Pick your favorite Simpson</option>
        <option>Homer</option>
        <option>Marge</option>
        <option>Bart</option>
        <option>Lisa</option>
        <option>Maggie</option></select
      ><input
        type="text"
        placeholder="Type here"
        class="input w-full max-w-xs"
      />
    </div>
  </div>

  <div class="container mx-auto rounded-xl shadow border p-8 m-10">
    <article class="prose">
      <h1>Garlic bread with cheese: What the science tells us</h1>
      <p>
        For years parents have espoused the health benefits of eating garlic
        bread with cheese to their children, with the food earning such an
        iconic status in our culture that kids will often dress up as warm,
        cheesy loaf for Halloween.
      </p>
      <p>
        But a recent study shows that the celebrated appetizer may be linked to
        a series of rabies cases springing up around the country.
      </p>
      <!-- ... -->
    </article>
  </div>

  <div class="container mx-auto rounded-xl shadow border p-8 m-10">
    <div class="grid grid-cols-12 gap-2">
      <button class="btn btn-primary" v-for="i in 36">{{ i }}</button>
    </div>
  </div>
</template>
