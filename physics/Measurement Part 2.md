 - When using an instrument to measure any physical quantities, measurement uncertainty is inevitable due to
	- Measuring instrument itself (instrumental uncertainty)
	- Limitations of the observer/ method used (procedural uncertainty)
- Uncertainty is inherent in all measurements, causing the measurement value to deviate from the 'true' or correct value
- Measurement error is the difference between a measure value and the true value of a quantity
## Actual uncertainty
- To express the uncertainty of an instrument, readings are expressed in the form of $(R \pm \Delta R)$, where $\Delta R$ is the actual uncertainty
- $\Delta R$  is to one significant figure only
- $R$ is rounded off to the same decimal place as $\Delta R$
- For a scale reading (only 1 reading is taken), the uncertainty is half the smallest division on the scale
- For a length reading (difference of two readings), the uncertainty is one division
## Fractional and Percentage uncertainty)
- The fractional uncertainty is $\frac{\Delta R}{R}$
- The percentage uncertainty is $\frac{\Delta R}{R} \times 100\%$
- $\Delta R$ is the uncertainty of measured value $R$
- It is an indication of the reliability of a instrument to measure a given quantity; the smaller the fractional/ percentage uncertainty, the more accurate the instrument
## Precision and accuracy (instruments)
- Precision of an instrument refers to the smallest value and instrument can measure, known as the limit of sensitivity of a measuring instrument
	- E.g. a meter rule can measure up to 0.1cm while a micrometre screw gauge can measure up to 0.001cm, hence the micrometre is a more precise instrument compared to a meter rule
	- Precision of an instrument is reflected by its actual uncertainty; the smaller the actual uncertainty, the more precise it is
- Accuracy of an instrument refers to the capability of the instrument to reliably measure the true value of a physical quantity
	- Thus it depends on both the precision of the instrument and the magnitude of the quantity measured as well
	- E.g. using a meter rule of precision 0.1cm to measure a length of 1cm will have a percentage uncertainty of 10%, but using the same meter rule to measure 100cm will result in a percentage uncertainty of only 0.1%
	- Hence the meter rule is more accurate for measuring 0.1cm
	- Accuracy of an instrument is reflect by its percentage/ fractional uncertainty; the smaller the fractional/ percentage uncertainty, the more accurate the instrument
## Systematic errors
- ==Systematic errors are errors of measurements that occur to **some fixed rule or pattern** such that they yield a **consistent over-estimation or under-estimation** of the true value==
- The error is systematic if
	- Repeated measurements taken under the same conditions yield the same error in magnitude or sign
	- Its value changes in a predictable manner depending on the conditions
- Examples
	- **Zero error** - Using a micrometre with a zero reading of -0.02mm will result in all readings being -0.02mm too small
	- **Faulty instrument** - Using a stopwatch that runs too fast will result in all time readings being too big
	- **Wrong assumptions** - Assuming the wrong value of g
	- **Wrong experimental technique** - Poor skills in reading measurements resulting in an error that affects all readings in the same way
- Systematic error can be reduced by recalibrating instruments or changing experimental techniques
## Random errors
- ==Random errors are **unpredictable** errors with **different magnitude and sign in repeated measurements**==
- There is an equal chance of the error being positive or negative
- Examples
	- Variation in the condition of measuring instruments
	- Variation arising from the inability of an observer to measure small intervals
	- Variation due to fluctuating external conditions (air pressure, temperature)
	- Irregularity of a quantity to be measured (small fluctuations in the diameter of a wire)
- As positive and negative errors are equally likely, the errors will tend to offset each other statistically
- We can reduce random errors by taking a number of repeated readings and finding the average
## Precision and accuracy of data readings
- ==Precision refers to the closeness of measure values to each other, regardless of the actual value==
	- Related to random error
	- Repeating the measurements can reduce the uncertainty in the average value obtained, because of the statistics of averaging
- ==Accuracy refers to the closeness of measure values to its true value==
	- Related to systematic error
	- Only can be reduced by recalibrating the instruments; repeating does not reduce it
## Uncertainties of derived quantities
### Addition and subtraction
- The consequential uncertainty is the sum of the absolute uncertainties$$\Delta R  = \Delta R_1 + \Delta R_2 +...$$
### Multiplication and division
- The consequential fractional uncertainty is the sum of the individual fractional uncertainties
$$\frac{\Delta R}{R} = \frac{\Delta R_1}{R_1} + \frac{\Delta R_2}{R_2} + ...$$
> [!NOTE]
> - When dividing by a whole number, e.g. $P =\frac{Q}{N}$, where N is the whole number,
> 	- $\frac{\Delta P}{P} = \frac{\Delta Q}{Q} + \frac{\Delta N}{N}$
> 	- N is a number, so $\Delta N = 0$ 
> 	- $\frac{\Delta P}{P} = \frac{\Delta Q}{Q}$
> 	- ${\Delta P} = {P}\frac{\Delta Q}{Q}$
> 	- Since $P =\frac{Q}{N}$,   ${\Delta P} = \frac{Q}{N}\frac{\Delta Q}{Q}$
> 	-  ${\Delta P} =\frac{\Delta Q}{N}$
>- When multiplying by a whole number, e.g. $P = QN$, where N is the whole number 
>	- $\frac{\Delta P}{P} = \frac{\Delta Q}{Q} + \frac{\Delta N}{N}$
>	- N is a number, so $\Delta N = 0$ 
>	- $\frac{\Delta P}{P} = \frac{\Delta Q}{Q}$
>	- ${\Delta P} = {P}\frac{\Delta Q}{Q}$
>	- Since $P = QN$, ${\Delta P} = {QN}\frac{\Delta Q}{Q}$
>	- ${\Delta P} = N \Delta Q$
- Useful shortcuts
	- If $R=y^n$ then $\frac{\Delta R}{R} = n\frac{\Delta y}{y}$
	- If $R = p^m \times q^n$, then $\frac{\Delta R}{R} = m\frac{\Delta p}{p}+ n\frac{\Delta q}{q}$
	- If $R = \frac{p^m}{q^n}$, then $\frac{\Delta R}{R} = m\frac{\Delta p}{p}+ n\frac{\Delta q}{q}$
### Numerical substitution
- When the calculation is a mixture of both summation and multiplication of measurements, or involves non linear functions such as sin, cos, ln, we will just use numerical substitutions$Uncertainty = \frac{Maximum\ value\ of\ derived\ quanitity - Minimum\ value\ of derived quantity}{2}$
