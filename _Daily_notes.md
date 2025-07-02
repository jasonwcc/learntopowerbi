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


# example 2
Orders By Visuals = {
    ("Brand", 1, UNICHAR(129522) & " "),
    ("Category",  2,UNICHAR(128757) & " Product"),
    ("Category", 3,UNICHAR(129528) & " Bike"),
    ("Store Country", 4, UNICHAR(127757) & " Store"),
    ("Customer Country", 5, UNICHAR(127978) & " Customer")
}

# example 3
CurrenciesInSaving = {("MYR", 2000), ("SGD", 1000), ("USD", 5000)}

