<template>
        <div class="wrapper">
            <parallax class="page-header header-filter" :style="headerStyle">
                <div class="md-layout">
                    <div class="md-layout-item">
                        <div class="image-wrapper">
                            <img :src="leaf4" alt="leaf4" class="leaf4" v-show="leafShow" />
                            <img :src="leaf3" alt="leaf3" class="leaf3" v-show="leafShow" />
                            <img :src="leaf2" alt="leaf2" class="leaf2" v-show="leafShow" />
                            <img :src="leaf1" alt="leaf1" class="leaf1" v-show="leafShow" />
                            <div class="brand">
                                <h1>Song name</h1>
                                <h3>{{this.firstname}}</h3>
                            </div>
                        </div>
                    </div>
                </div>
            </parallax>
        </div>

</template>
<script>
export default {
    name:'music',
    bodyClass: "index-page",
    props: {
        firstname:{type:String, default:"test"},
        image: {
            type: String,
            default: require("@/assets/img/vue-mk-header.jpg")
        },
        leaf4: {
            type: String,
            default: require("@/assets/img/leaf4.png")
        },
        leaf3: {
            type: String,
            default: require("@/assets/img/leaf3.png")
        },
        leaf2: {
            type: String,
            default: require("@/assets/img/leaf2.png")
        },
        leaf1: {
            type: String,
            default: require("@/assets/img/leaf1.png")
        },
        signup: {
            type: String,
            default: require("@/assets/img/city.jpg")
        },
        landing: {
            type: String,
            default: require("@/assets/img/landing.jpg")
        },
        profile: {
            type: String,
            default: require("@/assets/img/profile.jpg")
        }
    },
    methods: {
        leafActive() {
            if (window.innerWidth < 768) {
                this.leafShow = false;
            } else {
                this.leafShow = true;
            }
        }
    },
    computed: {
        headerStyle() {
            return {
                backgroundImage: `url(${this.image})`
            };
        },
        signupImage() {
            return {
                backgroundImage: `url(${this.signup})`
            };
        }
    },
    mounted() {
        console.log(this.firstname);
        this.leafActive();
        window.addEventListener("resize", this.leafActive);
    },
    beforeDestroy() {
        window.removeEventListener("resize", this.leafActive);
    }
};
</script>
<style lang="scss">
    .section-download {
        .md-button + .md-button {
            margin-left: 5px;
        }
    }

    @media all and (min-width: 991px) {
        .btn-container {
            display: flex;
        }
    }
</style>
