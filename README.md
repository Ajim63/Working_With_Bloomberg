# Getting-Minute-By-Minute-Data-From-Bloomberg
#This codes will allow you to collect Intraday data from Bloomberg




f = LocalTerminal.get_intraday_bar(ticker, event, start, end, interval=10).as_frame()

#Set the intended intra-day period in the "interval = 1" fo minute by minute data. 

days_back = 360
#Determine the number of days you want the data from. Bloomberg only allow 180 days back for intraday data. 

