<template>
  <div class="navbar flex poppins-medium ">
    <div class="flex gap-md items-center">
      <FontAwesomeIcon :class="[iconSize]" :icon="faBars" />
      <div class="icon-container">
        <FontAwesomeIcon :class="['light', iconSize]" :icon="faEnvelope" />
        <span class="badge green">10</span>
      </div>
      <div class="icon-container">
        <FontAwesomeIcon :class="['light', iconSize]" :icon="faBell" />
        <span class="badge purple">15</span>
      </div>
      <div class="flex gap-sm items-center">
        <img class="flag-img" src="../assets/640px-Flag_of_the_United_Kingdom.svg.png" alt="flag" />
        <p>English</p>
      </div>
    </div>
    <div class="flex gap-md items-center">
      <FontAwesomeIcon :class="['light', iconSize]" :icon="faSearch" />
      <div class="flex gap-sm items-center dropdown">
        <img class="profile-img" src="../assets/androgynous-avatar-non-binary-queer-person.jpg" alt="profile image" />
        <p class="light name">Raghava</p>
        <FontAwesomeIcon :class="['light', iconSize]" :icon="faCaretSquareDown" />
        <div class="dropdown-content">
          <p class="light dropdown-name">Raghava</p>
          <a href="#">Profile</a>
          <a href="#">Settings</a>
          <a href="#">Logout</a>
        </div>
      </div>
      <FontAwesomeIcon :class="['light', iconSize]" :icon="faComments" />
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faBell, faComments, faEnvelope, faUser, faCaretSquareDown } from '@fortawesome/free-regular-svg-icons';
import { faBars, faSearch } from '@fortawesome/free-solid-svg-icons';

export default {
  name: 'NavBar',
  components: {
    FontAwesomeIcon
  },
  data() {
    return {
      faEnvelope,
      faBars,
      faBell,
      faSearch,
      faUser,
      faComments,
      faCaretSquareDown
    }
  }
}
</script>

<style scoped>
.navbar {
  background-color: white;
  padding: 20px;
  justify-content: space-between;
}

.items-center {
  align-items: center;
}

.flex {
  display: flex;
}

.gap-md {
  gap: 20px;
}

.gap-sm {
  gap: 10px;
}

.flag-img {
  width: 25px;
  height: 15px;
}
.profile-img{
  width: 25px;
  height: 25px;
  border-radius:50%;
}


.iconSize {
  width: 25px;
  height: 25px;
}

.light {
  color: rgba(172, 166, 161, 255);
}

.icon-container {
  position: relative;
}

.badge {
  position: absolute;
  top: -5px;
  right: -10px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.green {
  background-color: green;
}

.purple {
  background-color: purple;
}

.green,
.purple {
  font-size: 8px;
  font-weight: 900;
  color: white;
  padding: 2px 2px 0 2px;
}

.dropdown {
  position: relative;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: white;
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
  border-radius: 10px;
  padding: 12px 16px;
  z-index: 1;
  top: 30px;
  right: 0;
  width: 150px;
}

.dropdown-content a {
  color: black;
  padding: 8px 12px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #f1f1f1;
}

.dropdown:hover .dropdown-content {
  display: block;
}

@media (max-width: 400px) {
  .name {
    display: none;
  }
  .dropdown-content .dropdown-name {
    display: block;
  }
}
</style>
