<template src="./template.html"/>

<script>
    export default {
        name: "ChatAddRoom",
        props: ['indexRoom'],
        beforeMount() {
            this.room = {...this.defaultRoom}
        },
        data() {
            return {
                room: null,
                defaultRoom: {
                    title: '',
                }
            }
        },
        methods: {
            closeAddRoom() {
                this.room = null;
                this.$emit('closeAddRoom');
            },
            addRoom() {
                this.$emit('addRoom', {id: this.indexRoom, ...this.room});
                this.room = null;
                this.closeAddRoom()
            }
        }
    }
</script>

<style scoped src="./style.less" lang="less">

</style>