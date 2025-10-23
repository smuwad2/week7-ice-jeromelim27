<script>
import axios from 'axios';

    export default { 

       // add code here
        data(){
            return{
                moods: ["happy", "sad", "Angry"],
                subject: "",
                entry:"",
                mood:""

            }
        },
        methods: {
            addPost(){
                axios.post("http://localhost:3000/addPost",{
                    subject: this.subject,
                    entry: this.entry,
                    mood: this.mood
                })
                .catch(error => {console.log(error.message)})
            }
        }
    }
    
</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
         <select v-model = "mood">
            <option v-for = "mood in moods">{{ mood }}</option>
         </select>

        <br>

        <br>
        <button @click = "addPost">Submit New Post</button>

        <hr> Click  <a><router-link to="/ViewPosts/">here</router-link></a>  to return to Main Page
       
    </div>
</template>

