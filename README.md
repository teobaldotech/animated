# animated
//animated sign
<!DOCTYPE html>
<html>
<head>
    <title>Animçao digitando...</title>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdn.bootcss.com/typed.js/1.1.4/typed.min.js"></script>
    <style type="text/css">
        .write{
            font-size: 55px;
            background-color: rgb(187, 88, 162);
        }
        .container{
            text-align: center;
            color:aquamarine;
        }
    </style>
</head>
<body>
  
<div class="container">
    <span class="write"></span>
</div>
<script type="text/javascript">
  
    


  $(function(){
    $(".write").typed({
        strings: ["Bem vindo ao letreiro animado , obrigado por visitar"],
        typeSpeed: 1,
    });
});
</script>
</body>
</html>
