# Javascript module 2

## opracht 1
#### kerstkaart
![ABC](/img/Schermafbeelding%202025-11-21%20100842.png)
# codes:
# html:

<img width="1126" height="370" alt="image" src="https://github.com/user-attachments/assets/e8e5d02d-8595-4807-936c-7d13d2860f21" />




# js:



const canvas = document.getElementById("canvasId");
const g = canvas.getContext("2d");

g.fillStyle = "darkblue";

g.fillStyle = "darkblue";
g.fillRect(0, 0, canvas.width, canvas.height);

function drawTree(x, y) {

    g.fillStyle = "brown";
    g.fillRect(x + 70, y + 220, 30, 70);


    const gradient = g.createLinearGradient(x, y, x, y + 260);
    gradient.addColorStop(0, "green");
    g.fillStyle = gradient;


    g.beginPath();
    g.moveTo(x + 85, y);
    g.lineTo(x, y + 220);
    g.lineTo(x + 170, y + 220);
    g.closePath();
    g.fill();


    g.fillStyle = "yellow";
    g.beginPath();
    g.arc(x + 85, y - 15, 15, 0, Math.PI * 2);
    g.fill();


    const placedBalls = [];

    for (let i = 0; i < 8; i++) {
        let ballX, ballY, valid;
        const radius = 10;


        do {
            ballX = x + 20 + Math.random() * 100;
            ballY = y + 20 + Math.random() * 100;

            valid = true;
            for (const b of placedBalls) {
                const dx = ballX - b.x;
                const dy = ballY - b.y;
                const dist = Math.sqrt(dx * dx + dy * dy);
                if (dist < radius * 2 + 5) {
                    valid = false;
                    break;
                }
            }
        } while (!valid);

        placedBalls.push({ x: ballX, y: ballY });

        g.fillStyle =
            "hsl(" + Math.floor(Math.random() * 360) + ", 90%, 60%)";

        g.beginPath();
        g.arc(ballX, ballY, radius, 0, Math.PI * 2);
        g.fill();
    }
}


function drawHouse(x, y) {

    g.fillStyle = "brown";
    g.fillRect(x, y, 100, 70);


    g.fillStyle = "black";
    g.beginPath();
    g.moveTo(x, y);
    g.lineTo(x + 50, y - 30);
    g.lineTo(x + 100, y);
    g.fill();


    const hour = new Date().getHours();
    const lightsOn = hour >= 18;


}


drawTree(320, 50);


let usedPositions = [];
for (let i = 0; i < 4; i++) {
    let x;


    do {
        x = 50 + Math.random() * 650;
    } while (usedPositions.some(px => Math.abs(px - x) < 120));

    usedPositions.push(x);

    drawHouse(x, 360);
}


g.fillStyle = "yellow";
g.font = "48px serif";
g.fillText("MERRY CHRISTMAS", 250, 580);
## opdract 2
#### order the array
<img width="1550" height="894" alt="image" src="https://github.com/user-attachments/assets/26b11ab3-c452-4dff-95e8-ba0a4df773e0" />
