<template>
  <div class="components-container board">
    <Kanban :key="1" :list="list1" :group="group" class="kanban mon" header-text="Monday" />
    <Kanban :key="2" :list="list2" :group="group" class="kanban tue" header-text="Tuesday" />
    <Kanban :key="3" :list="list3" :group="group" class="kanban wed" header-text="Wednesday" />
    <Kanban :key="4" :list="list4" :group="group" class="kanban thu" header-text="Thursday" />
    <Kanban :key="5" :list="list5" :group="group" class="kanban fri" header-text="Friday" />
    <Kanban :key="6" :list="list6" :group="group" class="kanban sat" header-text="Saturday" />
  </div>
</template>
<script>
import Kanban from '@/components/Kanban'

export default {
  name: 'DragKanbanDemo',
  components: {
    Kanban
  },
  data() {
    return {
      group: 'mission',
      list1: [
        { name: 'Course', id: 1 },
        { name: 'Course', id: 2 },
        { name: 'Course', id: 3 },
        { name: 'Course', id: 4 }
      ],
      list2: [
        { name: 'Course', id: 5 },
        { name: 'Course', id: 6 },
        { name: 'Course', id: 7 }
      ],
      list3: [
        { name: 'Course', id: 8 },
        { name: 'Course', id: 9 },
        { name: 'Course', id: 10 }
      ],
      list4: [
        { name: 'Course', id: 11 },
        { name: 'Course', id: 12 }
      ],
      list5: [
        { name: 'Course', id: 13 }
      ],
      list6: [

      ]
    }
  }
}
</script>
<style lang="scss">
.board {
  width: 1000px;
  margin-left: 20px;
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  align-items: flex-start;
}
.kanban {
  &.mon {
    .board-column-header {
      background: #4A9FF9;
    }
  }
  &.tue {
    .board-column-header {
      background: #f9944a;
    }
  }
  &.wed {
    .board-column-header {
      background: #2ac06d;
    }
  }
  &.thu {
    .board-column-header {
      background: #f9944a;
    }
  }
  &.fri {
    .board-column-header {
      background: #4A9FF9;
    }
  }
  &.sat {
    .board-column-header {
      background: #2ac06d;
    }
  }
}
</style>

