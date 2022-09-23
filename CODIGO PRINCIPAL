//Epic Australian Open
//Pablo Miranda, Facundo Ortiz, Lucas Ortiz, Anabel Torres
boolean finjuego= false, derecha = false, izquierda = false, d = false, a = false;
int puntosmax=0;
int puntosmin=0;
float cambiovel=0;
Tenis min;
pelota pelotita;
Tenis max;
void setup()
{
  frameRate(160);
  noStroke();
  pelotita= new pelota();
  min=new Tenis();
  max=new Tenis();
  max.y=0;
  size(500, 550);
}
void keyPressed()
{
  if (keyCode == LEFT)
  {
    izquierda = true;
  }
  if (keyCode == RIGHT)
  {
    derecha = true;
  }
  if (key == 'a')
  {
    a=true;
  }
  if (key == 'd' )
  {
    d=true;
  }
}
void keyReleased()
{
  if (keyCode == LEFT)
  {
    izquierda = false;
  }
  if (keyCode==RIGHT)
  {
    derecha = false;
  }
  if (key=='a')
  {
    a=false;
  }
  if (key=='d')
  {
    d=false;
  }
}
void draw()
{
  if (finjuego==false)
  {
    background(0);
    min.show();
    max.show();
    if (izquierda==true)
    {
      min.moveizquierda();
    }
    if (derecha==true)
    {
      min.movederecha();
    }
    if (a==true)
    {
      max.moveizquierda();
    }
    if (d==true)
    {
      max.movederecha();
    }
    pelotita.move();
    pelotita.bounce();
    pelotita.show();
    if (pelotita.y<-8)
    {
      finjuego=true;
      puntosmin++;
    }
    if (pelotita.y>508)
    {
      finjuego=true;
      puntosmax++;
    }
  } else //finjuego==true
  {
    background(0);
    fill(#FCD803);
    cambiovel=0;
    textSize(17);
    text("Jugador 1 / Puntos: "+puntosmax, 15, 250);
    text("Jugador 2 / Puntos: "+puntosmin, 15, 290);
    textSize(36);
    text("¡Punto! Click para reiniciar.", 15, 200);
    textSize(17.5);
    text("Pablo Miranda, Facundo Ortiz, Lucas Ortiz, Anabel Torres", 5, 340);
    if (mousePressed==true)
    {
      pelotita.x=int(random(200, 301));
      pelotita.y=int(random(200, 301));
      int xdirection=int(random(2));
      int ydirection=int(random(2));
      if (xdirection==0)
      {
        pelotita.derecha=true;
      } else //xidrection==1
      {
        pelotita.derecha=false;
      }
      if (ydirection==0)
      {
        pelotita.up=true;
      } else //ydirection==1
      {
        pelotita.up=false;
      }
      finjuego=false;
    }
  }
}
class Tenis
{
  int x, y;
     PImage img;
  Tenis()
  {
    x=250;
    y=496;
     img= loadImage("wachin.png");
   
  }
  void show()
  {


    image(img, 180, 200);
    
    fill(#FFDA05);
    rect(x, y, 110, 40);
    
  }
  void moveizquierda()
  {
    if (x>=0)
    {
      x-=5;
    }
  }
  void movederecha()
  {
    if (x<=440)
    {
      x+=5;
    }
  }
}
class pelota
{
  int x, y;
  boolean up, derecha;
  pelota()
  {
    x=16;
    y=484;
    up=true;
    derecha=true;
  }
  void move()
  {
    if (up==true)
    {
      y=int(y-2-cambiovel/2);
    } else  //up==false
    {
      y=int(y+2+cambiovel/2);
    }
    if (derecha==true)
    {
      x=int(x+1+cambiovel);
    } else  //derecha==false
    {
      x=int(x-1-cambiovel);
    }
  }
  void bounce()
  {
    if (get(int(x)-8, int(y))!=color(0))
    {
      derecha=true;
    }
    if (get(int(x)+8, int(y))!=color(0))
    {
      derecha=false;
    }
    if (get(int(x), int(y)-8)==color(#FFDA05))
    {
      up=false;
    }
    if (get(int(x), int(y)+8)==color(#FFDA05))
    {
      up=true;
      cambiovel+=1.0/4;
    }
  }
  void show()
  {
    fill(#00FA27);
    ellipse(x, y, 30, 30);
  }
}
