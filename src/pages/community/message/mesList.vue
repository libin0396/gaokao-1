<template>
  <div class="list-container">
    <headTop title="我的消息" :showLeft='false'></headTop>
    <div class="scroll-container">
      <conversation-item
        :conversation="item"
        v-for="item in conversationList"
        :key="item.conversationID"
      />
    </div>
    <footGuide></footGuide>
  </div>
</template>

<script>
import headTop from '@/components/common/header'
import footGuide from '@/components/common/footer'
import ConversationItem from './curMes'
import { mapState } from 'vuex'
export default {
  name: 'ConversationList',
  components: {
    ConversationItem,
    headTop,
    footGuide
  },
  data () {
    return {
    }
  },
  computed: {
    ...mapState({
      conversationList: state => state.conversation.conversationList
    })
  }
}
</script>

<style lang="scss" scoped>
@import '../../../style/mixin';
.list-container {
  padding-top: 60px;
}
.scroll-container {
  overflow-y: scroll;
  flex: 1;
}
</style>
