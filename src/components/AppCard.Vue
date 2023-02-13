<script>

  export default {
    name: 'AppCard',
    props: {
        element: Object
    },
             computed: {

                cover() {
                    const initialUrl = "https://image.tmdb.org/t/p/";
                    const coverSize = "w342";
                    let posterPath = this.element.poster_path

                    return initialUrl + coverSize + posterPath;
                },//cover

                vote() {
                    let newVote = this.element.vote_average
                    newVote = Math.ceil(newVote/2)

                    console.log(newVote);

                    return newVote
                },//vote

                flag() {
                    const flagDir = "src/assets/flags/"
                    let lang = this.element.original_language

                    return flagDir + lang + ".svg"

                }//flag

             },//export
            }
</script>

<template>
        <div class="card-container">

            <div class="front">
                <div class="cardImage">
                    <img :src="cover" alt="">
                </div>
            </div>

            
            <div class="back">

                    <h3 v-if="element.title" >
                    {{ element.title }}
                </h3>
                <h3 v-else-if="element.name">
                    {{ element.name }}
                </h3> 

                <h4>
                    <p class="star">
                        <span v-for="n in vote">
                        &#9733;</span>
                        <span v-for="n in (5-vote)">
                        &#9734;</span>
                    </p>
                </h4>
                
                <div class="img-container">
                    <img :src="flag" :alt="element.original_language">
                </div>

                <h6>
                    {{ element.release_date }}
                </h6>
                <p>
                    {{ element.overview }}
                </p>
            </div>

        </div>

  
  </template>
  
  <style lang="scss" scoped>

  .card-container {

        .front {
            
            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        }

        .back {
            display: none;
            background-color: rgba (0, 0 , 0, .6);
            max-height: 100%;
            color: white;
            overflow-y: auto;
            overflow-x: hidden;

            .star {
                span {
                    color: yellow;
    }
}
        }

        &:hover {
            .back {
            display: block;
            }

            .front {
                display: none;
            }
        }

        color: white;
  }

                .img-container {

                    width: 30px;
                    height: 30px;

                    img {
                    width: 100%;
                    height: 100%;
                    border-radius: 50%;
                    border: 1px solid black;
                    }
                }


  </style>
  