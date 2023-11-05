<template>
  <li>
    <div>
      <header>
        <h3>Title {{ title }}</h3>
        <button>Delete</button>
      </header>
    </div>
    <p>Description {{ description }}</p>
    <nav>
      <a :href=link>Link</a>
    </nav>
  </li>
</template>

<script>
export default { 
  props: {
    id: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
  },
};
</script>
