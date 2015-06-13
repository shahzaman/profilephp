<?php
include('session.php');
?>
<!doctype html>
<html>
<head>
    
    <title>E-trade</title>
    <link href="style.css" rel="stylesheet">

</head>
<body>


<div class="header">
     <div class="header_bar">
        <img src="images/logo.jpg" width="150" height="100">
       <a href="logout.php" class="abutton">Log Out</a>
      </div>  
</div>
    
	<div class="reg_box">
	<?php
	$connection = mysql_connect("localhost","root","")or die('could not connect');
$sql = mysql_select_db("trading")or die('Database not found');
	$query = ("SELECT * FROM user where Username='$user_check'") or die("Nothing here");
$result = mysql_query($query);

while($row = mysql_fetch_array($result))
{
	
       $Name = $row['UserName'];
	   $fname = $row['FirstName'];
	   $lname = $row['LastNAME'];
       $address = $row['Address'];
       $email = $row['Email'];
	   $mobiel = $row['Mobile'];
       $city = $row['City'];
	   $company = $row['Company'];  

echo "
    <center> Your personal Information</center><hr>
	  
	  <table width='50%' cellpadding='3' id='tbl' >
	  <tr>
	 &nbsp; Name&nbsp;:&nbsp;&nbsp;$fname&nbsp;$lname<br>
	  &nbsp;Company&nbsp;:&nbsp;&nbsp;$company<br>
	  &nbsp;Email&nbsp;:&nbsp;&nbsp;$email<br>
	  &nbsp;Mobile no.&nbsp;:&nbsp;&nbsp;$mobiel<br>
	  &nbsp;Address &nbsp;: &nbsp;&nbsp;$address<br>
	  &nbsp;City&nbsp; :&nbsp;&nbsp;$city<br>
	  <br>
	 
	 </tr>
	 </table>
	
";


}
?>	
	</div>

  
    


<section data-role="footer" class="footer" style="margin-top:50%;">
            <footer>
                <div class="footer">
              
                </div>
            </footer>
        </section>
</body>
</html>
