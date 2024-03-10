<template>
    <div class="image-gallery" style="padding-bottom: 40px;">
      <div class="buttons-row" v-for="(row, index) in buttonRows" :key="index">
        <div class="button" v-for="button in row" :key="button">
          <button @click="handleButtonClick(button)">{{ button }}</button>
        </div>
      </div>
      <div class="pagination">
        <button @click="previousPage" :disabled="currentPage === 1">Previous</button>
        <button @click="nextPage" :disabled="currentPage === totalPages">Next</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        buttons: Array.from({ length: 15 }, (_, index) => index + 1), 
        itemsPerRow: 2, 
        itemsPerPage: 6, 
        currentPage: 1 
      };
    },
    computed: {
      buttonRows() {
        const startIndex = (this.currentPage - 1) * this.itemsPerPage;
        const endIndex = Math.min(startIndex + this.itemsPerPage, this.buttons.length);
        const buttonsToShow = this.buttons.slice(startIndex, endIndex);
  
        const rows = [];
        for (let i = 0; i < buttonsToShow.length; i += this.itemsPerRow) {
          rows.push(buttonsToShow.slice(i, i + this.itemsPerRow));
        }
  
        return rows;
      },
      totalPages() {
        return Math.ceil(this.buttons.length / this.itemsPerPage);
      }
    },
    methods: {
      previousPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
        }
      },
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
        }
      },
      handleButtonClick(button) {
        console.log("Clicked button " + button);
      }
    }
  };
  </script>
  
  <style scoped>
  .image-gallery {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .buttons-row {
    display: flex;
    justify-content: center;
  }
  
  .button {
    margin: 5px;
  }
  
  .pagination {
    margin-top: 20px;
    display: flex;
    justify-content: center;
  }
  
  button {
    margin: 0 5px;
  }
  </style>
  