---
ID: 9
post_title: Draw
author: tomothy
post_date: 2016-05-01 03:11:41
post_excerpt: ""
layout: page
permalink: http://localhost/wordpress/draw/
published: true
pyre_slider_position:
  - default
pyre_slider_type:
  - 'no'
pyre_slider:
  - "0"
pyre_wooslider:
  - "0"
pyre_revslider:
  - "0"
pyre_elasticslider:
  - "0"
pyre_fallback:
  - ""
pyre_avada_rev_styles:
  - default
pyre_main_top_padding:
  - ""
pyre_main_bottom_padding:
  - ""
pyre_hundredp_padding:
  - ""
pyre_show_first_featured_image:
  - 'no'
pyre_display_header:
  - 'yes'
pyre_header_100_width:
  - default
pyre_header_bg:
  - ""
pyre_header_bg_color:
  - ""
pyre_header_bg_opacity:
  - ""
pyre_header_bg_full:
  - 'no'
pyre_header_bg_repeat:
  - repeat
pyre_displayed_menu:
  - default
pyre_display_footer:
  - default
pyre_display_copyright:
  - default
pyre_footer_100_width:
  - default
pyre_sidebar_position:
  - default
pyre_sidebar_bg_color:
  - ""
pyre_page_bg_layout:
  - default
pyre_page_bg:
  - ""
pyre_page_bg_color:
  - ""
pyre_page_bg_full:
  - 'no'
pyre_page_bg_repeat:
  - repeat
pyre_wide_page_bg:
  - ""
pyre_wide_page_bg_color:
  - ""
pyre_wide_page_bg_full:
  - 'no'
pyre_wide_page_bg_repeat:
  - repeat
pyre_portfolio_width_100:
  - 'no'
pyre_portfolio_content_length:
  - default
pyre_portfolio_excerpt:
  - ""
pyre_portfolio_filters:
  - 'yes'
pyre_portfolio_text_layout:
  - default
pyre_portfolio_featured_image_size:
  - default
pyre_portfolio_column_spacing:
  - ""
pyre_page_title:
  - default
pyre_page_title_text:
  - default
pyre_page_title_text_alignment:
  - default
pyre_page_title_100_width:
  - default
pyre_page_title_custom_text:
  - ""
pyre_page_title_text_size:
  - ""
pyre_page_title_custom_subheader:
  - ""
pyre_page_title_custom_subheader_text_size:
  - ""
pyre_page_title_font_color:
  - ""
pyre_page_title_height:
  - ""
pyre_page_title_mobile_height:
  - ""
pyre_page_title_bar_bg:
  - ""
pyre_page_title_bar_bg_retina:
  - ""
pyre_page_title_bar_bg_color:
  - ""
pyre_page_title_bar_borders_color:
  - ""
pyre_page_title_bar_bg_full:
  - default
pyre_page_title_bg_parallax:
  - default
pyre_page_title_breadcrumbs_search_bar:
  - default
sbg_selected_sidebar:
  - 'a:1:{i:0;s:1:"0";}'
sbg_selected_sidebar_replacement:
  - 'a:1:{i:0;s:0:"";}'
sbg_selected_sidebar_2:
  - 'a:1:{i:0;s:1:"0";}'
sbg_selected_sidebar_2_replacement:
  - 'a:1:{i:0;s:0:"";}'
---
<code><?php
//database connection variables
$user="root";
$password="cUznnGsC9JTjcScR";
$database="wordpress";
$host="localhost";

//database connection
$conn = new mysqli($host, $user, $password, $database) 
or die ('Cannot connect to db');
?>

<p>
Draw to purchase bags available in the March "All about the tote" bag release by Rainbow Rockstars. Only one bag can be drawn per entry. Multiple entries are allowed provided that entrants understand that all winning entries must be paid for. Preferences can be as few, or as many as you like. Preference boxes do not all need to be filled in. Draw will begin at 10am aest (qld time) on Wednesday 23rd of March and closes at 10am aest (qld time) Thursday 24th of March. Winning entries will be invoiced shortly after, to the email address provided and given 24hrs, from time of invoice, to pay. International entries are welcome and postage fees will be adjusted accordingly.  Prices stated below do not include postage. By entering this draw you agree to the terms stated here.
</p>


<form action="" method="post">

  First Name:<br>
  <input type="text" name="firstname" placeholder="James"><br><br>
  Last Name:<br>
  <input type="text" name="lastname" placeholder="Smith"><br><br>
  Email:<br>
  <input type="email" name="email" placeholder="John.Smith@email.net"><br><br>
  Country:<br>
  <input type="text" name="country" placeholder="Australia"><br><br>


<h3>Preference 1</h3>  
<select name='Name'>
<option>Select</option>
<?php
$result = $conn->query("select * from draw");
    while ($row = $result->fetch_assoc()) {
                  unset($price, $name);
                  $name = $row['name'];
				  $price = $row['price'];
                  echo "<option> Product: ".$name." &nbsp;&nbsp;Price: $".$price."</option>";
} 
?> 
</select>

<h3>Preference 2</h3>  
<select name='Name'>
<option>Select</option>
<?php
    $result = $conn->query("select * from draw");
    while ($row = $result->fetch_assoc()) {
                  unset($price, $name);
                  $name = $row['name'];
				  $price = $row['price'];
                  echo "<option> Product: ".$name." &nbsp;&nbsp;Price: $".$price."</option>";
}   
?> 
</select>

<h3>Preference 3</h3>  
<select name='Name'>
<option>Select</option>
<?php
    $result = $conn->query("select * from draw");
    while ($row = $result->fetch_assoc()) {
                  unset($price, $name);
                  $name = $row['name'];
				  $price = $row['price'];
                  echo "<option> Product: ".$name." &nbsp;&nbsp;Price: $".$price."</option>";
}   
?> 
</select>

<h3>Preference 4</h3>  
<select name='Name'>
<option>Select</option>
<?php
    $result = $conn->query("select * from draw");
    while ($row = $result->fetch_assoc()) {
                  unset($price, $name);
                  $name = $row['name'];
				  $price = $row['price'];
                  echo "<option> Product: ".$name." &nbsp;&nbsp;Price: $".$price."</option>";
}   

?> 
</select>
<br>
<br>
<input type="submit" name="submit" id="submit" class="button" value="Submit"/>
<?php
if(isset($_POST['submit'])){
// Fetching variables of the form which travels in URL
$fname = $_POST['firstname'];
$lname = $_POST['lastname'];
$email = $_POST['email'];
$country = $_POST['country'];
if($fname !=''&& $lname !=''&& $email !=''&& $country !='')
{
//  To redirect form on a particular page
header("Location:https://www.google.com");
}
else{
?><span><?php echo "<br><br>Please fill all fields.....!!!!!!!!!!!!";?></span> <?php
}
}
$conn->close();

?>
</form>


</code>