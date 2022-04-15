<template>
  <layout-p />
</template>
<script>
import LayoutP from "./components/LayoutP";
export default {
  components: {
    LayoutP,
  },
  data() {},
};
</script>

<style>
.container {
  width: 80%;
  margin: 0 auto;
  font-family: Arial, Helvetica, sans-serif;
}
.navbar {
  margin: 35px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.list {
  list-style: none;
  display: flex;
  justify-content: space-around;
}
.list > li {
  margin: 0 15px;
  cursor: pointer;
  color: #303446;
}
.navbar img {
  width: 150px;
  height: 50px;
}
.btn button {
  background-color: #4caf50; /* Green */
  border: none;
  border-radius: 10px;
  color: white;
  font-weight: bold;
  padding: 15px 28px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
.container-fluid {
  margin: 0;
  padding: 0;
  background-image: url("./images/girl.jpg");
}
.left-section {
  width: 30%;
}
.left-section p {
  margin: 30px 0;
}
.left-section {
  color: white;
}
.btn_tracking {
  background-color: #4caf50; /* Green */
  border: none;
  border-radius: 10px;
  color: white;
  font-weight: bold;
  padding: 15px 28px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-right: 20px;
}
.btn_again {
  border: none;
  padding-bottom: 3px;
  font-weight: bold;
  /* background-color: #fff; */
  border-bottom: 1px solid rgb(22, 22, 22);
}
.flex-number {
  padding: 40px 0;
  color: white;
  display: flex;
  text-align: center;
  justify-content: space-around;
  opacity: 1.9;
}
.section {
  margin: 100px 0;
  padding-right: 150px;
}
.left-section-2 {
  width: 30%;
}
.right-section {
  margin-left: 400px;
}
.page {
  display: flex;
  justify-content: flex-start;
}
.color-parag {
  color: #aaa3bf;
}
.btn-reference {
  background-color: #4caf50; /* Green */
  border: none;
  border-radius: 10px;
  color: white;
  font-weight: bold;
  padding: 15px 28px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-right: 20px;
}
.usta-img {
  position: absolute;
  width: 400px;
  height: 420px;
  border-radius: 10px;
  /* margin-right: 100px */
}
.usta-relative {
  position: relative;
  top: 200px;
  right: 100px;
  width: 250px;
  height: 280px;
  border-radius: 10px;
}
</style>
