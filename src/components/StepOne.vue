<template>
  <div class="container stepOne">
    <VueMultiselect
    v-for="option in options"
      v-model="value.title"
      :options="option.title">
    </VueMultiselect>
    <h1>نموذج طلب المنتج"هندسة الموسم"</h1>
    <h3>بيانات المنظمة</h3>
    <div class="stepOne__items">
      <div class="stopOne_content">
        <label for="nameOfOrgnization"> اسم المنظمة<span>*</span></label
        ><br />
        <input
          type="text"
          name="nameOfOrgnization"
          id="nameOfOrgnization"
          v-model="nameOfOrgnization"
        /><br />
      </div>
      <div class="stopOne_content">
        <label for="activeOfOrgnization"> نشاط المنظمة<span>*</span></label
        ><br />
        <input
          type="text"
          name="acriveOfOrgnization"
          id="activeOfOrgnization"
          v-model="activeOfOrgnization"
        /><br />
      </div>
      <div class="stopOne_content">
        <label for="city"> المدينة<span>*</span></label
        ><br />
        <input type="text" name="city" id="city" v-model="city" />
      </div>
      <div class="stopOne_content">
        <label for="government">المركز/المحافظه<span>*</span></label
        ><br />
        <input
          type="text"
          name="government"
          id="government"
          v-model="government"
        />
      </div>
    </div>
    <h3>الباقة المطلوبة</h3>
    <div class="chooseOption">
      <label for="chooseOption">اختر الباقة<span>*</span></label
      ><br />
      <input
        type="number"
        name="chooseOption"
        id="chooseOption"
        v-model="chooseOption"
      />
    </div>
  </div>
</template>

<script>
import VueMultiselect from 'vue-multiselect'

export default {
  components: { VueMultiselect },
  data () {
    return {
      value: { title: 'Explorer', desc: 'Discovering new species!', img: 'static/posters/creatures.png' },
      options: [
        { title: 'Space Pirate', desc: 'More space battles!', img: 'static/posters/fleet.png' },
        { title: 'Merchant', desc: 'PROFIT!', img: 'static/posters/trading_post.png' },
        { title: 'Explorer', desc: 'Discovering new species!', img: 'static/posters/creatures.png' },
        { title: 'Miner', desc: 'We need to go deeper!', img: 'static/posters/resource_lab.png' }
      ]
    
  }
  },
  methods: {},
  computed: {
    nameOfOrgnization: {
      get() {
        return this.$store.state.user.nameOfOrgnization;
      },
      set(value) {
        this.$store.commit("updateNameOfOrgnization", value);
      },
    },
    activeOfOrgnization: {
      get() {
        return this.$store.state.user.activeOfOrgnization;
      },
      set(value) {
        this.$store.commit("updateActiveOfOrgnization", value);
      },
    },
    city: {
      get() {
        return this.$store.state.user.city;
      },
      set(value) {
        this.$store.commit("updateCity", value);
      },
    },
    government: {
      get() {
        return this.$store.state.user.government;
      },
      set(value) {
        this.$store.commit("updateGovernment", value);
      },
    },
    chooseOption: {
      get() {
        return this.$store.state.user.chooseOption;
      },
      set(value) {
        this.$store.commit("updateChooseOption", value);
      },
    },
  },
};
</script>
<style src="vue-multiselect/dist/vue-multiselect.css" scoped></style>


