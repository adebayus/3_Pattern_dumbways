### This is a third-tier heading

You can use one `#` all the way up to `######` six for different heading sizes.
### Aplikasi Yang Digunakan

1. Vs Code

### Cara Menjalakan Aplikasi

2. node "nama_file.js"

### Sedikit Penjelasan Code

1. membuat file html beserta membuat div dengan id root

```html
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

</head>
<body>
    <div id="root">

    </div>
</body>
</html>

``` 
2. menambahkan javascript

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="index.css">
    <!-- <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous"> -->
</head>
<body>
    <div id="root">

    </div>
    <script>
        const kata="DUMBWAYS"
        var kataLength = kata.length-1
        const kataToArray = kata.split("")
        
        //  row 
        var makeRow = document.createElement("div")
        makeRow.className = "row"

        // col
        var makeCol = document.createElement("div")
        makeCol.className = "col"


        for (let i = 0; i < kata.length; i++) {
            document.getElementById('root').appendChild(makeRow.cloneNode(true))
            var classRowLength = document.getElementsByClassName("row")
            var lastIndexRow = classRowLength.length-1
            
            for (let y = 0; y < kata.length; y++) {
                document.getElementsByClassName('row')[lastIndexRow].appendChild(makeCol.cloneNode(true))
                var classColLength = document.getElementsByClassName("col")
                var lastIndexCol = classColLength.length-1
                if(i === y || kataLength === y ){

                    var text = document.createTextNode(`${kataToArray[y]}`)
                    document.getElementsByClassName('col')[lastIndexCol].appendChild(text)

                }
                else{
                    var text = document.createTextNode(` `)
                    document.getElementsByClassName('col')[lastIndexCol].appendChild(text)  
                }
                
            }

            kataLength--
            
        }

    </script>
</body>
</html>

```
3. menambahkan css
```css
*{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
}

#root {
    margin: 100px auto;
    max-width: fit-content;
}

.row{
    
    display: flex;
    max-width: fit-content;

}

.col{
    border: 1px solid darkgray;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 20px;

}

```
