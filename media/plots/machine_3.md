# Machine 3 Analysis Log
library(qcc)
# Using type='xbar.one' for individuals charts
qcc(m_data$PartLength, type='xbar.one')
process.capability(qcc_obj, spec.limits=c(45, 55))
