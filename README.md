# README.md

Uppgift till kurs DT084G, Webbutveckling, Mittuniversitetet.
Av Johanna H

Ett program som tar aktuellt datum och klockslag och konverterar detta för utskrift.
Tre stycken format för utskrift:

* 10:38, 2022-09-21
* September 21, 2022 - 10:38
* Onsdag 21/9, kl. 10.38


```Javascript
function printDateAndTime(option) { 
    let atm = new Date();
    let year = atm.getFullYear();
    let month = atm.getMonth() + 1;
    let day = atm.getDate();
    let dayOfWeek = atm.getDay();
    let hour = atm.getHours();
    let minutes = atm.getMinutes();

    let monthNames = ["Januari", "Februari", "Mars", "April", "Maj", "Juni", "Juli", "Augusti", "September", "Oktober", "November", "December"];
    let dayNames = ["Söndag", "Måndag", "Tisdag", "Onsdag", "Torsdag", "Fredag", "Lördag"];

    if (hour < 10) {
        hour = "0" + hour;
    }
    if(month < 10){
        month = "0" + month;
    }
    if (day < 10){
        day = "0" + day;
    }

    switch (option){ 
        case 1:
            console.log(`${hour}:${minutes}, ${year}-${month}-${day}`);
            break;
        case 2: 
            console.log(`${monthNames[month -1 ]} ${day}, ${year} - ${hour}:${minutes}`);
            break;
        case 3:
            console.log(`${dayNames[dayOfWeek]} ${day}/${month}, kl. ${hour}.${minutes}`);
            break;

    }
} 
    printDateAndTime(1);
    printDateAndTime(2);
    printDateAndTime(3);
```

