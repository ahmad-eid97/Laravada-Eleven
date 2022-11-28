<template>
    <section class="services">
        <div class="row m-0">
            <div v-for="service in services.slice(0, 3)" :key="service.id" class="col-md-6 col-lg-4 service">
                <div class="icon">
                    <font-awesome-icon :icon="service.item" />
                </div>
                <h4>{{service.title}}</h4>
                <p>
                    {{service.short_description}}
                </p>
                <div>
                    <a href="#" class="btn">
                        Contact us
                        <font-awesome-icon icon="fa-solid fa-arrow-right" />
                    </a>
                </div>
            </div>
        </div>
    </section>
  
</template>

<script>
export default {
    name: 'AppHomeServices',
    props: ["services"]
}
</script>

<style>
    .services {
        background-color: rgb(117, 179, 37);
        padding: 40px 50px;
    }
    .services .service {
        text-align: center;
        display: flex;
        justify-content: center;
        flex-direction: column;

    }
    .services .service:nth-of-type(2) {
        border-right: 4px dashed #a0cb69;
        border-left: 4px dashed #a0cb69;
    }
    .services .service .icon {
        width: 128px;
        height: 128px;
        border: 4px solid #a0cb69;
        padding: 20px;
        line-height: 118px;
        margin: 0 auto;
    }
    .services .service .icon svg{
        font-size: 64px;
        color: #fff;
    }
    .services .service h4{
        color: rgb(255, 255, 255);
        font-size: 20px;
        font-weight: 700;
        line-height: 26px;
        margin-bottom: 10px;
        margin-top: 15px;
        text-align: center;
    }
    .services .service p{
        color: rgb(255, 255, 255);
        font-size: 15px;
        font-weight: 400;
        line-height: 25.5px;
        text-align: center;
    }
    .services .service .btn{
        background-color: #91c251;
        border-radius: 3px;
        border: none;
        color: rgb(255, 255, 255);
        cursor: pointer;
        font-size: 15px;
        font-weight: 700;
        height: 50px;
        line-height: 20px;
        padding-bottom: 15px;
        padding-left: 35px;
        padding-right: 35px;
        padding-top: 15px;
        margin-bottom: 10px;
        margin-left: 0px;
        margin-right: 10px;
        margin-top: 0px;
        min-width: 160px;
    }
    .services .service .btn:hover{
        background-color: rgb(160, 209, 95);
        color: rgb(255, 255, 255);

    }
</style>