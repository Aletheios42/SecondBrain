<%*
let targetDate = tp.file.title;
let [year, month] = targetDate.split("-");
let prevMonth, nextMonth;

if (month === "01") {
   prevMonth = `${parseInt(year)-1}-12`;
   nextMonth = `${year}-02`;
} else if (month === "12") {
   prevMonth = `${year}-11`;
   nextMonth = `${parseInt(year)+1}-01`;
} else {
   let prev = parseInt(month) - 1;
   let next = parseInt(month) + 1;
   prevMonth = `${year}-${prev.toString().padStart(2,'0')}`;
   nextMonth = `${year}-${next.toString().padStart(2,'0')}`;
}

tR += `[[${prevMonth}]] - [[${nextMonth}]]`;
_%>.

# Metas
- ##
### ¿Qué proyectos tengo abiertos?
- Proyecto 1
## Objetivos Mensuales
- [ ] Tarea mensual 1
- [ ] Tarea mensual 2
- [ ] Tarea mensual 3
- - -
# Revisión: