<template>
 <div class="packs-row justify-center space px-16 pb-5"  >
    <div class="pack-col" v-for="(pack, i) in packs" :key="i" style="background-color: white;">
      <div class="card mx-auto " style="max-width: 300px;" color="" flat outlined>
        <div class="text-center">
          <router-link :to="{ name: 'order' }">
          <img
            class="pack-img"
            style="max-height: 300px; max-width: 300px;"
            :src="pack.img"
            alt="Pack Image"
          >
        </router-link>
        </div>

        <h3 class="card-title">{{ pack.title }}</h3>
        <p class="grey--text text-grey-darken-1 caption mt-n6">{{ pack.subtitle }}</p>
        <p class="mt-n4">{{ pack.price }}</p>

        <div class="card-actions mx-2 mt-n4">
          <button class="add-btn" @click="decrement">
            <span class="icon" style="color: green;">-</span>
          </button>

          <strong class="mx-2" v-text="bpm"></strong>

          <button class="add-btn" @click="increment">
            <span class="icon" style="color: green;">+</span>
          </button>

          <div class="spacer"></div>
          <router-link :to="{ name: 'order' }">
          <v-btn class="mx-2 mt-n3" fab dark small color="green">
            <v-icon dark> mdi-shopping </v-icon>
          </v-btn>
            </router-link>
         
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
      bpm: 1,
    packs: [
      { img: "p1.png", title: "Medium Box", price: "Rs55" },
      { img: "p2.png", title: "Big Pack",  price: "Rs100" },
      { img: "p3.png", title: "Small",   price: "Rs45" },
      { img: "p4.png", title: "Medium Box",  price: "Rs55" },
      { img: "p5.png", title: "Medium Box", price: "Rs55" },
      { img: "p6.png", title: "Medium Box",  price: "Rs55" },
    ],
  }),
   methods: {
      decrement () {
        this.bpm--
      },
      increment () {
        this.bpm++
      },
     
    },
};
</script>

<style>
.packs-row {
  display: flex;
  justify-content: center;
  gap: 18px;
  flex-wrap: wrap;
}

.pack-col {
  flex: 0 0 calc(33.33% - 16px); /* 33.33% width for each column with a gap of 16px */
  box-sizing: border-box;
  margin-bottom: 20px;
}

.card {
 
  border-radius: 8px;
  padding: 16px;
}

.pack-img {
  max-height: 300px;
  max-width: 300px;
 
}

.card-title {
  margin-top: 0;
  font-size: 1.5rem;
}

.card-actions {
  display: flex;
  align-items: center;
  margin-top: 16px;
}

.add-btn {
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 8px;
  cursor: pointer;
}

.icon {
  font-size: 1.2rem;
}

.spacer {
  flex-grow: 1;
}

.action-btn {
  border: none;
  border-radius: 50%;
  padding: 12px;
  color: white;
  cursor: pointer;
}

/* Media Query for responsiveness */
@media (max-width: 768px) {
  .pack-col {
    flex: 0 0 calc(50% - 16px); /* 50% width for each column with a gap of 16px */
  }
}
</style>