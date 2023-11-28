<script>
import { store } from "../store";
export default {
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <select 
        v-model="store.selectedOption" 
        class="form-select container" 
        aria-label="Default select example"
        @change="$emit('changeSelect')"
    >
            <option v-if="!store.selectedOption" value="">Select option</option>
            <option>
                Alien
            </option>
            <option>
                Ally of Justice
            </option>
            <option>
                Ancient Gear
            </option>
        </select>
</template>

<style lang="scss" scoped>


</style>