<template>
  <div>
    <p>{{ $t("hello") }}</p>
    <p>{{ $t("goodbye", { name }) }}</p>
    <p>{{ $tc("person", 0) }}</p>

    <p>{{ $tc("person", 1) }}</p>

    <p>{{ $tc("person", 2) }}</p>

    <p>{{ $d(new Date(), "short") }}</p>
    <p>{{ $d(new Date(), "long") }}</p>
    <button @click="setLocale('en')" class="button">English</button>
    <button @click="setLocale('uz')" class="button">Uzbek</button>
    <button @click="setLocale('de')" class="button">German</button>
  </div>
</template>

<script>
export default {
  name: "HelloI18n",
  data() {
    return { name: "Alex" };
  },
  methods: {
    setLocale(locale) {
      this.$i18n.locale = locale;
      localStorage.setItem("locale", locale);
    }
  }
};
</script>
