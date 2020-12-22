# 12-15



// include the library code:
#include <LiquidCrystal.h>
int x= 0;
String a[]={"A","B","C","D"};
String b[]={"C","D","A","B"};
int b1= 0;
int b2= 0;
int c1= 0;
int c2= 0;
int d= 1;
// initialize the library by associating any needed LCD interface pin
// with the arduino pin number it is connected to
const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.

}

void loop() {
  if(x==0)
  {
      lcd.setCursor(0, 0);
      lcd.print("welcome");
    if(digitalRead(7)==0)//加
  {
    lcd.clear();
    while(digitalRead(7)==0)
    x=1;
  }
    if(digitalRead(8)==0)//
  {
    lcd.clear();
    while(digitalRead(8)==0)
    x=1;
  }
  }
  if(x==1)
  { 
  if(digitalRead(7)==0)//加
  {
    d=1;
    lcd.clear();
    while(digitalRead(7)==0)
    delay(500);
    b1++;
    c1=0;
    if(b1>2)
    {
      b1=-1;
    c1=1;}
  }
  if(d==1)
  {
  if(c1<1)
  {
      lcd.setCursor(0, 0);
      lcd.print(a[b1]);
      lcd.setCursor(0, 1);
      lcd.print(a[b1+1]);
  }
  else
  {
      lcd.setCursor(0, 0);
      lcd.print(a[3]);
      lcd.setCursor(0, 1);
      lcd.print(a[0]);
  }
  }
      if(digitalRead(8)==0)//減
  {
    d=2;
    lcd.clear();
    while(digitalRead(8)==0)
    delay(500);
    b1--;
    c2=0;
    if(b1<0)
    {
      b1=3;
      ;
    c2=1;}
  }
    if(d==2)
  {
  if(c2<1)
  {
      lcd.setCursor(0, 0);
      lcd.print(a[b1]);
      lcd.setCursor(0, 1);
      lcd.print(a[b1+1]);
  }
  else
  {
      lcd.setCursor(0, 0);
      lcd.print(a[3]);
      lcd.setCursor(0, 1);
      lcd.print(a[0]);
  }
  }
  }
}
