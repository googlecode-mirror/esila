# Introduction #

Semua keratan kod dibawah ni jarang digunakan. Tapi ada masa-masa tertentu ianya berguna untuk digunakan pada function2 yang tertentu.

# Select Multiple ID Query #
query sql kat bawah ni aku guna untuk select beberapa id yang terpilih sahaja pada table2 tertentu. Bukan ikut syarat yang ditetapkan.

```
SELECT aka_nokp,peribadi_nama,aka_kod_peringkat
FROM pengajian
INNER JOIN
	peribadi
		ON (pengajian.aka_nokp = peribadi.peribadi_nokp)
WHERE
	aka_nokp IN ('A2920632','A2876275')
```

# AJAX using jQuery POST Method #
submit form dan papar content(returned value) pada page yang sama menggunakan jQuery

```

        <script type="text/javascript">
        function cari() {
            jQuery.post('proses_bayaran.php',jQuery("#frmCariLejer").serialize(),function(data){
                jQuery("#hasilCarian").html(data)
            });
        }
        </script>
```

| proses\_bayaran.php | action file |
|:--------------------|:------------|
| #frmCariLejer       | id form yang akan hantar input value |
| data                | Returned value daripada action file |
| #hasilCarian        | div yang akan display content returned value |


# ADD ROW guna jQuery #
add row guna jquery (bukan ajax with method post).
clone table row yang last dan tambah row tersebut di akhir table dan clear kan input value yang disalin pada row terakhir tadi.
```

        <script type="text/javascript">
            var bil = 1;
            function addRow()
            {
                  bil++;
                  jQuery("#tblElaun tr:last").clone().hide().appendTo("#tblElaun");
                  jQuery("#tblElaun tr:last td:first").html(bil);
                  jQuery("#tblElaun tr:last").find("input").val("");
                  jQuery("#tblElaun tr:last").fadeIn(1000);
            }
        </script>
```