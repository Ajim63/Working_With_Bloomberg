import datetime
import pandas as pd
from tia.bbg import LocalTerminal 
import matplotlib.pyplot as plt
import ipdb

def down_cur_date(ticker,event,start,end):

    f = LocalTerminal.get_intraday_bar(ticker, event, start, end, interval=10).as_frame()
    f.set_index('time',inplace=True)
    
    f = f['close']
    f = pd.DataFrame(f)
    colstr = ticker
    colstr = colstr.replace(" ","_")
    f.columns = [colstr]
    return f 

   
if __name__ == '__main__':
    Trickers = ['USCRWTIC Index', 'EUCRBRDT Index','CORNILNC Index', 'WEATTKHR Index', 'GCFPURGB Index', 'NGUSHHUB BGAP Index', 'JETIGCPR Index' ]
   
    days_back = 180

    dt = pd.tseries.offsets.BDay(-1).apply(pd.datetime.now())
    start = pd.datetime.combine(dt-datetime.timedelta(days=days_back), datetime.time(13, 30))
    end = pd.datetime.combine(dt, datetime.time(14, 30))

    data_lst = []
    event_list = ['Close']
    i = 0


    for ticker in Trickers: 
        for event in event_list:
            data_lst.append(down_cur_date(ticker,event,start=start,end=end)) 
            i = i+1
            #print "Finished with %s for %s: %i" % (ticker, event,i)
            tmpdf = pd.concat(data_lst,axis=1)
            tmpdf.to_csv('P:/Desktop/Crypto Minute/Com_tmp.csv')

    #data = pd.concat(data_lst,axis=1)
    #data.to_csv('P:/Desktop/Crypto Minute/Com.csv')

