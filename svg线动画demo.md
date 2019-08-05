```
<!DOCTYPE html>
<html>
    <head>
        <style>
            .cls-1{
                fill:none;
                stroke:#000;
                stroke-width:2px;
                animation: paint 2s linear forwards;
            }
            @keyframes paint{
                to{
                    stroke-dashoffset: 0;
                }
            }
            #outline{
                stroke-dashoffset: 578px;
                stroke-dasharray: 578px
            }
            #stock{
                stroke-dashoffset: 145px;
                stroke-dasharray: 145px
            }
            #inside-l{
                stroke-dashoffset: 212px;
                stroke-dasharray: 212px;
                animation-delay: 0.5s
            }
            #inside-r{
                stroke-dashoffset: 212px;
                stroke-dasharray: 212px;
                animation-delay: 1s
            }
            #drop{
                stroke-dashoffset: 28px;
                stroke-dasharray: 28px
            }
            .box{
                transform-origin: 50% 50%;
                transform: matrix(1,0,0,1,0,0);
                width:100px;
                height:100px;
                background: red;
            }
        </style>
    </head>
    <body>
        <div class="box"></div>
        <g transform="matrix(1,2,3,4,5,6)">
            <line x1="10" y1="20" x2="30" y2="40" style="stroke-width: 10px; stroke: blue;"/>
          </g>
</svg>
            <svg id="popsicle" viewBox="0 0 236 284">
                <title>未标题-1</title>
                <path id="drop" class="cls-1" d="M82.1,243.61s-6.45,10.58-1.29,12.13S82.1,243.61,82.1,243.61Z"/>
                <path id="stock" class="cls-1" d="M130,212.89V270s-7,7-12,7-12-7-12-7V211"/>
                <path id="inside-l" class="cls-1" d="M93.93,79c9.78-1.84,11.94,30,11.94,51s2,45-10,45S81,146,81,127,78,82,93.93,79Z"/>
                <path id="inside-r" class="cls-1" d="M142.93,79.08c9.78-1.84,11.94,30,11.94,51s2,45-10,45S130,146,130,127,127,82.07,142.93,79.08Z"/>
                <path id="outline" class="cls-1" d="M118,27c40.72,4.79,57,14,59,22s0,83,0,104,3,56-22,58c-15.39,1.23-41,2.84-61.22.17C89.36,210.58,83.74,234,80,233c-7-1.94-11-29-14-33C54,184,47,112,53,79S84,23,118,27Z"/>
            </svg>
        <script>
        
        </script>
    </body>
</html>
```
