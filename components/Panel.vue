<template>
  <div class="bg-white overflow-hidden shadow rounded-lg w-48 mb-4">
    <div
      class="border-b border-gray-200 bg-purple-500 text-white font-bold px-2 py-2 text-center"
    >
      <slot name="header"></slot>
    </div>
    <div class="px-4 py-4 text-center">
      <slot></slot>
    </div>
  </div>
</template>
