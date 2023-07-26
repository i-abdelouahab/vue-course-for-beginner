<template>
    <nav>
        <div class="menu">
          <ul>
              <li>
                  <a href="#">
                    <RouterLink to="/home">
                        <span><i class="fas fa-home"></i></span>
                      Home
                    </RouterLink>
                  </a>
              </li>
              <li>
                  <a href="#">
                      <RouterLink to="/about">
                        <span><i class="fas fa-address-card"></i></span>
                        About
                      </RouterLink>
                  </a>
              </li>
          </ul>
        </div>
    </nav>
</template>
<script>
export default {
    name: "SideBar",
}
</script>
<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style: none;
    text-decoration: none;
}

.menu{
    height: 100%;
    position: fixed;
    left: 0;
    top: 0;
    width: 300px;
    padding-top: 60px;
    background-color: #212121; 
    transform: translateX(-250px);
    transition: 0.5s;
    margin-left: 190px;
    position: absolute;
}

ul li{
    border-bottom: 1px solid rgba(255, 255, 255, 0.10);
    transition: 0.3s;
    /*text-align: center;*/
    padding-left: 25px;
}
ul li:hover{
    padding-left: 35px;
    background-color: #445665;
}
ul li a{
    display: block;
    color: #fff;
    padding: 20px;
    text-transform: uppercase;
    font-weight: bold;
}

#open{
    display: none;
}
.open{
    height: 80px;
    width: 80px;
    /*position: absolute;*/
    /*background-color: #000;*/
}
.open i{
    font-size: 25px;
    cursor: pointer;
    margin-left: 25px;
    margin-top: 25px;
    background-color: #000;
    padding: 15px 15px;
    color: white;
    z-index: 99;
}

</style>