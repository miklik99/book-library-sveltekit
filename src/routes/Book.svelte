<script lang="ts">
	import { spring } from 'svelte/motion';
  import welcome from '$lib/images/book.jpg';

	let count = 0;

	const displayed_count = spring();
	$: displayed_count.set(count);

	function modulo(n: number, m: number) {
		// handle negative numbers
		return ((n % m) + m) % m;
	}
</script>

<div class="book">
  <div class="image-section">
    <div class="color"></div>
    <img srcset={welcome} type="image/webp" alt="Book">
  </div>
  <div class="text-section">
    <p class="title">Title</p>
    <p class="author">Author</p>
  </div>
</div>

<style lang="sass">
.book
  width: 250px
  border: 1px solid

  .image-section
    text-align: center
    position: relative
    bottom: 0
    left: 0
    width: 100%
    height: 65%

    img
      width: 50%
      border-radius: 0.8em
      box-shadow: 0px 0px 30px -5px rgba(0,0,0,0.5)

      &:hover
        

    .color
      z-index: -1
      position: absolute
      background-color: pink
      width: 100%
      height: 75%
      bottom: -15px
      left: 0
      border-radius: 0.8em

  .text-section
    text-align: center
    padding: 30px

    .title
      font-weight: bold


</style>