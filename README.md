# menghitung-depresiasi-web

Berikut codingan untuk menghitung depresiasi:

<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <title>Laporan MDPLP</title>
 <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

    <style>
        form{
            padding: 20px;
        }
    </style>
</head>

<body>

    <div class="container">
        
    <!-- Form input data Angka -->
    <form name="form">
        <div class="form-group col-md-12">
            <label for="">Nilai Perolehan</label>
                <input class="form-control np" type="text" name="np" size="3">
        </div>

        <div class="form-group col-md-12">
            <label for="">Nilai Regulasi</label>        
            <input class="form-control nr" type="text" name="nr" size="3">
        </div>

        <div class="form-group col-md-12">
            <label for="">Usia Ekonomis</label>        
            <input class="form-control ue" type="text" name="uk" size="3">
        </div>
        
        <div class="form-group col-md-12">
            <input class="btn btn-primary btn-hitung" type="button"  value="Hitung">
            <input class="btn btn-secondary btn-clear" type="reset"   value="Clear">
        </div>

        <div class="form-group col-md-12">
            <label for="">Hasil Depresiasi</label>        
            <input class="form-control hd" type="text" name="hasil" size="3">
        </div>
    </form>
    
    </div>

  <!-- <span>Nilai Perolehan</span>
  <input type="text" name="angka1" size="3">
  <span>Nilai regulasi</span>
  <input type="text" name="angka2" size="3"><br> <br>
  <span>Usia Ekonomis</span>
  <input type="text" name="angka3" size="3"><br> <br>
  <span>Hasil Depresiasi</span>
  <input type="text" name="hasil" size="6" value=""><br>  -->


<!-- javascript -->
<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
 <script>
     $(document).ready(function(){
        // $('input').keyup(function(event) {

        //     // skip for arrow keys
        //     if(event.which >= 37 && event.which <= 40) return;

        //     // format number
        //     $(this).val(function(index, value) {
        //     return value
        //     .replace(/\D/g, "")
        //     .replace(/\B(?=(\d{3})+(?!\d))/g, ".")
        //     ;
        //     });
        // });

        function cek(){
            if (form.np.value == "" || form.nr.value == "" || form.uk.value== "") {
                alert("Angka Kosong");
                exit()
            }
        }

        function hitung(){
            cek();
            var nilai_perolehan = $(".np").val()
            var nilai_regulasi = $(".nr").val()
            var usia_ekonomis = $(".ue").val()

            console.log(nilai_perolehan+ " "+nilai_regulasi)

            var hasil_depresiasi = (nilai_perolehan - nilai_regulasi) / usia_ekonomis

            if(hasil_depresiasi){
                $(".hd").val(hasil_depresiasi)
            }
        }

        $('.btn-hitung').on('click',function(){
            hitung()
        })

     })
 </script>
</body>
</html>
