<template>
  <div class="form-section">
    <form @submit.prevent="handleSubmit" class="form">
      <div class="wrapper">
        <UI-input v-model="gel" placeholder="GEL per item" />
      </div>
      <div>
        <p>Select who will <strong>not</strong> pay</p>
        <UI-check-box
          v-for="user in users"
          :name="user.name"
          :key="user.id"
          v-model="user.checked"
        />
      </div>
      <div class="btns-wrapper">
        <UI-button>Add</UI-button>
      </div>
    </form>

    <div class="monetary-debt">
      <h2>Monetary debt</h2>
      <my-list :users="users" />
      <UI-button @click="removeItems" bgColor="lightcoral">Remove</UI-button>
    </div>
  </div>
</template>

<script>
import UIInput from "@/components/UI/UIInput.vue";
import UIButton from "@/components/UI/UIButton.vue";
import UICheckBox from "@/components/UI/UICheckBox.vue";
import MyList from "@/components/MyList.vue";

export default {
  components: {
    UIInput,
    UIButton,
    UICheckBox,
    MyList,
  },
  data() {
    return {
      gel: null,
      users: [
        { id: Date.now(), name: "Соня", checked: false, debt: 0 },
        { id: Date.now(), name: "Карина", checked: false, debt: 0 },
        { id: Date.now(), name: "Гриша", checked: false, debt: 0 },
        { id: Date.now(), name: "Саша", checked: false, debt: 0 },
      ],
    };
  },
  methods: {
    handleSubmit() {
      let usersChecked = this.users.filter((user) => !user.checked).length;

      this.users.forEach((user) => {
        if (!user.checked) {
          let debt = this.gel / usersChecked;
          user.debt += debt;
        }
        user.checked = false;
      });

      this.gel = null;
    },
    removeItems() {
      this.users.forEach((user) => {
        user.debt = 0;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.form-section {
  margin-top: 2rem;
  display: flex;
  flex: 1;
  min-height: 230px;
  gap: 1rem;
  max-width: 100%;
  justify-content: center;
  align-items: center;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  height: 250px;
  max-width: 500px;
  background-color: #fff;
  border-radius: 1rem;
  filter: drop-shadow(2px 2px 4px #aaa);
}

.wrapper {
  display: flex;
  gap: 1rem;
}

.monetary-debt {
  @extend .form;
}

.btns-wrapper {
  display: flex;
  gap: 1rem;
}

@media screen and (max-width: 414px) {
  .form-section {
    flex-direction: column;
  }
}
</style>
