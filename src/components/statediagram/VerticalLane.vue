<template>
    <div
        class="objectDiv"
        @click.stop="setEditingId"
        :style="{minWidth: this.width*0.95 + 'px', minHeight: this.height*0.95 + 'px'}"
        v-clickoutside="hideInputAndSave"
    >
        <div
            class="laneTitle"
            :style="{width: this.width*0.95 + 'px', height: this.height*0.15 + 'px'}"
        >
            <el-input
                class="contentSpan"
                v-model="name"
                v-if="showInput && id == $store.state.editingId"
                size="mini"
                :autofocus="true"
                :style="{marginTop: this.height*0.05 + 'px'}"
            ></el-input>
            <span
                :style="{width: this.width*0.6+'px', maxHeight: this.height*0.2 + 'px', marginTop: this.height*0.05 + 'px'}"
                v-else
                class="contentSpan omitted"
                @click="handleNameClick"
            >{{name}}</span>
        </div>
        <div
            class="laneBody"
            :style="{width: this.width*0.95 + 'px', height: this.height*0.75 + 'px'}"
        ></div>
    </div>
</template>
<script>
import CommonComponent from "../CommonComponent.vue";
export default {
    name: "State",
    extends: CommonComponent,
    data() {
        return {
            name: ""
        };
    },
    watch: {
        properties: {
            deep: true,
            handler(prop) {
                this.name = prop.name;
            }
        },
        name(newName) {
            this.$store.dispatch("modifyNode", {
                nodeKey: "properties",
                key: "name",
                value: newName,
                id: this.id
            });
        }
    },
    methods: {
        hideInputAndSave() {
            this.showInput = false;
            this.setEditStateFalse();
        }
    }
};
</script>
<style scoped>
.laneTitle {
    border: 2px solid black;
    background: white;
}
.laneBody {
    border-left: 2px solid black;
    border-right: 2px solid black;
    border-bottom: 2px solid black;
}
</style>