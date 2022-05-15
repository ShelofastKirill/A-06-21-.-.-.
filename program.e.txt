program lab6;
{$APPTYPE CONSOLE}
uses
  Windows;
var x,s,a,b,y,o:real;
    z:integer;

begin
  setConsoleCP(1251);
  setConsoleOutputCP(1251);
  writeln('нахождение квадратного корня числа.');
  writeln('введите число от которого надо взять квадратный корень(число должно быть больше 0)');
  readln(x);
  o:=x;
  if(x>0)then begin
    writeln('введите количество знаков после ","([1;17])');
    readln(z);
    if(z>=1) and (z<=17) then begin
      s:=x;
      a:=0;
      b:=x;
      while(abs(a-b)>exp(ln(10)*-7)) do begin
        a:=(a+b)/2;
        b:=s/a;
      end;
      y:=(a+b)/2;
      write('sqrt(',o:0:10,')=');
      writeln(y:0:z);
    end;
    if (z<1) or (z>17) then writeln('некорректный ввод данных число должно быть >=1 и <=17');
  end;
  if (x<=0) then writeln('некорректный ввод данных число должно быть больше 0');
  readln;
end.
