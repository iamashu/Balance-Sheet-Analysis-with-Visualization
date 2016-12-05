library(quantmod)
library(zoo)
library(TTR)
getSymbols("AAPL")
getSymbols("AAPL", src = "yahoo")
hist <- getYahooData("AAPL",20130101,20131203)
str(hist)
head(hist)
plot(hist$Close)
plot(hist$Low/hist$High)
viewFin(AAPL.f,type="BS",period="A")
apple <- getFin("AAPL")
AAPL.f
viewFin(AAPL.f,type="BS",period="A")
DF = viewFin(AAPL.f,"BS","A")
rownames(DF)
CA = DF["Total Current Assets",]
CA 
lineChart(CA)
GA = DF["Total Current Assets",]
FA = DF["Total Current Liabilities",]
XA = GA / FA
XA
HA = DF["Total Equity",]
YA = DA/HA
YA
barChart(YA,theme = 'white', type = 'hlc')
pie(CA,col = rainbow(length(x)))
INT = DF["Intangibles, Net" ,]
GOO = DF["Goodwill, Net" ,]
TCE = HA - INT - GOO 
ASS = DF["Total Assets" ,]
TCER = TCE/ASS
TCER
lineChart(TCER)
GTA = GOO/ASS
GTA
lineChart(GTA)
RET = DF["Retained Earnings (Accumulated Deficit)" ,]
RET
counts <- c(GA,FA)
barplot(counts,col=c("darkblue","red"),beside = TRUE,)
LTD = DF["Total Long Term Debt" ,]
LTD
chartSeries(LTD)