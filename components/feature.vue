<template>
    <div class="feature flex">
            <div class="feature-image flex middle">
                <img :src="featureImg" :alt="featureAlt">
            </div>
            <div class="feature-content flex center-column-left">
                <div class="feature-title">
                    <h2>{{projectTitle}}</h2>
                    <p>{{projectDes}}</p>
                    <nuxt-link class="flex center case-study" to="">
                        View Case Study 
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M9 18L15 12L9 6" stroke="#1E1E1C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </nuxt-link>
                </div>
            </div>
    </div>
</template>


<script>
export default {
    name: 'feature',
    props: [
        'projectTitle',
        'projectDes',
        'featureImg',
        'featureAlt'
    ]
}
</script>


<style lang="scss" scoped>

.feature {
    margin: 0 0 160px 0;
    justify-content: space-between;
    min-width: 100%;
    .feature-content {
        margin-top: 120px;
        max-width: 340px;
        .feature-title {
            max-width: 100%;
        }
        p {
            margin-top: 8px;
            max-width: 100%;
        }
        a {
            margin-top: 40px;
            svg {
                margin-left: 8px;
            }
        }
    }
    .feature-image {
        justify-content: center;
        background-color: $card-bkg;
        padding: 120px;
        min-width: 65%;
        max-width: 65%;
        img {
            height: 24vw;
            // margin: 120px;
        }
    }
    @media only screen and (max-width: 1440px) {
        .feature-content {
            p {
                max-width: 340px;
                margin: 16px 0;
            }
        }
    }
    @media only screen and (max-width: 768px) {
        padding: 40px;
        flex-flow: column;
        width: 100vw;
        margin: 0 0 40px 0;
        .feature-content {
            width: 100%;
            margin-top: 24px;
            text-align: center;
            display: flex;
            flex-flow: column;
            align-items: center;
            p {
                max-width: 450px;
                margin: 16px 0;
            }
        }
        .feature-image {
            height: 160px;
            img {
                margin-left: 64px;
            }
        }
    }
    @media only screen and (max-width: 450px) {
        .feature-image {
            height: 120px;
            img {
                margin-left: 40px;
            }
        }
    }
}

.switch {
    div:first-child {
        order: 2;
    }
    // div:nth-child(2) {
    //     order: 1;
    // }
    // @media only screen and (max-width: 768px) {
    //     background-color: rgba($color: $main-blue, $alpha: .1);
    //     div:first-child {
    //         order: 1;
    //     }
    //     div:nth-child(2) {
    //         order: 2;
    //     }
    // }
}

.dark-image {
    .feature-image {
        background: #131313;
    }
}

.blue-image {
    .feature-image {
        background: $main-blue;
    }
}

.low-image {
    .feature-image {
        padding-bottom: 0px;
        img {
            margin-top: 120px;
        }
    }
}
    
</style>