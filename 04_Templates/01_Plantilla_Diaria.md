<%*
let currentDate = tp.file.title;
let weekNum = moment(currentDate).format('YYYY-[W]WW');
let yesterdayDate = moment(currentDate).subtract(1, 'days').format('YYYY-MM-DD');
let tomorrowDate = moment(currentDate).add(1, 'days').format('YYYY-MM-DD');
tR += `Semana: [[${weekNum}]]
[[${yesterdayDate}]] - [[${tomorrowDate}]]`;
_%>.
# Rituales Diarios
- [ ] 
- [ ] 
- [ ] 

<%*
let weekFile = `00_Journal/Weekly/${weekNum}`;
let weekTasks = await tp.file.include(`[[${weekFile}#Objetivos Semanales]]`);
tR += weekTasks;
_%>
---
## Reflexiones del Día