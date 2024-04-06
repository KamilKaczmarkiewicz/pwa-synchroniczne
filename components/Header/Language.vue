<template>
    <div class="language">
      <select class="language-select" aria-label="Wybierz język">
        <option value="pl">PL</option>
        <option value="en">EN</option>
        <option value="de">DE</option>
      </select>
    </div>
  </template>
  
  <style>
  .language {
    display: grid;
    position: relative;
    height: 26px;
  }
  .language::after {
    content: "";
    position: absolute;
    top: 7px;
    right: 5px;
    width: 10px;
    height: 6px;
    background-color: black;
    clip-path: polygon(100% 0%, 0 0%, 50% 100%);
  }
  .language-select {
    height: 20px;
    appearance: none;
    cursor: pointer;
    padding: 0px 18px 0px 5px;
    border: 1px solid black;
    font-family: "Bitter", sans-serif;
    font-size: 10px;
    font-weight: 600;
  }
  </style>