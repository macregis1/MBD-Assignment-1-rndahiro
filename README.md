Mobile Phone Activity Analysis
1. overview of the Approach

This project analyzes CDRs from the Milan metropolitan area to understand the urban dynamics and telecommunication usage patterns. the analysis focused on three specific days, the 2nd, 4th, and 6th November 2013, to capture a representative sample of weekly activity.

The workflow involved
* data integraton by merging multiple large-scale CSV files into a unified high-performance dataframe,
* temporal engineering by extracting hourly and period-based features to identify peak usage time,
* statical profiling by categorizing traffic into domestic and internal segments to compare behavioral differences.

2. Key decisions and Methodology

handling missing values

a significant portion of the datset contained null values, particularly in smsout and callin columns. I decided to fill the missing values with the mean of each respective column.

Since the grid squares represents diverse areas like commercial, residentail, and rural, a missing entry often signifies a period of no recorded activity. However, to maintain statistical consistency fr aggregate calculations without biasing the results towards zero, the mean imputation method was chosen per the requirement of the assignment, which is the rationalization.

The impact of this modification, affected approxiamtely 5880441 records, ensuring that subsequent statistical comparisons like domestic vs international ratios, were based on a complete dataset.

AGGREGATION LOGIC

TO provide a holistic view of network load, I created a total_activity metric. This metric combined SMS, voice calls, and data usage into a single volume indicator. this allowed for the identification of PEAK HOURS that reflect true network congestion rather than just a spike in one specific medium.

3. SUMMARY OF KEY FINDINGS

TEMPORAL TREND

* the peak usage show that the network experiences its highest loat at 17:00, suggesting a surge in communication during the transition from work to evening personal time.

* the lowest activity shows that the usage drops to a minimun at 4:00, reflecting the late-night/early-morning dormancy.

* day versus night, this shows that the day activity accounts for 78.51% of the total volume, confirming that the network is primarily utilized for business and daytime social interactions.

DOMESTIC VERSUS INTERNATIONAL DYNAMICS

* Call volume which shows that the internation calls dominate the network, accounting for 66.89% pf the total voice traffic

* international behavior shows a ratio of 1.6749 (incoming/outgoing). A ratio greater than 1 suggests that international users are more frequentyl being contacted from abroad than initiating calls themselves

* usage pattern: comparing hourly patterns shows that international calls often peak at different times than domestic calls, likely influenced by timezone differences of the originating/destination countries.

CORRELATION ANALYSIS

A correlation coefficient of 0.8856 was found between SMS and call volumes. this indicates a strong or moderate positive relationshiop, providing that grid squares with high messaging activity are almost always the same hubs for voice communication.

GITHUB LINK:
