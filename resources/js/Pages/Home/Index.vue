<template>
    <div>
        <h1>Hello {{ name }}</h1>
    </div>
</template>
<script>
import Default from "../Layout/Default";

export default {
    layout: Default,
    props: {
        name: String,
    },
    setup(props, { attr, slots, emit }) {
        window.Echo.channel("test-channel").listen("TestEvent", (e) => {
            console.log(e);
        });
    },
};
</script>