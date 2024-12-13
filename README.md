# basededatos
'''sql
USE "bdacademia" ;
#  a) mostrar el numero de pago y el monto de pago cuyo monto de pago es el maximo.
SELECT numePago , montPago
FROM pagos  
WHERE montPagosPago=(SELECT MAX(montPago)FROM pagos);

#  b) Mostrar el número de movimiento, fecha de movimiento y estado de movimiento de las 10 primeras filas cuya fecha se encontraba entre el 24-06-2019 y el 27-06-2019 incluidas las fechas dadas.
SELECT numeMovil, fechMovi,estaMovi
FROM movimiento
WHERE fechMovi BETWEEN'2019-06-24'AND'2019-06-27'LIMIT 10;

# c) Mostrar el número de inscripción, código de año, estado de pago y monto total de pagos por cada inscripción cuyo estado es pagado (utilice group by).
SELECT numeInsc, codiAnio,estaPago, SUM(montPago) AS monto total
FROM pagos GROUP BY numeInsc, codiAnio, estaPago
HAVING estaPago = 'pagado';

# d) Seleccionarlos nombres y apellidos de los estudiantes que se encuentran matriculados en el segundo grado de secundaria.
SELECT persona.nombPers,persona.apelPers 
FROM persona 
JOIN inscripcion ON persona,dniPers
JOIN matricula ON inscripcion.numeInsc=matricula.numeInsc
WHERE matricula.niveMatri='segundo grado'

# e) Realizar una vista NOINSCRITOS para mostrar los datos de las personas a los cuales nunca se les inscribieron.
'''
