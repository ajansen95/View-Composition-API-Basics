<template>
    <div class="posts">
        <h1>Posts</h1>

        <ul>
            <li v-for="post in posts" :key="post.id">
                <RouterLink :to="`/postDetail/${post.id}`">{{post.title}}</RouterLink>
            </li>
        </ul>

        <textarea v-autofocus></textarea>
    </div>
</template>


<script setup>
/*
    imports
 */

    import {vAutofocus} from "@/directives/vAutofocus";
import {ref} from "vue";

/*
    posts
*/
    const posts = ref([
        {
            id: 'id1',
            title: 'Post1'
        },
        {
            id: 'id2',
            title: 'Post2'
        },
        {
            id: 'id3',
            title: 'Post3'
        }
    ])


</script>


<style>
ul{
    margin-bottom: 30px;
}
</style>
