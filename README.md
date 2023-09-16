# movingeffectfeature

<!-- The code you provided is an HTML document. It defines the structure and content of a web page. Let's
break it down: -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style2.css">
</head>
<body>
    

    <div id="cursor"></div>
    <div id="rect">
        <img src="https://plus.unsplash.com/premium_photo-1674248775248-0feaf59b0f55?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1930&q=80" alt="">
    </div>




    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js" integrity="sha512-16esztaSRplJROstbIIdwX3N97V1+pZvV33ABoG1H2OyTttBxEGkTsoIVsiP1iaTtM8b3+hu2kB6pQ4Clr5yug==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <script src="script2.js"></script>
</body>
</html>


// cxs
/* The CSS code you provided is setting some styles for various elements in a web page. */
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html,body
{
    width: 100%;
    height: 100%;
    cursor: none;
}


 #rect {
    width: 300px;
    height: 180px;
    background-color: black;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
}

#rect img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
}


#cursor{
    width: 13px;
    height: 13spx;
    background-color: black;
    /* mix-blend-mode: difference; */
    position: absolute;
    border-radius: 50%;
    z-index: 100;

}

/* The code is creating a rectangle element and moving it based on the position of the mouse cursor.
The rectangle's position is mapped to the mouse position, so as the mouse moves to the left, the
rectangle moves to the left as well. The speed of the rectangle's movement slows down as the mouse
moves further to the left. Additionally, the code changes the background color of the body element
and updates the image inside the rectangle element every second. */
// ek rectagle baano  and mouse center pe ho rect center pe ho, jav mouse left jana shuru ho rect bhi left jna shuru hojaye , pr jese jese mouse left jaye rect ki speed left me jate jate speed slow hojaye, 

var cursor = document.querySelector("#cursor");
var body = document.querySelector("body");
var rect = document.querySelector("#rect");

/// innerwidth mtlb woh screen jo use horhi hai width mein

window.addEventListener("mousemove", function(dets){
    var xvalue = gsap.utils.mapRange(0, window.innerWidth, 80+rect.getBoundingClientRect().width/2 , window.innerWidth-(80+rect.getBoundingClientRect().width/2), dets.clientX);
   

    gsap.to(cursor, {
        left: dets.clientX + "px",
        top: dets.clientY + "px",
        ease:Power1,
        scale:2,
        
    })


    var yvalue = gsap.utils.mapRange(0, window.innerHeight, 80+rect.getBoundingClientRect().height/2 , window.innerHeight-(80+rect.getBoundingClientRect().height/2), dets.clientY);



    var img  = this.document.querySelector("#rect img");
    var allimages  = [
        "https://images.unsplash.com/photo-1692764619881-0c41dcdbab2c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwxNXx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
    
    
        "https://plus.unsplash.com/premium_photo-1692340973236-e4617a167ff4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw1MXx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
    
        "https://images.unsplash.com/photo-1692555331534-47b8c0061803?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw1OHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
    
        "https://images.unsplash.com/photo-1687360440613-7e002b7261da?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHw4M3x8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
    
        "https://images.unsplash.com/photo-1691856630890-9270899274a0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyMzF8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=500&q=60",
    
    
        "https://images.unsplash.com/photo-1687360440155-81bdb9ecd713?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwyOTh8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=500&q=60",
    
    
        "https://plus.unsplash.com/premium_photo-1692340973390-ed4a319f129d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwzMTR8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=500&q=60",
    
        "https://images.unsplash.com/photo-1692423018159-1820c667b1fd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw0MDB8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=500&q=60",

        "https://images.unsplash.com/photo-1682687982183-c2937a74257c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2071&q=80",


        "https://images.unsplash.com/photo-1694428275090-c8668a271519?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1932&q=80",



    
    ]

    var index = 0;
   
    function imagechange(){
        setInterval(function(){
            img.setAttribute("src", allimages[index]);
            index++;
        } , 1000);
    }


    var a = Math.floor(Math.random() * 255)
    var b = Math.floor(Math.random() * 255)
    var c = Math.floor(Math.random() * 255)


    function bodycolorchange(){
          gsap.to(body, {
            backgroundColor :  `rgba(${a}, ${b}, ${c})`,
            ease:Power1,     
          })
    }

    gsap.to("#rect", {
         onStart: function(){
            imagechange();
            bodycolorchange();
         },

        
        left: xvalue + "px", 
        // left: dets.x + "px",
        top: yvalue + "px",
        ease:Power3,

    })
})

