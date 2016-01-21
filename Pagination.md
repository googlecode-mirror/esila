# Pengenalan #

Guide macamana nak guna pagination dalam coding.


# Cara Penggunaan #



perlu cari line berikut dan dibawahnya bermula paging declaratation.
```
$DBQueryPB->runSQL_Query();
```

coding bawah ni untuk declare object pagination yang akan diletakkan di bawah baris kod di atas.
```
$myPagination = new Pagination();
$myPagination->initPaging($myPagination, $DBQueryPB, $query, 20, 5);
```
dengan :

`$myPagination` : adalah objekbagi kelas paging ini sendiri<br>
<code>$DBQueryPB</code> : objek bagi kelas DBQuery yang dicipta<br>
<code>$query</code> : SQL query yang hendak di run bagi hasil carian page berkenaan. Bukan objek SQLquery tetapi sql punya query. (<code>$sqlQueryObj-&gt;getSQLQuery()</code>)<br>
<code>20</code> : bilangan row yang hendak dipaparkan pada satu page<br>
<code>5</code> : bilangan link yang hendak dipaparkan dibawah (1 2 3 4 <b>5</b>



<pre><code>$myPagination-&gt;paging($myPagination);<br>
</code></pre>
kod di atas perlu diletakkan di bawah sekali (asalkan diluar selepas while) untuk melengkapkan pagination tersebut. Dan juga untuk hasilakan UI pagination(link) di bahagian footer page tersebut.