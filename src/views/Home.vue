<template>
  <div class="font-two">
    <div class="format-text">
      <div class="home">
        <h1>Welcome to the Library!</h1>
        <div class="search-gruoup">
          <input v-model="name" placeholder="Search item" />
          <button @click="searchByName()">Search for name</button>
          <button @click="searchByDescription()">Search for description</button>
        </div>
        <div class="radio-button-filter">
          <input
            type="radio"
            v-model="selectedCategory"
            value="Books"
            id="r-books"
          />
          <label for="r-books">Books</label>
          <input
            type="radio"
            v-model="selectedCategory"
            value="Magazines"
            id="r-magazines"
          />
          <label for="r-magazines">Magazines</label>
          <input
            type="radio"
            v-model="selectedCategory"
            value="Newspaper"
            id="r-newspaper"
          />
          <label for="r-newspaper">Newspaper</label>
          <input
            type="radio"
            v-model="selectedCategory"
            value="Others"
            id="r-others"
          />
          <label for="r-others">Others</label>
          <input
            type="radio"
            v-model="selectedCategory"
            value="All"
            id="r-all"
          />
          <label for="r-all">All</label>
          <p></p>
          <table class="table">
            <thead>
              <tr>
                <th>CODE</th>
                <th>NAME</th>
                <th>DESCRIPTION</th>
                <th>CATEGORY</th>
              </tr>
            </thead>
            <tbody>
              <tr :key="item.name" v-for="item in itemsList">
                <td>{{ item.code }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.description }}</td>
                <td>{{ item.category }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      name: "",
      selectedCategory: "All",
      itemsList: [
        {
          code: "1",
          name: "Automata Theory, Languages, and Computation",
          description: "Definition and exercises",
          category: "Book"
        },
        {
          code: "2",
          name: "Cosmopolitan",
          description: "Magazine for women",
          category: "Magazines"
        },
        {
          code: "3",
          name: "Los Tiempos",
          description: "Newspaper of June 2, 2020",
          category: "Newspapers"
        },
        {
          code: "4",
          name: "Exercising improves mental health",
          description: "Mental Health Articles",
          category: "Others"
        },
        {
          code: "5",
          name: "The Adventures of Sherlock Holmes",
          description: "Fictional story about a detective",
          category: "Book"
        },
        {
          code: "6",
          name: "Opinion",
          description: "Newspaper of June 2, 2020",
          category: "Newspapers"
        }
      ]
    };
  },
  computed: {
    filteredList() {
      return this.itemsList;
    }
  }
};
</script>

<style src="./style.css" scoped></style>
