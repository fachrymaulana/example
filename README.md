<html>
<head>
<title>Data Barang</title>
</head>
<body>
<h2>Daftar Data Barang</h2>
<table width="500" border="0" cellpadding="0" cellspacing="1" bgcolor="#CCCCCC">
<tr bgcolor="#999999">
    <th><font color="#FFFFFF">Kode Barang</font></th>
    <th><font color="#FFFFFF">Nama Barang</font></th>
    <th><font color="#FFFFFF">Jenis Barang</font></th>
    <th><font color="#FFFFFF">Harga Barang</font></th>
</tr>
<?php
   $host ="localhost";
   $user ="root";
   $paswd="";
   $db   ="dbinventory";

   $idkoneksi=@mysql_connect($host,$user,$paswd) or
      die("Koneksi dengan <b>Server MySQL</b> tidak berhasil !");
   $iddatabase=@mysql_select_db($db);

   $sqlstr="select * from tbarang";
   $hasil=@mysql_query($sqlstr,$idkoneksi);

   while($row=mysql_fetch_array($hasil))
   {
?>
<tr bgcolor="#FFFFFF">
    <td><?php echo $row["kode_barang"]; ?></td>
    <td><?php echo $row["jenis_barang"]; ?></td>
    <td><?php echo $row["jenis_barang"]; ?></td>
    <td><?php echo $row["harga_barang"]; ?></td>
</tr>

<?php
   }
   @mysql_close($idkoneksi);
?>
</table>
</body>
</html>
