# admission-form-system

<!Doctype html>
<html>
 <head>
  <meta charset="UTF-8">
  <link rel="author" href=C:\xampp\htdocs\test\form.php>
 <style>
  table, td{text align: "center"; border:1px solid blue; border-radius:5px;}
 body{ margin:auto;padding:auto;width:1024px; background: "bk_img.jpeg"}
 tr, td {
    padding: 8px;
 text-align:center;}
}
 </style>
 
   <h2 text align="center"><i>Aishwarya College</i></h2>
   <p text align="center">A-9, 1st Extension Kamla Nehru Nagar, Jodhpur<br>Ph:0291-2760175</p><br><br>
 </head>
<body>

 <?php
// define variables and set to empty values
$Err = "";
$name = $email = $gender =$session_yr=$c_app=$ad_sem_yr=$univ=$name_op=$f_name=$m_name=$b_group=$res_phone=$stu_mnum=$cor_add=$per_add=$pincode=$id="";
  $session_yr = $_POST["session_yr"];
$c_app=$_POST["c_app"]  ;
$ad_sem_yr=$_POST["ad_sem_yr"];
$univ=$_POST["univ"];
$name_op1=$_POST["name_op1"];
$name_op2=$_POST["name_op2"];
$name_op3=$_POST["name_op3"];
$name_op4=$_POST["name_op4"];
$name=$_POST["name"];
$f_name=$_POST["f_name"];
$m_name=$_POST["m_name"];
$b_group=$_POST["b_group"];
$cor_add=$_POST["cor_add"];
$pincode=$_POST["pincode"];
$per_add=$_POST["per_add"];
$res_phone=$_POST["res_phone"];
$stu_mnum=$_POST["stu_mnum"];
$f_mnum=$_POST["f_mnum"];
$email=$_POST["email"];
$org=$_POST["org"];

if ($_SERVER["REQUEST_METHOD"] == "POST")
{
    if (empty($session_yr))  
	   {  
       echo $Err="enter the session";
	   }
     
     
    else if(empty($c_app))
     {
	     echo $Err="Course name is required";
     }	
     
     
    else if(empty($ad_sem_yr)) 
	   {
		   echo $Err="Admitted semester/year required";
	   }
	  
    
    else if(empty($univ)) 
	   {
		   echo $Err="Enter university";
	   }
	
    
    else if(empty($name_op1)) 
    {
		  echo $Err="Optional subject1 name is required";
    }
    
    else if(empty($name_op2)) 
    {
      echo $Err="Optional subject2 name is required";
    }

    else if(empty($name_op3)) 
    {
      echo $Err="Optional subject name3 is required";
    }

    else if(empty($name_op4)) 
    {
      echo $Err="Optional subject name4 is required";
    }

    else if(empty($name))
	  {
		   echo $Err="Name is required";
	  }
	
     
     else if(empty($f_name))
    {
	    echo $Err="Enter father's name";
    }

     
    else if(empty($m_name))
    {
	    echo $Err="Enter mother's name";
    }	

    
    else if(empty($b_group))
    {
	    echo $Err="enter the blood group";
    }

    
    else if(empty($cor_add))
    {
	    echo $Err="enter the correspondence address";
    }

    
    else if(empty($pincode))
    {
       echo $Err="enter the pincode";
    }
    
    
    else if(empty($per_add))
   {
	  echo $Err="enter the permanent address";
   }

   
    else if(empty($res_phone))
    {
	     echo $Err="enter the residential phone number with std code";
    }

   
   else if(empty($stu_mnum))
   {
	   echo $Err="enter the students mobile number";
   }
   
   
   else if(empty($f_mnum))
   {
	   echo $Err="enter your father's mobile number";
   }
   
   
   else if(empty($email))
   {
    	echo $Err="enter your email id";
   }

   
   else if(empty($org))
   {
	 echo $Err="enter organisation name";
   }

  $connect = mysql_connect("localhost","root","");
  if(!$connect)
  die("Server Not connected");
  $db = mysql_select_db("form",$connect);
  if(!$db)
  die("Database not Connected");
  

 $sql = "INSERT INTO registration(session,c_app,ad_sem_yr,univ,name_op1,name_op2,name_op3,name_op4,name,f_name,m_name,dob,cor_add,per_add,res_phone,stu_mnum,f_mnum,email,gender,category,medium,f_occ,m_occ)
VALUES ('$session_yr','$c_app','$ad_sem_yr','$univ','$name_op1','$name_op2','$name_op3','$name_op4','$name','$f_name','$m_name','$dob','$cor_add','$per_add','$res_phone','$stu_mnum','$f_mnum','$email','$gender','$category','$medium','$f_occ','$m_occ')";

/*echo "INSERT INTO registration (session,c_app,ad_sem_yr,univ,name_op1,name_op2,name_op3,name_op4,name,f_name,m_name,dob,cor_add,per_add,res_phone,stu_mnum,f_mnum,email,gender,category,medium,f_occ,m_occ)
VALUES ($session_yr,$c_app,$ad_sem_yr,$univ,$name_op1,$name_op2,$name_op3,$name_op4,$name,$f_name,$m_name,$dob,$cor_add,$per_add,$res_phone,$stu_mnum,$f_mnum,$email,$gender,$category,$medium,$f_occ,$m_occ)";	
}*/

mysql_query($sql);
}

?>
 <form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
 
   <table style="width:100%">
  <tr>
    <td>Session</td>
    <td colspan='8'><input type="text" name="session_yr" value="<?php echo $_POST["session_yr"];?>" size="150"></td>		
  </tr>
  <tr>
    <td>Course Applied for: </td>
    <td><input type="text" name="c_app" value="<?php echo $_POST["c_app"];?>"></td>
	<td>Admitted Sem/Year:</td>
	<td><input type="text" name="ad_sem_yr" value="<?php echo $_POST["ad_sem_yr"];?>" ></td>
	<td>University</td>
	<td  colspan='4'><input type="text" name="univ" value="<?php echo $_POST["univ"];?>" size="65"></td>
  </tr>
  <tr>
    <td>Name of the optional subject</td>
    <td colspan='2'><input type="text" name="name_op1" value="<?php echo $_POST["name_op1"];?>" size="30"></td><td  colspan='2'><input type="text" name="name_op2" value="<?php echo $_POST["name_op2"];?>" size="30"></td><td colspan='2'><input type="text" name="name_op3"  value="<?php echo $_POST["name_op3"];?>"size="30"></td><td colspan='2'><input type="text" name="name_op4"  value="<?php echo $_POST["name_op4"];?>"size="30"></td>
  </tr>
  <tr>
    <td>Name of the Applicant</td>
    <td colspan='8'><input type="text" name="name" value="<?php echo $_POST["name"];?>" size="150"></td>		
  </tr>
  <tr>
    <td>Father's Name</td>
    <td colspan='8'><input type="text" name="f_name" value="<?php echo $_POST["f_name"];?>" size="150"></td>		
  </tr>
  <tr>
    <td>Mother's Name</td>
    <td colspan='8'><input type="text" name="m_name" value="<?php echo $_POST["m_name"];?>" size="150"></td>		
  </tr>
  <tr>
    <td> Date of birth(dd/mm/yyyy)</td>
	<td>
	<select>
      <option value="volvo">01</option>
      <option value="saab">02</option>
      <option value="opel">03</option>
      <option value="audi">04</option>
	  <option value="audi">05</option>
	  <option value="audi">06</option>
	  <option value="audi">07</option>
	  <option value="audi">08</option>
	  <option value="audi">09</option>
	  <option value="audi">10</option>
	  <option value="audi">11</option>
	  <option value="audi">12</option>
	  <option value="audi">13</option>
	  <option value="audi">14</option>
	  <option value="audi">15</option>
	  <option value="audi">16</option>
	  <option value="audi">17</option>
	  <option value="audi">18</option>
	  <option value="audi">19</option>
	  <option value="audi">20</option>
	  <option value="audi">21</option>
	  <option value="audi">22</option>
	  <option value="audi">23</option>
	  <option value="audi">24</option>
	  <option value="audi">25</option>
	  <option value="audi">26</option>
	  <option value="audi">27</option>
	  <option value="audi">28</option>
	  <option value="audi">29</option>
	  <option value="audi">30</option>
	  <option value="audi">31</option>
    </select>
	</td>
	<td>
	<select>
      <option value="volvo">Jan</option>
      <option value="saab">Feb</option>
      <option value="opel">March</option>
      <option value="audi">April</option>
	  <option value="audi">May</option>
	  <option value="audi">June</option>
	  <option value="audi">July</option>
	  <option value="audi">Aug</option>
	  <option value="audi">Sept</option>
	  <option value="audi">Oct</option>
	  <option value="audi">Nov</option>
	  <option value="audi">Dec</option>
    </select>
	</td>
	<td>
	<select>
      <option value="volvo">2000</option>
      <option value="saab">2001</option>
      <option value="opel">2002</option>
      <option value="audi">2003</option>
    </select>
	</td>
	<td> Blood Group</td>
	<td colspan='4'><input type="text" name="b_group" value="<?php echo $_POST["b_group"];?>"  size="65"></td>
  </tr>
  <tr>
    <td> Correspondence Address:</td>
	<td colspan='6'> <input type="text" name="cor_add" value="<?php echo $_POST["cor_add"];?>" size="110"></td> <td>PINCODE</td><td><input type="text" name="pincode"value="<?php echo $_POST["pincode"];?>" ></td> 
  </tr>	
  <tr>
    <td> Permanent Address:</td>
	<td colspan='6'> <input type="text" name="per_add" value="<?php echo $_POST["per_add"];?>"  size="110"></td> <td>PINCODE</td><td><input type="text" name="pincode"value="<?php echo $_POST["pincode"];?>" ></td> 
  </tr>	
  <tr>
    <td> Res. Phone(STD code)</td>
	<td colspan='4'> <input type="text" name="res_phone" value="<?php echo $_POST["res_phone"];?>" size="70"></td> <td colspan='4'><input type="text" name="res_phone" value="<?php echo $_POST["res_phone"];?>" size="65"></td> 
  </tr>	
  <tr>
    <td> Student's Mobile Number</td>
	<td colspan='4'> <input type="text" name="stu_mnum" value="<?php echo $_POST["stu_mnum"];?>" size="70"></td> <td>Father's Mobile Number</td><td colspan='4'><input type="text" name="f_mnum" value="<?php echo $_POST["f_mnum"];?>"  size="50"></td> 
  </tr>
  <tr>
    <td>E-mail Address(if any)</td>
    <td colspan='8'><input type="text" name="email" value="<?php echo $_POST["email"];?>" size="150"></td>		
  </tr>
  <tr>
    <td>Gender</td>
    <td><input type="radio" name="gender">
         <?php if (isset($gender) && $gender=="female") echo "checked";?>Female
        <input type="radio" name="gender">
         <?php if (isset($gender) && $gender=="male") echo "checked";?>Male</td>		
  </tr>
  <tr>
    <td>Category</td>
	<td><input type="radio" name="category">
         <?php if (isset($category) && $category=="General") echo "checked";?>General</td>
		 <td><input type="radio" name="category">
         <?php if (isset($category) && $category=="SC") echo "checked";?>SC</td>
		 <td><input type="radio" name="category">
         <?php if (isset($category) && $category=="ST") echo "checked";?>ST</td>
		 <td><input type="radio" name="category">
         <?php if (isset($category) && $category=="OBC") echo "checked";?>OBC</td>
		 <td><input type="radio" name="category">
         <?php if (isset($category) && $category=="PH") echo "checked";?>PH</td>
		 <td><input type="radio" name="category">
         <?php if (isset($category) && $category=="Minority") echo "checked";?>Minority</td>
		 <td colspan='3'><input type="radio" name="category">
         <?php if (isset($category) && $category=="SBC") echo "checked";?>SBC</td>
  <tr>
    <td>Medium of Learning:</td><td>English<input type="radio" name="med">
         <?php if (isset($med) && $med=="English") echo "checked";?></td>
		 <td>Hindi<input type="radio" name="med">
         <?php if (isset($med) && $med=="Hindi") echo "checked";?></td>
  </tr>	
  <tr>	
	<td>Father's Occupation:</td><td><input type="radio" name="f_occ">
         <?php if (isset($f_occ) && $f_occ=="Govt") echo "checked";?>Govt.</td>
	<td><input type="radio" name="f_occ">
         <?php if (isset($f_occ) && $f_occ=="Private") echo "checked";?>Private</td>
	<td><input type="radio" name="f_occ">
         <?php if (isset($f_occ) && $f_occ=="Business") echo "checked";?>Business</td>
	<td colspan='2'>Post<input type="text" value="<?php echo $_POST["org"];?>"></td>
	<td colspan='3'>Organisation<input type="text" name="org" value="<?php echo $_POST["org"];?>" ></td>
  </tr>	
  <tr>	
	<td>Mother's Occupation(if any):</td><td><input type="radio" name="m_occ">
         <?php if (isset($m_occ) && $m_occ=="Govt") echo "checked";?>Govt.</td>
	<td><input type="radio" name="f_occ">
         <?php if (isset($m_occ) && $m_occ=="Private") echo "checked";?>Private</td>
	<td><input type="radio" name="f_occ">
         <?php if (isset($m_occ) && $m_occ=="Business") echo "checked";?>Business</td>
	<td colspan='2'>Post<input type="text" value="<?php echo $_POST["org"];?>"></td>
	<td colspan='3'>Organisation<input type="text" name="org" value="<?php echo $_POST["org"];?>" ></td></td>
  </tr>	
	</table><br>
  <input type="submit" name="submit" value="Submit"><br> 

</body>
 </form>
</html>
