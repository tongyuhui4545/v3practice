<template>
    <Card>
        <form>
            <h2>How would you rate your service with us?</h2>
            <!-- Rating -->
            <rating-select :rating="rating" />
            <div class="input-group">
                <input type="text" placeholder="Write a review" v-model="text">
                <button type="submit" class="btn btn-primary" :disabled="btnDisabled"></button>
            </div>
            <div class="message" v-if="message !== ''">
                Text must be at least 10 characters
            </div>
        </form>
    </Card>
</template>

<script setup>
import Card from "./shared/Card.vue";
import RatingSelect from "./shared/RatingSelect.vue";
import {ref} from "vue";

const text = ref('');
const btnDisabled = ref(false);
const message = ref('');
const rating = ref(10);

const setRating = (val) => {
    rating.value = val;
}
</script>

<style scoped>
</style>