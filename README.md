# 🏥 Physician Schedule Optimization

A compact probabilistic modeling project focused on a common healthcare operations problem: how many appointments should be booked when not every patient is expected to attend?

## 💼 Business use case

A physician can see up to 30 patients per day, while historical scheduling data suggest that roughly 25% of booked patients do not show up. Booking too few appointments leaves clinical capacity unused and can reduce revenue. Booking too many creates a different set of problems, including longer waits, overtime, rescheduling, and a poorer patient experience.

This project treats scheduling as a risk-based decision rather than relying only on average attendance. A binomial model is used to estimate how likely different arrival levels are under alternative booking decisions.

## 🎯 Principal objective

The objective is to identify booking levels that make better use of available capacity while keeping the probability of exceeding the physician's daily workload within an acceptable range.

The analysis starts with the expected-value benchmark and then moves to the full distribution of possible patient arrivals. This makes it possible to compare utilization against operational risk and connect the statistical output to an actual scheduling policy.

## 📊 Key takeaways

Booking 40 patients produces an expected attendance of 30, but the average hides meaningful day-to-day variation. Under the assumptions used in the notebook, there is approximately a 43.95% probability that more than 30 patients will arrive when 40 appointments are booked.

More conservative booking levels of 34 to 35 appointments illustrate how risk tolerance can be incorporated into the scheduling decision. The exercise also shows why a production solution should go beyond a single historical no-show rate and account for factors such as appointment type, day of week, lead time, physician, seasonality, and patient history.

From a business perspective, the most useful booking policy is not necessarily the one that maximizes expected utilization. It is the one that balances unused capacity against the operational cost of overbooking and aligns that trade-off with the organization's service expectations.

## 🔎 Explore the notebook

The [notebook](https://github.com/saels/physician-schedule-optimization/blob/c6f473fa30aa777813cfaddb11469ce2cb64a456/Physician_schedule_optimization.ipynb) contains the full reasoning behind the approach, the probability calculations, the arrival distribution, and the translation from model output to a practical booking decision. Review the code and accompanying analysis for the assumptions, implementation details, and additional insights behind these conclusions.
