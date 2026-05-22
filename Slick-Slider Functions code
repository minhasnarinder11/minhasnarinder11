// function that runs when shortcode is called
function wpb_demo_shortcode() { 
  ?>
<style>
.center .slick-slide{
  background-color: #ffffff00;
  color: #FFF;
  height: auto;
  margin: 0 15px 0 0;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: scale(0.8);
  transition: all 0.4s ease-in-out;
}
/*.center .slick-slide {
    width: 500px !important;
}*/
.center .slick-slide,
.center .slick-slide[aria-hidden="true"]:not(.slick-cloned) ~ .slick-cloned[aria-hidden="true"] {
  transform: scale(0.8, 0.8);
  transition: all 0.4s ease-in-out;
}
.center .slick-center,
.center .slick-slide[aria-hidden="true"]:not([tabindex="-1"]) + .slick-cloned[aria-hidden="true"] {
  transform: scale(1);
  background-color: #000000;
}
.center .slick-current.slick-active{
  transform: scale(1);
  background-color: #000000;
}

.slick-next, .slick-prev{
  z-index: 5;
}
.slick-next{
  right: 40px!important;
}
.slick-prev{
  left: 15px!important;
}

.slick-next:before, .slick-prev:before {
    font-size: 46px !important;
    line-height: 1;
    opacity: .75;
    color: #E1991E !important;
}
.slick-slide {position: relative;}
.custom-text-and-image {
    border: 3px solid #a9751c;
    position: absolute;
    z-index: 99;
    bottom: 40px;
    left: 0;
    width: 86%;
    margin: 0 30px;
    padding: 5px 5px 5px 5px;
    border-radius: 10px;
    display: flex;
}
.custom-text-and-image .custom-img img {
    position: relative;
    top: 18px;
    height: 40px;
    width: auto;
}
.custom-img img {
    width: 40px;
    height: 40px;
}
.custom-text-and-image .custom-text {
    width: 88%;
    float: left;
}
.slick-slide .custom-text h2 {
    font-family: "Rajdhani", Sans-serif;
    font-size: 32px;
    font-weight: 700;
    line-height: 1.3em;
    letter-spacing: 0px;
    color: #E1991E;
    margin: 0;
}
.slick-slide .custom-text p {
    font-family: 'Work Sans';
    font-size: 14px;
    font-weight: 400;
    line-height: 1.3em;
    letter-spacing: 0px;
    margin: 0;
}
.slick-next:before, .slick-prev:before
Specificity: (0,1,1)
 {
    color: #e1991e !important;
}
</style>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.5.9/slick-theme.min.css" >
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css">


<div class="wrapper">
  <div class="center">
<?php
$args = array('post_type' => 'commercial', 'orderby' => 'date', 'order' => 'DESC' );
//print_r($args);echo '</pre>';
$the_query = new WP_Query($args);
if ($the_query->have_posts()) :
    while ($the_query->have_posts()) :
        $the_query->the_post();
        $featured_img_url = get_the_post_thumbnail_url(get_the_ID(),'full'); 
?>
<div><img src="<?php echo $featured_img_url; ?>" />
    <div class="custom-text-and-image">
        <div class="custom-text">
            <h2><?php echo get_the_title(); ?></h2>
            <p><?php echo get_the_excerpt(); ?></p>
        </div>
        <div class="custom-img">
            <?php 
            $icon_url = get_field('add_icon'); // Returns URL directly since format = Image URL
            if ($icon_url) : ?>
                <img src="<?php echo esc_url($icon_url); ?>"/>
            <?php endif; ?>
        </div>
    </div>
</div>
        
        

<?php endwhile;
    wp_reset_postdata();
endif; ?>


      <!--div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad1-1000x593.png" /></div>
      <div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad2-1000x593.png" /></div>
      <div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad3-1000x593.png" /></div>
      <div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad1-1000x593.png" /></div>
      <div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad1-1000x593.png" /></div>
      <div><img src="https://leadbusy.com/wp-content/uploads/2024/07/bad1-1000x593.png" /></div-->
    </div>
</div>


<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
<script>
$('.center').slick({
  centerMode: true,
  dots: true,
  centerPadding: '490px',
  slidesToShow: 1,
  responsive: [
    {
      breakpoint: 768,
      settings: {
        arrows: true,
        dots: true,
        centerMode: true,
        centerPadding: '40px',
        slidesToShow: 1
      }
    },
    {
      breakpoint: 480,
      settings: {
        arrows: true,
        dots: true,
        centerMode: true,
        centerPadding: '10px',
        slidesToShow: 1
      }
    }
  ]
});
</script>
  <?php
}
// register shortcode
add_shortcode('home_pageservice', 'wpb_demo_shortcode');
