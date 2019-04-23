# Java 8 - Date and Time

#### Get current Date:
```
        LocalDate date = LocalDate.now();                               // 2018-04-09
```


#### Get current Time:
```
        LocalTime time = LocalTime.now();                               // 06:21:10.409
```


#### Get current Date and Time:
```
        LocalDateTime dateTime = LocalDateTime.now();                   // 2018-04-09T06:21:10.410
```


#### Change the format of Date and Time:
```
        DateTimeFormatter format =  DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");   
        String formatedDateTime = current.format(format);                                       // 09-04-2018 06:21:10
```


#### Get Month, Day, Seconds, Week from Date:
```
        Month month = current.getMonth();                               // APRIL
        int day = current.getDayOfMonth();                              // 9
        int seconds = current.getSecond();                              // 10
        DayOfWeek week = LocalDate.parse("2016-06-12").getDayOfWeek();  // TUESDAY
```


#### Create a specific Date:
```
        LocalDate date2 = LocalDate.of(2019,1,26);                      // 2019-01-26
        LocalDate date3 = LocalDate.parse("2019-01-26");                // 2019-01-26                                        
```


#### Add a day:
```
        LocalDate tomorrow = LocalDate.now().plusDays(1);
```


#### Minus a Month:
```
        LocalDate previousMonthSameDay = LocalDate.now().minus(1, ChronoUnit.MONTHS);
```

