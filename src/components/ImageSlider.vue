<template>
    <div class="image-slider">
        <img :src="currentImage" alt="Slider Image">
        <button @click="nextImage">Next</button>
    </div>
</template>
  
<script>
// This exports a default Vue component object with its data, computed, and methods options.
export default {
    data() {
        // This is the data option, which is a function that returns an object containing the component's data.
        return {
            // This is an array of image paths that will be used in the image slider.
            images: [
                'src/assets/slider-images/img1.jpg',
                'src/assets/slider-images/img2.jpg',
                'src/assets/slider-images/img3.jpg',
                'src/assets/slider-images/img4.jpg',
                'src/assets/slider-images/img5.jpg',
            ],
            // This is the index of the current image being displayed in the slider.
            currentIndex: 0,
        };
    },
    computed: {
        // This is the computed option, which is an object containing computed property functions.
        currentImage() {
            // This computed property function returns the current image path based on the currentIndex.
            return this.images[this.currentIndex];
        },
    },
    methods: {
        // This is the methods option, which is an object containing methods functions.
        nextImage() {
            // This method function increments the currentIndex to show the next image in the slider.
            if (this.currentIndex === this.images.length - 1) {
                // If the current index is the last index in the array, loop back to the first index.
                this.currentIndex = 0;
            } else {
                // Otherwise, increment the current index.
                this.currentIndex += 1;
            }
        },
    },
};

</script>
  
<style>
.image-slider {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.image-slider img {
    max-width: 100%;
    max-height: 500px;
}

.image-slider button {
    margin-top: 1rem;
    border: 2px solid green;
    border-radius: 3px;
    background: #009f00;
    color: white;
    font-weight: 700;
    font-size: 1.4em;
    padding: 5px 15px;
    cursor: pointer;
}

.image-slider button:hover{
    opacity: 0.7;
}
</style>
  