<template>
   <div>
      <div v-for="post in posts" :key="post.id">
         <p>PostID :{{post.id}}</p>
         <p>Post Title: {{ post.title }}</p>
         <p>Post Content: {{post.content}}</p>

         <div v-if="post.video">
            <p>Video title: {{ post.video.title }}</p>
            <p>Video URL: {{ post.video.url }} </p>
            <!-- <iframe width="560" height="315" :src="post.video.url" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -->
         </div>
         <br><br><hr>
      </div>
   </div>
</template>

<script>
export default {
   data() {
      return {
         posts: [],
         posts1: [
            {
            "id": 1,
            "title": "Post 1",
            "slug": "first-post",
            "content": "# Descripción del post 1\n\n**Probando**\n\n```\n  const export loco = () => {\n  }\n```\n\n![2012-22-skul-the-hero-slayer-switch-00 (1).jpg](/uploads/2012_22_skul_the_hero_slayer_switch_00_1_c90b95b056.jpg)\n\n\n",
            "video": null,
            "published_at": "2021-10-07T01:32:24.941Z",
            "created_at": "2021-10-07T01:32:11.799Z",
            "updated_at": "2021-10-07T01:40:15.654Z",
            "image": {
               "id": 2,
               "name": "Cyberpunk2077_GlobalGameUnlockMap_EN_uja9kdfasgnkqkcm.png",
               "alternativeText": "",
               "caption": "",
               "width": 1920,
               "height": 1080,
               "formats": {
               "thumbnail": {
               "name": "thumbnail_Cyberpunk2077_GlobalGameUnlockMap_EN_uja9kdfasgnkqkcm.png",
               "hash": "thumbnail_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0",
               "ext": ".png",
               "mime": "image/png",
               "width": 245,
               "height": 138,
               "size": 39.71,
               "path": null,
               "url": "/uploads/thumbnail_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0.png"
               },
               "large": {
               "name": "large_Cyberpunk2077_GlobalGameUnlockMap_EN_uja9kdfasgnkqkcm.png",
               "hash": "large_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0",
               "ext": ".png",
               "mime": "image/png",
               "width": 1000,
               "height": 563,
               "size": 339.93,
               "path": null,
               "url": "/uploads/large_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0.png"
               },
               "medium": {
               "name": "medium_Cyberpunk2077_GlobalGameUnlockMap_EN_uja9kdfasgnkqkcm.png",
               "hash": "medium_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0",
               "ext": ".png",
               "mime": "image/png",
               "width": 750,
               "height": 422,
               "size": 228.1,
               "path": null,
               "url": "/uploads/medium_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0.png"
               },
               "small": {
               "name": "small_Cyberpunk2077_GlobalGameUnlockMap_EN_uja9kdfasgnkqkcm.png",
               "hash": "small_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0",
               "ext": ".png",
               "mime": "image/png",
               "width": 500,
               "height": 281,
               "size": 128.79,
               "path": null,
               "url": "/uploads/small_Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0.png"
               }
               },
               "hash": "Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0",
               "ext": ".png",
               "mime": "image/png",
               "size": 359.15,
               "url": "/uploads/Cyberpunk2077_Global_Game_Unlock_Map_EN_uja9kdfasgnkqkcm_108f7b0ed0.png",
               "previewUrl": null,
               "provider": "local",
               "provider_metadata": null,
               "created_at": "2021-10-07T01:31:00.722Z",
               "updated_at": "2021-10-07T01:31:00.731Z"
            }
            },
            {
            "id": 2,
            "title": "Todo sobre los huracanes",
            "slug": null,
            "content": "**Muy buen video**",
            "video": {
               "id": 1,
               "title": "One video",
               "url": "https://www.youtube.com/embed/1bpbzXwG2bE",
               "published_at": "2021-10-07T01:44:19.339Z",
               "created_at": "2021-10-07T01:44:17.222Z",
               "updated_at": "2021-10-07T03:31:33.144Z"
            },
            "published_at": "2021-10-07T01:45:07.408Z",
            "created_at": "2021-10-07T01:45:05.959Z",
            "updated_at": "2021-10-07T01:45:07.422Z",
            "image": null
            }
         ]
      }
   },
   async fetch(){
      this.posts = await this.$axios.get('http://localhost:1337/posts').then(res => res.data)
      console.log(this.posts);
   }


   // Fuente para acceder a un objeto de multiples niveles
   // https://stackoverflow.com/questions/68478677/nuxt-js-unable-to-output-nested-array-elements-in-nuxt-js-array
}
</script>

