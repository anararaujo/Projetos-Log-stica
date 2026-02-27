# Projetos Logistica
Aqui é onde salvo todos os projetos elaborados em sala de aula a partir do 3° semestre do curso de Logística da Fatec Jessen Vidal.


## CÓDIGO PYTHON DA ATIVIDADE 2 PO
!pip install pulp
from pulp import *
problema1 = LpProblem('Producao_monobloco', LpMinimize)
x11 = LpVariable ("11", lowBound= 0)
x12 = LpVariable ("12", lowbound= 0)
x13 = LpVariable ("13", lowbound= 0)
x22 = LpVariable ("22", lowbound= 0)
x23 = LpVariable ("23", lowbound= 0)
x33 = LpVariable ("33", lowbound= 0)
problema1+= 3000*x11 + 3200*x12 + 3400*x13 + 3000*x22 + 3200*x23 + 3200*x33
problema1 += x11 + x12 + x13 <= 2500
problema1 += x22 + x23 <= 2500
problema1 += x33 <= 2000
problema1 += x11 == 1000
problema1 += x12 + x22 == 2000
problema1 += x13 + x23 + x33 == 3000
problema1
PROBLEMA1.SOLVE()
for V in problema1.variables () :
print (v.name, "=", V.varValue)
print('custo total =', value(problema1.objective))
