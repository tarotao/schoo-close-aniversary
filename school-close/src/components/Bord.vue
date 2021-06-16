<template>
    <section>
        <v-container>
            <v-row>
                <v-col>
                    <header>
                        <v-app-bar
                            app
                            color="green"
                        >
                            <h1>掲示板</h1>
                        </v-app-bar>
                    </header>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                   <ul class="lists" style="list-styl-type: none">
                        <BordList v-for= "(list, index) in lists" :key="index"
                            :user = "list.user"
                            :date = "list.date"
                            :message = "list.message"
                        />
                    </ul>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                    <p class="user-title">名前:</p><input v-model="user"><br>
                    <p class="message-title">コメント</p>
                    <textarea v-model="message"></textarea> <br>
                    <v-btn v-on:click="doAdd" color="accent" class="btn">送信</v-btn>
                </v-col>
            </v-row>
        </v-container>
    </section>
</template>

<script>
import BordList from './BordList.vue'
export default {
  name: 'Bord',
  components: {
    BordList
  },
  data () {
    return {
      user: '',
      date: '',
      message: '',
      lists: [
      ]
    }
  },
  methods: {
    doAdd () {
      var now = new Date()
      this.lists.push({
        user: this.user,
        date: now.getMonth() + 1 + '月' + now.getDate() + '日' + now.getHours() + '時' + now.getMinutes() + '分',
        message: this.message
      })
      this.user = ''
      this.message = ''
    }
  }
}
</script>

<style lang="scss" scoped>
textarea, input {
    border-style: solid;
}
h1 {
    color: white;
}
.user-title {
    display: inline;
    margin-right: 10px;
}
.message-title {
    margin-top: 15px;
}
.lists {
    margin: 70px 0
}
.btn {
    margin-top:20px
}
</style>
