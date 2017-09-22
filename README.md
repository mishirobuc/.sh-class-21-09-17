# .sh-class-21-09-17
commands 


#solo imprime lo que esta en comillas
>echo 'foo\nbar \nfoo' |sort | uniq -e |sort -nr  
#imprime 10 lineas (Line 1....Line 10)
>seq -f  "Line %g" 10 | tee lines
#los siguientes cuatro comandos sirven para imprimir las primeras 3 lineas
<lines head -n3
<head -n3 lineas
<lines awk  'NR<=3'
< lines sed -n '1,3p'
#imprime las ultimas 3 lineas
<lines tail -n3
#imprimen de la linea 4 a la 10
<lines tail -n +4
<lines sed '1,3d'
#imprime dos veces cada linea a partir de la linea 4
<lines sed '1,3!p'
#imprimen de la linea 4 ala 6
<lines sed -n '4,6p'
<lines awk '(NR>=4)&&(NR<=6)'
<lines head -n6| tail -n3
#imprimen las lineas impares 
<lines sed -n '1~2p'
<lines awk 'NR %2'
#imprimen las lineas pares
<lines sed -n '0~2p'
<lines awk '(NR+1)%2'
#remplazan los espacios del texto por guion bajo
echo "hello world!" |tr  ' ' '_'
#remplaza los signos de admiracion por signos de interrogacion
echo "hello world!" |tr  ' !'  '?'
#imprime borrando los espacios, saltos de linea y signos de admiracion
echo "hello world!" |tr  -d -c '[a-z]'
#convierten el texto de minusculas a mayusculas mayusculas
echo "hello world!" |tr  '[a-z]'  '[A-Z]'
echo "hello world!" |tr  '[:lower:]' '[:upper:]'
#cambia la palabra hello por bye
echo "hello world!" | sed -re  's/hello/bye/;s/\s+//gis/ls+//'
