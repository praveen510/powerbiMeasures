MaxMin_Highlight = 
VAR CurrentSales = [Total_Sales]
VAR MaxSalesOverall = 
    MAXX(
        ALLSELECTED('Sales'[Date]),
        CALCULATE([Total_Sales])
    )
VAR MinSalesOverall = 
    MINX(
        ALLSELECTED('Sales'[Date]),
        CALCULATE([Total_Sales])
    )
RETURN
SWITCH(
    TRUE(),
    CurrentSales = MaxSalesOverall, "#aecf70",  -- Green
    CurrentSales = MinSalesOverall, "#ed778d",  -- Red (https://htmlcolorcodes.com/)
    "#7bc8fe"                                    -- Blue (default)
)
