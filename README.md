<!DOCTYPE HTML>
<html>
<head>
 <meta charset="UTF-8">

 <style>
    table, td{text align: "center"; border:1px solid blue; border-radius:5px;}
    body{ margin:auto;padding:auto;width:1024px; background: "bk_img.jpeg"}
    tr, td 
    {
       padding: 8px;
       text-align:center;
    }

 </style>
</head>
 <body>
 <?php
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
 }  

  $connect = mysql_connect("localhost","root","");
  if(!$connect)
  die("Server Not connected");
  $db = mysql_select_db("form",$connect);
  if(!$db)
  die("Database not Connected");

  $sql1= "SELECT  id, name, f_name, email from registration";
  $retvalue=mysql_query($sql1);
?>
<table style="width:100%">
  <tr>
      <td>Id</td><td>Name</td><td>Father's Name</td><td>Email id</td><td>Operation</td>
  </tr>
  <?php
    while($row = mysql_fetch_array($retvalue))
    {
  ?>
  <tr>
      <td><?php echo $row["id"];?></td><td><?php echo $row["name"];?></td><td><?php echo $row["f_name"];?></td><td><?php echo $row["email"];?></td><td><a href="edit.php?id=<?php echo $row['id'];?>">Edit</a>&nbsp;<a href="delete.php">Delete</a></td>
  </tr>
  <?php
    }
  ?>
?>
 </body>
</html>
