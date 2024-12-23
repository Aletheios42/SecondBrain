<%*
let targetDate = tp.file.title;
let weekDate = moment(targetDate, "YYYY-[W]WW");
let month = weekDate.format("YYYY-MM");

let prevWeek = weekDate.clone().subtract(1, 'weeks').format("YYYY-[W]WW");
let nextWeek = weekDate.clone().add(1, 'weeks').format("YYYY-[W]WW");

tR += `Mes: [[${month}]]
[[${prevWeek}]] - [[${nextWeek}]]`;
_%>.
## Objetivos Semanales
- [ ] Tarea semanal 1
- [ ] Tarea semanal 2
- [ ] 

<%*
let monthTasks = await tp.file.include(`[[00_Journal/Monthly/${month}#Objetivos Mensuales]]`);
tR += monthTasks;
_%>
# Revisión: