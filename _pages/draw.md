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
include "config.php"; // Database connection using PDO
?>
<form method="post">
  First Name:<br>
  <input type="text" name="firstname" placeholder="James"><br><br>
  Last Name:<br>
  <input type="text" name="lastname" placeholder="Smith"><br><br>
  Email:<br>
  <input type="email" name="email" placeholder="John.Smith@email.net"><br><br>
  Address:<br>
  <input type="text" name="address" placeholder="Australia"><br><br>
<h3>Preference 1</h3>  
<select name="pref1">
    <option value="" default selected>Select</option>
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
<select name="pref2">
    <option value="" default selected>Select</option>
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
<select name="pref3">
    <option value="" default selected>Select</option>
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
<select name="pref4" id='pref4'>
    <option value="" default selected>Select</option>
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
$fname = $_POST['firstname'];
$lname = $_POST['lastname'];
$email = $_POST['email'];
$address = $_POST['address'];
$pref1 = $_POST['pref1'];
$pref2 = $_POST['pref2'];
$pref3 = $_POST['pref3'];
$pref4 = $_POST['pref4'];
if($fname !=''&& $lname !=''&& $email !=''&& $address !='')
{
$sql = "INSERT INTO draw_users (fname, lname, email, address)
VALUES ('$fname', '$lname', '$email', '$address')";
$pref = "INSERT INTO draw_preferences (email, pref1, pref2, pref3, pref4)
VALUES ('$email', '$pref1', '$pref2', '$pref3', '$pref4')";
$select = "SELECT * FROM draw_users";
  $email = $_POST['email'];
$result = mysqli_query($conn,"SELECT * FROM draw_users");
  $row = mysqli_fetch_array($result);
if ($conn->query($sql) === TRUE && $conn->query($pref) === TRUE) {
	 <br><br>echo 'Entered Preferences';
} else {
    <br><br>echo "Error: " . $sql . "<br>" . $conn->error;
}
}
}
else{
?><span><?php echo "<br><br>Please fill all fields.....!!!!!!!!!!!!";?></span> <?php
}
$conn->close();
?>
</form>