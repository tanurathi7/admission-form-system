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
       $connect = mysql_connect("localhost","root","");
        if(!$connect)
        die("Server Not connected");
        $db = mysql_select_db("form",$connect);
        if(!$db)
        die("Database not Connected");

      $id = $_GET["id"];
      
      $sql = "select * from registration where id=$id";
      $rs = mysql_query($sql);
      $row = mysql_fetch_array($rs);
    ?>
    <form method="post" action="update.php">
 
      <table style="width:100%">
      <tr>
         <td>Session</td>
         <td colspan='8'><input type="text" name="session_yr" value="<?php echo $row["session"];?>" size="150"></td>    
      </tr>
      <tr>
         <td>Course Applied for: </td>
         <td><input type="text" name="c_app" value="<?php echo $row["c_app"];?>"></td>
         <td>Admitted Sem/Year:</td>
         <td><input type="text" name="ad_sem_yr" value="<?php echo $row["ad_sem_yr"];?>" ></td>
         <td>University</td>
         <td  colspan='4'><input type="text" name="univ" value="<?php echo $row["univ"];?>" size="65"></td>
      </tr>
      <tr>
         <td>Name of the optional subject</td>
         <td colspan='2'><input type="text" name="name_op1" value="<?php echo $row["name_op1"];?>" size="30"></td><td  colspan='2'><input type="text" name="name_op2" value="<?php echo $row["name_op2"];?>" size="30"></td><td colspan='2'><input type="text" name="name_op3"  value="<?php echo $row["name_op3"];?>"size="30"></td><td colspan='2'><input type="text" name="name_op4"  value="<?php echo $row["name_op4"];?>"size="30"></td>
      </tr>
      <tr>
         <td>Name of the Applicant</td>
         <td colspan='8'><input type="text" name="name" value="<?php echo $row["name"];?>" size="150"></td>    
      </tr>
      <tr>
         <td>Father's Name</td>
         <td colspan='8'><input type="text" name="f_name" value="<?php echo $row["f_name"];?>" size="150"></td>    
      </tr>
      <tr>
         <td>Mother's Name</td>
         <td colspan='8'><input type="text" name="m_name" value="<?php echo $row["m_name"];?>" size="150"></td>    
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
         <td colspan='4'><input type="text" name="b_group" value="<?php echo $row["b_group"];?>"  size="65"></td>
      </tr>
      <tr>
         <td> Correspondence Address:</td>
         <td colspan='6'> <input type="text" name="cor_add" value="<?php echo $row["cor_add"];?>" size="110"></td> <td>PINCODE</td><td><input type="text" name="pincode"value="<?php echo $row["pincode"];?>" ></td> 
      </tr> 
      <tr>
         <td> Permanent Address:</td>
         <td colspan='6'> <input type="text" name="per_add" value="<?php echo $row["per_add"];?>"  size="110"></td> <td>PINCODE</td><td><input type="text" name="pincode"value="<?php echo $row["pincode"];?>" ></td> 
      </tr> 
      <tr>
         <td> Res. Phone(STD code)</td>
         <td colspan='4'> <input type="text" name="res_phone" value="<?php echo $row["res_phone"];?>" size="70"></td> <td colspan='4'><input type="text" name="res_phone" value="<?php echo $row["res_phone"];?>" size="65"></td> 
      </tr> 
      <tr>
         <td> Student's Mobile Number</td>
         <td colspan='4'> <input type="text" name="stu_mnum" value="<?php echo $row["stu_mnum"];?>" size="70"></td> <td>Father's Mobile Number</td><td colspan='4'><input type="text" name="f_mnum" value="<?php echo $row["f_mnum"];?>"  size="50"></td> 
      </tr>
      <tr>
        <td>E-mail Address(if any)</td>
        <td colspan='8'><input type="text" name="email" value="<?php echo $row["email"];?>" size="150"></td>    
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
 </form>
  </body>
</html>

