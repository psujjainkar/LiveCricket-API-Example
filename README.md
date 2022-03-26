<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.12.9/dist/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
    <title>Document</title>

    <style>

            #demo 
            {

                background-color:rgb(228, 228, 228);
                padding:10px;
                border:solid 1px black;
                border-radius: 10px;
                width:400px;
                font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

            }

    </style>


</head>
<body>
    
   

    <ul id="list1" class="list-group bg-primary">
        
      </ul>
    
  

<script>

const settings = {
	"async": true,
	"crossDomain": true,
	"url": "https://livescore6.p.rapidapi.com/matches/v2/list-live?Category=cricket",
	"method": "GET",
	"headers": {
		"X-RapidAPI-Host": "livescore6.p.rapidapi.com",
		"X-RapidAPI-Key": "7cf3ddde6dmsha9a32b4fb4fe9b1p1e9483jsnabe46e9b6f75"
	}
};

$.ajax(settings).done(function (response) {
	
        
    //console.log(response.Stages[0].Events[0].ECo);
    //document.getElementById('demo').innerHTML=JSON.stringify((response.Stages[0].Events[0].ECo));
    
    var featureData=response.Stages;

     //console.log("data : "+JSON.stringify(featureData));
     console.log(response);
    


    for(var k in featureData) {
               // console.log(k, featureData[k].attributes.DTENAME);
                
              // getDTNCode1 = featureData[k].Snm;
              // getDTNCode2 = featureData[k].Cnm;
             //  getDTNCode3 = featureData[k].ECo;
               
               
               //console.log(JSON.stringify("Teams : "+getDTNCode1+" | Series Name  : "+ getDTNCode2));
               
               
               console.log(JSON.stringify(response.Stages[k].Cnm));
              //  console.log("result : "+JSON.stringify(getDTNCode3));
             // console.log(response.Stages[k].Events[0].ECo);
             
                // document.getElementById('demo').innerHTML = "\n"+JSON.stringify(getDTNCode);
              //  $("#demo").append(getDTNCode);      
                
             //    $("#selectTeam").append($("<option></option>").val(featureData[k].Snm).html(featureData[k].Snm));      

             $("#list1").append($("<li class='list-group-item list-group-item-info'>"+"<span class='badge badge-danger'>"+featureData[k].Snm+"</span class='badge badge-primary'> "+"<span>"+response.Stages[k].Events[0].ECo+" </span> "+ "<span class='badge badge-primary'>"+response.Stages[k].Cnm+"</span>"+"</li>"));    
             
             
            }




});

</script>


</body>
</html>
