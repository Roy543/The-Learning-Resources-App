<template>
  <ul></ul>
</template>

<script>
export default {
  data() {
    return {
      storedResource: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official VueJS Documentation.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to Google.',
          link: 'https://google.org',
        }
      ],
    };
  },
};
</script>