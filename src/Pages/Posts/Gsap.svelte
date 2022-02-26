<script>
    import gsap from "gsap";

    let hello = "";

    function playme() {
        gsap.to(".box", {
            duration: 1,
            opacity: 0,
        });
    }
    function resetme() {
        gsap.to(".box", {
            duration: 1,
            opacity: 1,
        });
    }
    function sayhello() {
        if (hello.length > 0) {
            hello = "";
        } else {
            hello = "hello";
        }
    }
</script>

<div
    class="box"
    on:click={sayhello}
    on:mouseover={playme}
    on:mouseout={resetme}
/>

<div>{hello}</div>

<style>
    .box {
        width: 100px;
        height: 100px;
        background: black;
        cursor: pointer;
    }
</style>
