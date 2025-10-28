<script>
    export default {
        // Add code if/as necessary
        // Hint: Add properties subject, entry and mood
        props: ['post']
    }
</script>


<template>
    <!-- TODO: add your template code here Use boostrap card --> 
    <div class="card" style="width: 18rem;">
        <img class="card-img-top" :src="`/assets/${post.mood.toLowerCase()}.png`" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{post.subject}}</h5>
            <p class="card-text">{{post.entry}}</p>
        </div>
        <slot></slot>
    </div>
    
</template>

