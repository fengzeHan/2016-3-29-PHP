# 2016-3-29-PHP
//orderform.html
!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
	   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml" lang="en_US" xml:lang="en_US">
<!--
 * Created on 2016-3-29
 *
 * To change the template for this generated file go to
 * Window - Preferences - PHPeclipse - PHP - Code Templates
-->
 <head>
  <title>汽车零部件商店 </title>
 </head>
 <body>
 <form action="processorder.php" method="post">
<table border="0">
<tr bgcolor="#cccccc">
<td width="150">Item</td>
<td width="15">Quantity</td>
</tr>
<tr>
<td>Tires</td>
<td align="center"><input type="text" name="tireqty" size="3" maxlength="3"/></td>
</tr>
<tr>
<td>Oil</td>
<td align="center"><input type="text" name="oilqty" size="3" maxlength="3"/></td>
</tr>
<tr>
<td>Spark Plugs</td>
<td align="center"><input type="text" name="sparkqty" size="3" maxlength="3"/></td>
</tr>
<tr>
<td colspan="2" align="center"><input type="submit" value="Submit Order"/></td>
</tr>
</table>
</form>

 </body>
</html>



//proccessorder.php
<?php
/*
 * Created on 2016-3-29
 *
 * To change the template for this generated file go to
 * Window - Preferences - PHPeclipse - PHP - Code Templates
 */

define('TIREPRICE',100);
define('OILPRICE',10);
define('SPARKPRICE',4);
$tireqty = $_POST['tireqty'];
$oilqty = $_POST['oilqty'];
$sparkqty = $_POST['sparkqty'];
$totalqty = 0;
$totalqty = $tireqty + $oilqty + $sparkqty;
echo "Item orderde:".$totalqty."<br/>";
$totalamount = 0.00;
$totalamount = $tireqty * TIREPRICE + $oilqty * OILPRICE + $sparkqty * SPARKPRICE;
echo "Subtotal $".number_format($totalamount,-2)."<br/>";
$taxrate = 0.10;
$totalamount = $totalamount * (1 + $taxrate);
echo "Total including tax : $".number_format($totalamount,-2)."<br/>";

?>

