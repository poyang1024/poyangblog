<template>
    <header :class="{ 'scrolled-nav' : scrollNav}" >
        <nav>
            <div class="branding">
                <img src="../assets/code.png" alt="">
            </div>
            <ul v-show="!mobile" class="navigation">
                <li><router-link class="link" :to="{name: 'home'}">Home</router-link></li>
                <li><router-link class="link" :to="{name: ''}">About</router-link></li>
                <li><router-link class="link" :to="{name: ''}">profolio</router-link></li>
                <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
            </ul>
            <div class="icon">
                <i @click.stop="toggleMobileNav" v-show="mobile" class="fas fa-bars" :class="{ 'icon-active': mobileNav }"></i>
            </div>
            <transition name="mobile-nav">
                <ul v-show="mobileNav" class="dropdown-nav">
                    <li><router-link class="link" :to="{name: 'home'}">Home</router-link></li>
                    <li><router-link class="link" :to="{name: ''}">About</router-link></li>
                    <li><router-link class="link" :to="{name: ''}">profolio</router-link></li>
                    <li><router-link class="link" :to="{name: ''}">Contact</router-link></li>
                </ul>
            </transition>
        </nav>
    </header>
  </template>
  
  <script>
    export default {
        name: 'Navigation',
        data() {
            return {
                mobile: null,
                mobileNav: null,
                scrollNav: null,
                windowWidth:null,
            };
        },
        created() {
            window.addEventListener("resize", this.checkScreen);
            this.checkScreen();
        },

        mounted() {
            window.addEventListener("scroll", this.updateScroll);
        },
        methods: {
            toggleMobileNav() {
                this.mobileNav = !this.mobileNav;
            }, 
            toggleMobileNavHome(e) {
                let self = this;
                    if (self.mobileNav == true){
                        self.mobileNav = false;
                    }
            },
            updateScroll(){
                const scrollPosition = window.scrollY;
                if(scrollPosition > 50){
                    this.scrollNav = true;
                    return;
                }
                this.scrollNav = false;
            },

            checkScreen(){
                this.windowWidth = window.innerWidth;
                if(this.windowWidth <= 750){
                    this.mobile = true;
                    return;
                }
                this.mobile = false; 
                this.mobileNav = false;
                return;
            },
        },
    }
  </script>
  
  <style lang="scss" scoped>
    header {
      background-color: #042e58;
      opacity: .95;
      z-index: 99;
      width: 100%;
      position: fixed;
      transition: .5s ease all;
      color: #fff;
      
      nav {
        position: relative;
        display: flex;
        flex-direction: row;
        padding: 12px 0;
        transition: .5s ease all;
        width: 90%;
        margin: 0 auto;
        @media (min-width: 1240px){
            max-width: 1240px;
        }

        ul,
        .link {
          font-weight: 500;
          color: #fff;
          list-style: none;
          text-decoration: none;
        }

        li{
            text-transform: uppercase;
            padding: 16px;
            margin-left: 16px;
        }

        .link {
            font-size: 14px;
            transition: .5s ease all;
            padding-bottom: 4px;
            border-bottom: 1px solid transparent;

            &:hover {
                color: #fa8b4c;
                border-color: #fa8b4c;
                cursor: pointer;
            } 
        }
        .branding {
            display: flex;
            align-items: center;

            img {
                width: 50px;
                transition: .5s ease all; 
                &:hover {
                    cursor:pointer;
                } 
            }
        }

        .navigation {
            display: flex;
            align-items: center;
            flex: 1;
            justify-content: flex-end;
            margin-left: auto;
        }

        .icon{
            display: flex;
            align-items: center;
            position: absolute;
            top: 0;
            right: 24px;
            height: 100%;
            
            i{
                font-size: 24px;
                cursor: pointer;
                transition: .8s ease all;
                &.icon-active {
                    color: #fff;
                }
            }
        }
        .icon-active {
            transform: rotate(180deg);
        }

        .dropdown-nav {
            margin : 0;
            display: flex;
            flex-direction: column;
            position: fixed;
            width: 100%;
            max-width: 250px;
            height: 100%;
            top: 0;
            left: 0;
            background-color: #fff;

            li{
                margin-left: 0;
                .link {
                    color: #000;
                }
            }
        }

        .mobile-nav-enter-active{
            transition: 1s ease all;
        }
        .mobile-nav-leave-active {
            transition: 1.8s ease all;
        }

        .mobile-nav-enter-from, .mobile-nav-leave-to{
            transform: translateX(-290px);
        }

        .mobile-nav-enter-to{
            transform: translateX(0);
        }


    }
    }
     
    .scrolled-nav{
        background-color: #042e58;
        opacity: 1;
        box-shadow: 0 4px 6px -1px #042e58, 0 2px 4px -1px #042e58;

        nav{
            padding: 8px 0;

            .branding img{
                img{
                    width: 40px; 
                    box-shadow: 0 4px 6px -1px #042e58, 0 2px 4px -1px #042e58;
                }
            }
        }
    }
  
</style>






  