# Getting-Minute-By-Minute-Data-From-Bloomberg
#This codes will allow you to collect Intraday data from Bloomberg


Set the intended intra-day period in the "interval = 1" fo minute by minute data. 

	f = LocalTerminal.get_intraday_bar(ticker, event, start, end, interval=10).as_frame()


Determine the number of days you want the data from. Bloomberg only allow 180 days back for intraday data. 
		
	days_back = 360

Set the trickers, it worked for currency, stock or index. 

	Trickers = ['USCRWTIC Index', 'EUCRBRDT Index','CORNILNC Index', 'WEATTKHR Index', 'GCFPURGB Index', 'NGUSHHUB BGAP Index', 'JETIGCPR Index' ]
