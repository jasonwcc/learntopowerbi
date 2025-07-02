DateT = ADDCOLUMNS(
    CALENDAR( DATE(2017,1,1), DATE(2020,12,31) ),
    "Year", YEAR([Date]),
    "FyYear", "FY" & YEAR([Date]),
    "Quarter", IF( MONTH([Date]) <= 3, 3,
            IF( MONTH([Date]) <= 6, 4,
            IF( MONTH([Date]) <= 9, 1,2 )
            )),
    "Month", month([Date]),
    "Month Lname", FORMAT([Date], "Mmmm"),
    "MonthKey1", FORMAT([Date], "yyyy MMM"),
    "MonthKey2", (YEAR([Date]) * 100) + MONTH([Date]),
    "Day", DAY([Date]),
    "WeekDay", WEEKDAY([Date],2),
    "Week Sname", FORMAT([Date], "Ddd"),
    "Week Num", WEEKNUM([Date],2)
)
