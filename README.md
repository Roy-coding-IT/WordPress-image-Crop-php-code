# WordPress-image-Crop-php-code

<?php

// in functions.php

add_theme_support( 'post-thumbnails');

/* 
Wordpress Auto crop an image = 5 size. All Sizes are given below.

thumbnail		// Thumbnail (default 150px x 150px max)
medium 			// Medium resolution (default 300px x 300px max)
large			// Large resolution (default 640px x 640px max)
full			// Original image resolution (unmodified)

But, if you need custom size, you can define sizes in functions.php
*/

add_image_size( 'post-image', 600, 200, true );

// Using the sized image in your loop

// Image URL

// If you want to use wordpress resize just add your size, I've added large size image in example 

$image_variable = wp_get_attachment_image_src( get_post_thumbnail_id( $post->ID ), 'large' ); echo $image_variable[0];


// If you want to use your custom size

$image_variable = wp_get_attachment_image_src( get_post_thumbnail_id( $post->ID ), 'post-image' ); echo $image_variable[0];



?>
