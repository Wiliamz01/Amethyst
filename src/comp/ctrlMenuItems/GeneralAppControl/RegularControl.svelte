<script lang="ts">
    export let imageURI : string;
    export let alt : string;
    export let cta : (any) => any = () => {};
</script>

<main on:click={cta} title={alt}>
    <img src={imageURI} alt={alt}>
</main>

<style lang="scss">
    @import "../public/global";
    
    main{
        height:40px; width:55px;
        border-radius: 7px;
        margin-right: 5px;
        display: flex; align-items: center; justify-content: center;
        cursor: pointer;
        transition: background-color 200ms ease;

        img{
            filter: invert(1) brightness(0.5);
            height:24px;
            transition: filter 200ms ease;
            user-select: none; -webkit-user-select: none; -webkit-user-drag: none;
        }

        &:hover{
            background-color: hsla(0,0%,100%,10%);
            img{
                filter: invert(1) brightness(0.6);
            }
        }

        &.multi{
            width:65px;  
            
            .more-options{
                height:20px;
                transform: translate3d(2px,0px,0px);
            }
        }
    }
</style>