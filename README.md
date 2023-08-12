<!DOCTYPE html>
<html>
<title>Temperature Converter</title>

<script>
        function convert(from,v) {
    var c, f, k,
        f2c = function(f) { return (f - 32) * 5/9; },
        c2f = function(c) { return c * 9/5 + 32; },
        k2c = function(k) { return +k - 273.15; }, 
        c2k = function(c) { return +c + 273.15; };
    if (v !== '') switch(from) {
        case 'c':
            c = v;
            f = c2f(c);
            k = c2k(c);
            break;
        case 'f':
            f = v;
            c = f2c(f);
            k = c2k(c);
            break;
        case 'k':
            k = v;
            c = k2c(k);
            f = c2f(c);
    }
    if (from !== 'c') document.getElementById('c').value = c;
    if (from !== 'f') document.getElementById('f').value = f;
    if (from !== 'k') document.getElementById('k').value = k;
}
        </script>

    <body>
        <head>
            <style>
                body {
                    background-color: #97a0b3;
                }
    
                p {
                    color: white;
                }
    
            </style>
        </head>
    
        <h2>Temperature Converter</h2>
        <input id='c' type="number" step="any" onchange="convert('c',this.value)"/>°Celcius<br>
<input id='f' type="number" step="any" onchange="convert('f',this.value)"/>°Fahrenheit<br>
<input id='k' type="number" step="any" onchange="convert('k',this.value)" min="0"/>°Kelvin
</body>
</html> 
