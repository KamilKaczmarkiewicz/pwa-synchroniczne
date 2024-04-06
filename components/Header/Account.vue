<template>
  <div class="user-profile">
    <NuxtLink to="/">
      <img
        class="user-profile-icon"
        src="/icons/account.svg"
        alt="Account"
      />
    </NuxtLink>
  </div>
</template>

<style>
.user-profile {
  height: 26px;
}

.user-profile-icon {
  cursor: pointer;
  opacity: 0.8;
}
</style>
  