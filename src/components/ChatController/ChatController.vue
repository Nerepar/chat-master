<template src="./template.html"/>

<script>
import ChatAddRoom from "@/components/ChatAddRoom/ChatAddRoom";
import RoomStorage from "@/components/RoomStorage/RoomStorage";

export default {
  name: "ChatController",
  components: {
    ChatAddRoom, RoomStorage
  },
  data() {
    return {
      addFormVisible: false,
      indexRoom: 0,
      props: ['data'],
      desk: [
          {
        title: 'Комнаты',
        rooms: []
        },
      ],
    };
  },
  methods: {
    addRoomClick() {
      this.addFormVisible = true
    },
    closeAddRoom() {
      this.addFormVisible = false
    },
    addRoom(roomData) {
      this.indexRoom++;
      this.desk[0].rooms.push(roomData)
    }
  }
}
</script>

<style scoped src="./style.less" lang="less">

</style>