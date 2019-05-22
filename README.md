# CC2-Processing-Project

PFont myFont;
PImage galaxy;
int r = (int)(random(0,255));
int b = (int)(random(0,255));
int g = (int)(random(0,255));
int alpha = (int)(random(50,100));
float xPos = mouseX;
float yPos = mouseY;
float randomWidthAndHeight = random(0,10);

void setup()
{
  size(1300,800);
  noStroke();
  
  galaxy = loadImage("download.jpeg");
  background(galaxy);
  
  myFont = createFont("Papyrus", 18);
  textFont(myFont);
  textAlign(CENTER, CENTER);
  text("Move the mouse for circles, click the mouse for squares, click and move the mouse for both, and press the spacebar for a new screen.", width/2, height/2);
}

void draw()
{
  if (mousePressed)
  {
  stroke(255,0); //second variable = alpha/transparency
  line(mouseX, 0, mouseX, height);
  line(0, mouseY, width, mouseY); 
 
  xPos = random(width);
  yPos = random(height);
  randomWidthAndHeight = random(0,100);
  r = (int)(random(0,255));
  b = (int)(random(0,255));
  g = (int)(random(0,255));
  alpha = (int)(random(50,100));
  rect(xPos, yPos, randomWidthAndHeight, randomWidthAndHeight);
  fill(r,g,b,alpha);
  }
}

void keyPressed()
{
  if(key == (char)32) //spacebar
  {
    alpha -= 50;
    background(random(0,255),alpha);
  }
}

void mouseMoved()
{
  xPos = random(width);
  yPos = random(height);
  randomWidthAndHeight = random(0,100);
  r = (int)(random(0,255));
  b = (int)(random(0,255));
  g = (int)(random(0,255));
  alpha = (int)(random(50,100));
  ellipse(xPos, yPos, randomWidthAndHeight, randomWidthAndHeight);
  fill(r,g,b,alpha);
}
