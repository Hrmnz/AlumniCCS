
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.0/jquery.min.js"></script>
<script>
$(document).ready(function() {
    $.ajax({
        type: "GET",
        url: "data.txt",
        dataType: "text",
        success: function(data) {processData(data);}
     });
});

function processData(allText) {
    var allTextLines = allText.split(/\r\n|\n/);
    var headers = allTextLines[0].split(',');
    var lines = [];

    for (var i=1; i<allTextLines.length; i++) {
        var data = allTextLines[i].split(',');
        if (data.length == headers.length) {

            var tarr = [];
            for (var j=0; j<headers.length; j++)
            {
                tarr.push(headers[j]+":"+data[j]);
            }
            lines.push(tarr);
        }
    }
    alert(lines[1]);
    // alert(lines);
}
</script>
</head> 
# AlumniCCS
Project for CCS - Thapar University ,Passouts

To store data CSV file format will be used.
To retrieve data javascript will be used.
Updation will be done manually.

UPTIL NOW: ALERT pop up is the retrieved data in desired format from csv file (data.txt)
raw data was :

heading1,heading2,heading3,heading4,heading5
value1_1,value2_1,value3_1,value4_1,value5_1
value1_2,value2_2,value3_2,value4_2,value5_2
