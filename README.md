<!DOCTYPE html>
<script>
function go(x){
document.form1.action="http://35.221.224.197:2700/"+x;
document.form1.submit();
}

function getTime() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
     document.getElementById("txt1").value = this.responseText;
    }
  };
  xhttp.open("GET", "http://35.221.224.197:2700/getTime", true);
  xhttp.send();
}
</script>


<html>
<body>

調時間
<form action = "http://35.221.224.197:2700/setTime" method="post">
	日期:<input type= "text" name = "date" value = "2020-6-1"><br>
	時間:<input type= "text" name = "time" value = "14:00"><br>
	<input type = "submit" value = "submit">
</form>
--------塞NPC收集品--------------
<form action = "http://35.221.224.197:2700/AddCollection" method="post">
	帳號:<input type= "text" name = "account" value = "try1"><br>
	道具id:<input type= "text" name = "item" value = ""><br>
	數量:<input type= "text" name = "num" value = ""><br>
	<input type = "submit" value = "submit">
</form>
--------收禮明細--------------
<form name = "form1" method="post">
	帳號:<input type= "text" name = "account" value = "try1"><br>
	<input type="button" value="查看收禮明細" name="B3" onclick="go('getGiftList');">
	<input type="button" value="清除收禮明細" name="B3" onclick="go('deleteGiftList');">
</form>
-------增加貨幣----------
<form action = "http://35.221.224.197:2700/addCoin" method="post">
	帳號:<input type= "text" name = "account" value = "try1"><br>
	M幣:<input type= "text" name = "mcoin" value = "0"><br>
	G幣:<input type= "text" name = "gcoin" value = "0"><br>
	<input type = "submit" value = "送出">
</form>
-------塞道具----------
<form action = "http://35.221.224.197:2700/sendItem" method="post">
	帳號:<input type= "text" name = "account" value = "try1"><br>
	道具id(男):<input type= "text" name = "item_m" value = "27011001"><br>
	道具id(女):<input type= "text" name = "item_f" value = "27011001"><br>
	道具期限(天數,永久:0):<input type= "text" name = "deadline" value = "0"><br>
	<input type = "submit" value = "送出">
</form>

--------重開--------------
<form action = "http://35.221.224.197:2700/restart" method="post">
	<input type= "hidden" name = "target" value = "restart_EC.bat"><br>
	<input type = "submit" value = "重開商城">
</form>
<form action = "http://35.221.224.197:2700/restart" method="post">
	<input type= "hidden" name = "target" value = "restart_Social.bat"><br>
	<input type = "submit" value = "重開社交">
</form>

<form action = "http://35.221.224.197:2700/restart" method="post">
	<input type= "hidden" name = "target" value = "setPriorityNormal.bat"><br>
	<input type = "submit" value = "調高社交區優先權">
</form>

<form action = "http://35.221.224.197:2700/restart" method="post">
	<input type= "hidden" name = "target" value = "setPriorityLow.bat"><br>
	<input type = "submit" value = "調低社交區優先權">
</form>
----------滿額寶箱-----------
<form action = "http://35.221.224.197:2700/sendPurchaseBox" method="post">
	帳號:<input type= "text" name = "account" value = "try1"><br>
	寶箱號碼(1:49|2:300|3:1000|4:3000):<input type= "text" name = "boxId" value = "1"><br>
	<input type = "submit" value = "100抽">
</form>
----------批次塞道具---------
<form enctype="multipart/form-data" action="http://35.221.224.197:2700/upload" method="post">
AddItem:<input type="file" name="AddItem" /></br>
AdditemAccount:<input type="file" name="AddItemAccount" /></br>
<input type="hidden" name="token" value="{{.}}"/>
<input type="submit" value="upload" />
</form>
<form action = "http://35.221.224.197:2700/restart" method="post">
	<input type= "hidden" name = "target" value = "shutdown.bat"><br>
	<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><input type = "submit" value = "關機">
</form>
</body>
</html>




