<template>
  <section class="container posts-page">
    <el-card style="flex: 1">
      <div 
        slot="header" 
        class="clearfix">
        <span>新着投稿</span>
      </div>
      <el-table
        :data="showPosts"
        style="width: 100%"
        class="table"
        @row-click="handleClick"
      >
        <el-table-column
          prop="title"
          label="タイトル">
          <div slot-scope="scope">
            <span>{{ scope.row.title }}&nbsp;</span>
            <span>
              <i class="el-icon-star-on" />
              <span>{{ scope.row.likes.length }}</span>
            </span>
          </div>
        </el-table-column>
        <el-table-column
          prop="user.id"
          label="投稿者"
          width="180"/>
        <el-table-column
          prop="created_at"
          label="投稿日時"
          width="240"/>
      </el-table>
    </el-card>
  </section>
</template>

<script>
export default {
  computed: {
    showPosts() {
      return [
        {
          id: '001',
          title: 'aieuo',
          body: 'あいえうお',
          created_at: '2018/01/12 12:00:00',
          user: {
            id: 'aiueo'
          }
        },
        {
          id: '002',
          title: 'aieuo',
          body: 'あいえうお',
          created_at: '2018/01/12 12:00:00',
          user: {
            id: 'kakikukeko'
          }
        }
      ]
    }
  }
}
</script>


<style>
.posts-page .el-table__row {
  cursor: pointer;
}
</style>
