data <- read.table('./exdata-data-household_power_consumption/household_power_consumption.txt', sep = ";",header=T)
data$Date <- as.Date(data$Date, format="%d/%m/%Y")
df <- data[(data$Date=="2007-02-01") | (data$Date=="2007-02-02"),]
df <- transform(df, timestamp=as.POSIXct(paste(Date, Time)), "%d/%m/%Y %H:%M:%S")
tail(df$timestamp)

plot(df$timestamp,df$Sub_metering_1,type = "l",ylab = "Energy sub metering",xlab="")
lines(df$timestamp,as.numeric(as.character(df$Sub_metering_2)),col="red")
lines(df$timestamp,as.numeric(as.character(df$Sub_metering_3)),col="blue")

legend("topright",inset=.05, col=c("black","red","blue"), c("Sub_metering_1  ","Sub_metering_2  ", "Sub_metering_3  "),lty=c(1,1), lwd=c(1,1))

dev.copy(png, file="plot3.png", width=480, height=480)
dev.off()
