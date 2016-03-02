<!DOCTYPE html>
<html>
<head>
 <meta charset="UTF-8">

 <style>

 table, td{text align: "center"; border:1px solid blue; border-radius:5px;}
 body{ margin:auto;padding:auto;width:1024px; background: "bk_img.jpeg"}
 tr, td {
    padding: 8px;
    text-align:center;}

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
      <td><?php echo $row["id"];?></td><td><?php echo $row["name"];?></td><td><?php echo $row["f_name"];?></td><td><?php echo $row["email"];?></td><td><a href="edit.php?id=<?php echo $row['id'];?>">Edit</a>&nbsp;<a href="delete.php?id=<?php echo $row['id'];?>">Delete</a></td>
  </tr>
</table>
</body>
</html>
