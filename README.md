# pacman
Create a classic animation of the Pacman chasing a ball using HTML and CSS, and tailor it with your own unique style.

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> 🎮 G A m E B o Y ! </title>
    <style>
  
        *,
        *::after,
        *::before {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            background-image: url(./img/d.gif);
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }

        .gameboy {
            width: 600px;
            height: 800px;
            margin: auto;
            margin-top: 100px;
            background-image: url(./img/588px-Gameboy.svg.png);
            background-size: contain;
            background-repeat: no-repeat;
            background-position: contain;
            display: flex;
        }


        .screen {
            width: 260px;
            height: 260px;
            background-image: linear-gradient(to right, #141e22 0%, #010303 100%);
            border-radius: 10px;
            display: flex;
            margin-left: 118px;
            margin-top: 100px;
            overflow: hidden;
            border: 3px solid rgb(236, 213, 84);

        }

        .gradient {
            position: absolute;
            width: 254px;
            height: 80px;
            background-image: linear-gradient(-60deg, #16a085 0%, #f4d03f 100%);
            top: 300px;

        }

        .pacman {
            position: relative;
            width: 5%;
            height: 2px;
            animation-name: run;
            animation-timing-function: linear;
            animation-duration: 2s;
            animation-iteration-count: infinite;
            top: 40%;
            z-index: 2;
        }

        .pacman::before {
            content: "";
            border-width: 30px;
            position: absolute;
            border-radius: 50%;
            border-style: solid;
            border-top-color: salmon;
            border-left-color: salmon;
            border-bottom-color: transparent;
            border-right-color: transparent;
            animation: mouth-open 0.5s ease infinite;
        }

        .pacman::after {
            content: "";
            border-width: 30px;
            position: absolute;
            border-radius: 50%;
            border-style: solid;
            border-top-color: transparent;
            border-left-color:  salmon;
            border-bottom-color: salmon;
            border-right-color: transparent;
            animation: mouth-close 0.5s ease infinite;

        }

        .pacman-eye {
            position: absolute;
            width: 12px;
            height: 12px;
            border-radius: 100%;
            top: 10px;
            left: 20px;
            background: rgb(255, 255, 255);
            z-index: 1;
        }

        .pacman-eye::before {
            content: "";
            position: absolute;
            width: 8px;
            height: 8px;
            border-radius: 100%;
            left: 6px;
            top:1px;
            background: rgb(49, 47, 47);
            z-index: 1;
        }

      

        .ball-container {
            position: relative;
            display: flex;
            justify-content: space-between;
            animation: ball-move 2s linear infinite;
            
            top: 130px;
            background-image: url(./img/2b50.gif);
            
        }

        .ball {
            transform: translateY(-50%);
            height: 20px;
            width: 15px;
            background-image: url(./img/2b50.gif);
            margin-right: 100px;
            border-radius: 100%;
            background-color: rgb(220, 242, 227);
            background-image: url(./img/2b50.gif);

        }

 
        @keyframes ball-move {
            0% {
                transform: translateX(35%);
                opacity: 1;
            
            
            }
            100% {
                /* transform: translateX(-100%); */
                opacity: 0;
            }
        }
        

        @keyframes mouth-open {
            50% {
                transform: rotate(40deg);
            }
        }

        @keyframes mouth-close {
            50% {
                transform: rotate(-40deg);
            }
        }

        @keyframes run {
            0% {
                left: 1%;
            }
            25% {
                left: 30%;
                transform: scale(1.2);
            }
            50% {
                left: 50%;
                transform: scale(1.5);
            }
            75% {
                left: 70%;
                transform: scale(1.2);
            }
            

            100% {
                left: 90%;
                transform: scale(1);
            }
        }
        
    </style>
</head>

<body>
    <div class="gameboy">
        <div class="screen">
            <div class="gradient"></div>
            <div class="pacman">
                <div class="pacman-eye"></div>
            </div>
            <div class="ball-container">
                <div class="ball"></div>
                <div class="ball"></div>
                <div class="ball"></div>
                <div class="ball"></div>
                <div class="ball"></div>
            </div>
        </div>
    </div>
</body>

</html>
