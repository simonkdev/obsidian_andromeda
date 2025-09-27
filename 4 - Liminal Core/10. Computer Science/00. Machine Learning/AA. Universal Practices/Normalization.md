2025-09-13 17:19

Tags: [[machine learning]]

------------------------------------------------

##### Overview:
If you work with multiple input variables on vastly different scales, it will cause your algorithm to converge very slowly. Having them within a similar range will make the conversion faster and more efficient.

##### Min-Max Normalization:
In min-max norm., in order to normalize a feature, the minimum value is assigned a 0 and the maximum value a 1. Every value in between is transformed into a decimal between 0 and 1.
The formula for one value is:
$$val_{new} = \frac{val_{old} - min}{max-min}$$

This has one significant weakness, which is outliers. In case the feature has 99 values between 0 and 30 but one at 100, the 99% will be between 0 and 0.3. This is where the z-score normalization comes into play:

##### Z-Score Normalization ("Standardization")
Here, we use the mean value (Mittelwert) and standard deviation (Standardabweichung / Wie stark verbreitet die Daten sind) to calculate the new values. If a value is equal to the mean value, it will be normalized to 0. If it is below, it will be negative, if it is above, it will be positive. The formula is:
$$value_{new} = \frac{value_{old} - \mu }{\sigma}$$
with $\mu$ representing the mean value and $\sigma$ representing the standard deviation.



------------------------------------------------------
### References
https://www.codecademy.com/article/min-max-zscore-normalization
