<template>
    <div>
        <div>
            <h1>Flask+Vue</h1>
            <h2>
                {{items}}
            </h2>
        </div>
    </div>
</template>
<script>
/* eslint-disable */
    export default {
        data() {
            return {
                
                items: ['']
            }
        },
        methods: {
            async getData() {
                try {
                    
                    const response = await this.$http.get('http://localhost:5000/')
                    
                    this.items = response.data
                    console.log(this.items.message)
                } catch (error) {
                    // log the error
                    console.log(error);
                }
            }
        },
        created() {
            
            this.getData()
        }
    }
</script>