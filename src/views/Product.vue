<template>
  <div
    class="bg-image d-flex justify-content-center align-items-center"
    style="background-color: rgb(4, 40, 75)"
  >
    <v-container>
      <center><h1 style="color: white">Product</h1></center>
      <v-container class="d-flex flex-wrap">
        <v-card
          class="mx-auto mb-5"
          max-width="400"
          v-for="(i, index) in productlist"
          :key="index"
        >
          <v-img class="text-black align-end" height="350px" :src="i.imageurl">
            <v-card-title>{{ i.name }}</v-card-title>
          </v-img>

          <v-card-subtitle class="pb-0">{{ i.rightText }}</v-card-subtitle>

          <v-card-text class="text--primary">
            <div style="font-size: large">{{ i.leftText }}</div>
          </v-card-text>

          <v-card-actions>
            <v-btn color="info" text :to="'/detail/' + i.rightText"
              >detail</v-btn
            >
            <v-btn color="orange" @click="selected(i)"> Add </v-btn>
          </v-card-actions>
        </v-card>
      </v-container>

      <table class="table table-striped table-hover"></table>
      <v-container
        ><h4 class="text-danger fs-1">Total {{ total() }} Baht</h4></v-container
      >
      <v-container grid-list-xs class="white">
        <router-view :key="$route.path"></router-view>
      </v-container>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productlist: [
        {
          name: "ELITE Nike Mercurial Vapor 13 Elite Ag",
          imageurl:
            "https://p-th.ipricegroup.com/cfeb371787e30067ff5050eb7e0138fb8219756f_0.jpg?position=6",
          rightText:
            "Top Nike รองเท้าผ้าใบลําลองเหมาะกับการเล่นฟุตบอล Size 39-45",
          leftText: "Price : 2,568",
          active: false,
          price: 2568,
        },

        {
          name: "Nike Men's Air Max Alpha Trainer 4 Training Shoes - Black",
          imageurl:
            "https://p-th.ipricegroup.com/d96b9f70a931d386fc72fb1c6e117f99cda7bc01_0.jpg?position=7",
          rightText:
            "ไนกี้ รองเท้าเทรนนิ่งผู้ชาย แอร์ แม็กซ์ อัลฟ่า เทรนเนอร์ 4 - สีดำ Size 39-45",
          leftText: "Price : 3,100",
          active: false,
          price: 3100,
        },

        {
          name: "Nike Hypervenom Phantom III DF FG",
          imageurl:
            "https://p-th.ipricegroup.com/05c5d117285ccf7e6daff582b689a90fb8374312_0.jpg?position=8",
          rightText:
            "รองเท้าฟุตบอลไฮท็อป Nike Hypervenom Phantom III DF FG Size 39-45",
          leftText: "Price : 1,759",
          active: false,
          price: 1759,
        },

        {
          name: "Nike Mercurial Vapor 13 Elite FG",
          imageurl:
            "https://p-th.ipricegroup.com/a7bb17034b4ae393dba7eeb6c557b126473805de_0.jpg?position=10",
          rightText:
            "องเท้าผ้าใบลําลองไซส์ Knitted waterproof low-top football shoes Size 39-45",
          leftText: "Price : 1,378",
          active: false,
          price: 1378,
        },
        {
          name: "Nike Tiempo Legend 9 Elite FG",
          imageurl:
            "https://p-th.ipricegroup.com/394a8bd3ff445e7c2e9e819100d0ba2e4cebd6f6_0.jpg?position=19",
          rightText:
            "	ใหม่ล่าสุด Nike Tiempo Legend 9 Elite FG รองเท้าฟุตบอล สตั๊ด ตัวท็อป Size 39-45",
          leftText: "Price : 7,900",
          active: false,
          price: 7900,
        },
        {
          name: "Nike Hypervenom Phantom III DF FG",
          imageurl:
            "https://p-th.ipricegroup.com/e35ba1a1cc3bbbc484e512a53b97de2dbbf5c50b_0.jpg?position=32",
          rightText:
            "รองเท้าฟุตบอล NIke Hypervenom Phantom III DF FG Size 39-45",
          leftText: "Price : 2,338",
          active: false,
          price: 2338,
        },
        {
          name: "Nike Mercurial Superfly 7 Elite FG",
          imageurl:
            "https://p-th.ipricegroup.com/930bdb874dd56cc06a0e63e4c8e43ca34de5698a_0.jpg?position=33",
          rightText:
            "Nike รองเท้าฟุตบอล กันน้ํา สําหรับผู้ชาย และผู้หญิง Size 36-45",
          leftText: "Price : 1,378",
          active: false,
          price: 1378,
        },
        {
          name: "Nike Mercurial Superfly 8 Academy FG/MG Mbappe",
          imageurl:
            "https://p-th.ipricegroup.com/0f5dceff26f47fc2cd6a1bfe8dba0b0a7335c90f_0.jpg?position=36",
          rightText:
            "ใหม่ล่าสุด Nike Mercurial Superfly 8 Academy FG/MG Mbappe รองเท้าฟุตบอล สตั๊ดหุ้มข้อ Size 39-45",
          leftText: "Price : 6,500",
          active: false,
          price: 6500,
        },
      ],
    };
  },
  methods: {
    selected: function (i) {
      i.active = !i.active;
    },
    total: function () {
      var sum = 0;
      this.productlist.forEach(function (i) {
        if (i.active) {
          sum += i.price;
        }
      });
      return sum;
    },
  },
};
</script>

<style>
h2 {
  color: white;
}
</style>
