<template>
    <button :class="mode"><slot></slot></button>
</template>

<script>
    export default {
        props: ['type', 'mode']
}
</script>

<style scoped>
    button{
        color: #fff;
        text-transform: uppercase;
        text-decoration: none;
        background: #60a3bc;
        padding: 20px;
        border-radius: 12px;
        display: inline-block;
        border: none;
        transition: all 0.4s ease 0s;
        cursor: pointer;
    }
    button:hover {
        text-shadow: 0px 0px 5px rgba(255, 255, 255, 1);
        box-shadow: orchid;
        -webkit-box-shadow: 0px 5px 20px -10px rgba(0,0,0,0.57);
        -moz-box-shadow: 0px 5px 20px -10px rgba(0,0,0,0.57);
        transition: all 0.4s ease 0s;
    }
    .flat {
        background-color: transparent;
        color: #1b0004;
        border: none;
    }
    .flat:hover,
    .flat:active {
        background-color: #640032;
        color: white;
    }

</style>