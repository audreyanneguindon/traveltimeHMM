# traveltimeHMM
Travel time prediction from GPS points using an HMM.

# Installation
```
install.packages("devtools")
devtools::install_github("melmasri/traveltimeHMM")
```

# for an example
```R
data(trips)
?traveltimeHMM  # for help
fit <- traveltimeHMM(trips$logspeed, trips$trip, trips$timeBin, trips$linkId, nQ = 2, max.it = 20)
single_trip <- subset(trips, trip==2700)
pred <- predict.traveltime(fit, single_trip$linkId, single_trip$length,single_trip$time[1])
hist(pred)      # histogram of prediction samples
mean(pred)      # travel time point estimate
sum(single_trip$traveltime)    # observed travel time
```
