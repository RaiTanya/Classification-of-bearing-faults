# Classification-of-bearing-faults
Classification of bearing faults through statistical features using CEEMDAN Technique
Contents
1. Introduction
2. Literature Survey
3. Signal Processing Techniques
Time Domain
Frequency Domain
Time-Frequency Domain
4. Introduction to Statistical Features in Vibration
    Analysis
5. Statistical Features and their Importance
6. Representation of Statistical Features
7. Results
8. Research Gaps
9. Project Objectives
10. Conclusions
11. References

INTRODUCTION

1.Bearings are critical machine elements that support loads and allow relative motion with minimal friction.
2.Various factors like improper design, defective installation, load fluctuations, excessive temperature, and improper lubrication can cause machinery failure.
3.Continuous condition monitoring (CM) helps in detecting developing faults and scheduling timely maintenance to prevent breakdowns.
4.CM techniques are essential for ensuring equipment reliability, safety, and reducing maintenance costs.
5.We aim to investigate the effect of simulated localized bearing faults on different bearing elements, focusing on identifying faults in the inner and outer races.
6.Vibration signals from a bearing test rig will be processed using Complete Ensemble Empirical Mode Decomposition with Adaptive Noise (CEEMDAN).

LITERATURE SURVEY

1. McFadden and Smith (1984) introduced envelope analysis, marking a foundational step in bearing fault detection. They focused on extracting fault-related frequencies from vibration signals, setting the stage for the development of techniques that could isolate and identify specific defects in bearings more efficiently.

2. Wu and Huang (2009) enhanced this early approach by introducing Empirical Mode Decomposition (EMD), which decomposed signals into Intrinsic Mode Functions (IMFs). This method allowed for adaptive analysis of non-stationary and non-linear signals, overcoming limitations of traditional methods like Fourier transforms in identifying complex faults.

3. Lei et al. (2009) proposed an EEMD-based method for fault detection in rotating machinery, further refining signal decomposition by adding white noise to counter mode mixing in EMD. This method enhanced the clarity of IMFs and made it possible to analyze more intricate fault characteristics.

4. Zhou et al. (2015) combined EEMD with SVM for bearing fault detection, optimizing the process through **Principal Component Analysis (PCA)** for dimensionality reduction. This method enabled more efficient fault classification, setting the stage for further improvements in both accuracy and speed.

5. Imaouchen et al. (2017) introduced CEEMD, which utilized adaptive white noise to improve the separation of IMFs. Their contribution was crucial in reducing noise interference and mode mixing, allowing for more accurate fault detection in mechanical systems.

6. Zhan et al. (2019) proposed ECEEMDAN, an enhanced version of CEEMDAN that adjusted noise amplitude and ensemble trials dynamically. Their method significantly improved the accuracy of fault detection by fine-tuning signal decomposition, helping eliminate residual noise issues and improving IMF selection.

7. Ma et al. (2019) further enhanced CEEMDAN by focusing on its ability to strengthen mode characteristics for improved fault identification. This method increased the precision of IMF extraction, particularly in noisy environments, which proved critical for diagnosing faults in roller bearings.

8. Yang et al. (2020) improved fault detection in noisy backgrounds by combining wavelet threshold denoising with CEEMD. This hybrid approach successfully filtered out noise before signal decomposition, allowing for cleaner IMFs and more reliable fault characteristic extraction.

9. Hou and Guo (2020) developed MCEEMD, an improvement on CEEMDAN that ordered IMFs by frequency and implemented a second noise-reduction phase using the Duffing system. This approach ensured more accurate identification of fault-related signals by enhancing the sensitivity of the decomposition process.

10. Li et al. (2020) concluded the progression by introducing CEEMDAN-based hybrid methods that combined adaptive noise techniques with SVM for fault classification. Their work demonstrated the superior accuracy of CEEMDAN in identifying both fault modes and severity, solidifying CEEMDAN as the most effective tool for bearing fault diagnosis in complex environments.

SIGNAL PROCESSING TECHNIQUES

1. Time Domain Techniques : Peak Amplitude, Peak to Peak, Root mean Square, Kurtosis, Crest Factor
2. Frequency Domain Techniques : Fast Fourier Transform, Hilbert Transform
3. Time-Frequency Domain: EMD, EEMD, CEEMDAN

The vibration signal of the bearing changes as the rolling elements engages with the local defects.  In the case of several faults on the raceway, the balls impact the defects at regular intervals, resulting in peaks.  A very short duration pulses are produced on the inter action of the defect with rolling elements of bearing. There is an increase in overall vibration energy due to the fact that these pulses excite the natural frequencies of bearing elements and housing structures

1. Time Domain Signal Processing

Time domain signal processing evaluates how a signal behaves over time, focusing on amplitude variations and patterns. It provides a straightforward way to observe overall trends, detect abnormalities, and calculate descriptive metrics to quantify the signal’s characteristics. This approach is particularly useful for early-stage fault detection when anomalies are subtle.
#Peak Amplitude: The highest value in the signal waveform, useful for detecting sudden events like impacts or high-energy vibrations caused by faults.
#Peak-to-Peak: The total difference between the maximum and minimum signal values, highlighting the extent of oscillations and the signal’s dynamic range.
#RMS (Root Mean Square): Measures the signal's effective power, giving an average energy representation, which is critical in assessing vibrational intensity over time.
#Kurtosis: Indicates how sharply signal values are concentrated around the mean. Higher kurtosis suggests impulsive events, common in bearing defects.
#Crest Factor: The ratio of peak amplitude to RMS, helpful in detecting rare, high-energy impacts that might otherwise be averaged out in the RMS metric.

2.Frequency Domain Analysis

Frequency domain analysis focuses on understanding how signal energy is distributed across frequencies. It helps identify periodic patterns and harmonics, which are often linked to rotating machinery faults such as unbalanced loads or misalignments. This method is essential for diagnosing recurring issues tied to specific mechanical frequencies.
#FFT (Fast Fourier Transform): Breaks the signal into its frequency components, generating a spectrum to pinpoint dominant frequencies associated with machinery faults like bearing resonance or gear meshing. It’s fast and widely used for initial diagnostics.
#Hilbert Transform: Extracts the analytic signal to analyze amplitude and phase variations. Envelope analysis, derived from the Hilbert transform, highlights modulations and transient behavior, such as early-stage bearing cracks or defects.

3.Time-Frequency Analysis

Time-frequency analysis combines the strengths of time and frequency domain techniques, making it suitable for non-stationary signals where frequency components vary over time. This approach is highly effective for detecting complex faults in bearings under changing operational conditions.
#EMD (Empirical Mode Decomposition): Breaks a signal into Intrinsic Mode Functions (IMFs), each representing oscillatory components with specific frequency ranges. This helps isolate fault-related signal patterns from background noise.
#EEMD (Ensemble Empirical Mode Decomposition): Adds white noise during decomposition to reduce mode mixing, ensuring clearer and more reliable IMFs. This improvement enhances fault feature extraction in complex systems.
#CEEMDAN (Complete Ensemble Empirical Mode Decomposition with Adaptive Noise): Improves EEMD by using adaptively tuned noise, leading to precise decomposition without excessive computational complexity. It’s especially useful for identifying transient vibrations and fault signatures.

EXPERIMENTATION AND METHODOLOGY

The experimental rig is an electromechanical system designed to examine the motor-end bearing under various fault conditions. Using electro-discharge machining, faults such as outer race, inner race, and ball faults with varying degrees of damage were introduced, with point flaws ranging from 0.007 to 0.021 inches in increments of 0.007 inches. Bearings were tested at four speeds (1772–1797 rpm) under loads ranging from 0 to 3 hp, adjusted in 1 hp increments. A sampling rate of 12 kHz was used to record data for healthy and faulty bearings, resulting in 40 experimental signals, including 4 healthy and 36 faulty states. Each signal, captured over 10 seconds, was divided into 30 sub-signals, yielding a total of 1,200 sub-signals for analysis.

The acquired signals were denoised using CEEMDAN, and significant intrinsic mode functions (IMFs) were selected based on their correlation with the original signal. Statistical features of these IMFs were computed and compared with those obtained using the standard EEMD method. Machine learning, specifically SVM, was employed to classify the bearing states based on these features. The experimental methodology involved six key steps: data acquisition, segmentation, decomposition and denoising, IMF selection using permutation entropy and correlation, computation of statistical features, and classification. This approach effectively distinguished healthy and faulty bearing conditions, validating the proposed methodology's efficacy.

INTRODUCTION TO STATISTICAL FEATURES IN VIBRATION ANALYSIS

In the field of vibration analysis, statistical features play a crucial role in extracting meaningful insights from raw vibration signals. Bearings, being critical components in rotating machinery, often exhibit changes in their vibration patterns when faults develop. These changes can be effectively quantified using statistical features, which provide a summary of signal characteristics without requiring complex transformations.
Before applying advanced signal decomposition techniques like CEEMDAN (Complete Ensemble Empirical Mode Decomposition with Adaptive Noise), it is essential to analyze statistical features. This preliminary study helps establish baseline behavior and detect abnormalities in vibration signals, laying the foundation for further analysis.
By computing statistical features on vibration data collected from faulty bearings, we can:
#Identify irregularities in vibration signals.
#Differentiate between normal and faulty bearing conditions.
#Select relevant features for machine learning models in predictive maintenance.

STATISTICAL FEATURES AND THEIR IMPORTANCE

The statistical features calculated in this study are listed below. Each of these features captures specific characteristics of the vibration signal, providing insights into the nature and severity of bearing faults.

1. Mean (Average Value)
Importance:
Represents the central tendency of the vibration signal.
A significant shift in mean values may indicate an imbalance or misalignment in the bearing.

2. Standard Deviation (Std)
​Importance:
Measures the spread of vibration values around the mean.
High standard deviation suggests increased variations, which may indicate bearing damage.

3. Variance
Importance:
Represents the degree of fluctuation in the vibration signal.
Higher variance indicates instability and possible bearing faults.

4. Median
Definition: The middle value when data is arranged in ascending order.
Importance:
Less sensitive to extreme values (outliers) than the mean.
If median and mean differ significantly, it may indicate skewed data due to faults.

5. Minimum & Maximum Values
Definition:
Minimum (Min): The smallest observed vibration value.
Maximum (Max): The largest observed vibration value.
Importance:
Captures the range of vibration fluctuations.
A large difference between max and min values indicates sudden impacts or shocks caused by bearing faults.

6. Skewness
Importance:
Measures asymmetry in the vibration data distribution.
Positive skewness: More extreme high values, indicating impulsive forces.
Negative skewness: More extreme low values, possibly due to wear.

7. Kurtosis
Importance:
Measures the sharpness of peaks in the vibration data.
High kurtosis (>3): Indicates sharp, sudden impulses caused by bearing faults.
Low kurtosis (<3): Suggests a flatter distribution with fewer sharp peaks.

This statistical analysis provides a foundation for identifying fault patterns in bearing vibration signals. Once these statistical features are computed, we will proceed with CEEMDAN decomposition, followed by further feature extraction and classification.

REPRESENTATION OF STATISTICAL FEATURES

1. Time Series Plot of Raw vs Processed Data (Before & After CEEMDAN)

Why?

Visualizes the direct effect of CEEMDAN on the vibration signal.
Shows how the denoised signal extracts important fault characteristics.
Great for comparison: raw signal may look chaotic, while the processed signal reveals distinct patterns.

CODE:

clc; clear;

% Load the vibration dataset
T = readtable("F007_1750.xlsx");
numericalValues = table2array(T);

% Select one column (vibration data from one sensor)
signal = numericalValues(:, 1);
t = 1:length(signal); % Time axis

% Plot the raw vibration signal
figure;
plot(t, signal, 'b');
title('Raw Vibration Signal');
xlabel('Time');
ylabel('Amplitude');
grid on;

2. Histogram of Statistical Features (Variance, Kurtosis, Skewness)

Why?

Histograms show the distribution of key statistical features, making it easier to spot differences between normal and faulty conditions.
Helps demonstrate which features are most effective in fault detection.

CODE:

% Compute statistical features
varValues = var(numericalValues);
skewnessValues = skewness(numericalValues);
kurtosisValues = kurtosis(numericalValues);

% Plot histograms
figure;
subplot(3,1,1);
histogram(varValues, 20, 'FaceColor', 'r');
title('Variance Distribution');
xlabel('Variance'); ylabel('Frequency');
grid on;

subplot(3,1,2);
histogram(skewnessValues, 20, 'FaceColor', 'g');
title('Skewness Distribution');
xlabel('Skewness'); ylabel('Frequency');
grid on;

subplot(3,1,3);
histogram(kurtosisValues, 20, 'FaceColor', 'b');
title('Kurtosis Distribution');
xlabel('Kurtosis'); ylabel('Frequency');
grid on;

RESULTS

1.Time Series Plot (Raw Vibration Signal)

What This Plot Shows:
The x-axis represents time, and the y-axis represents the amplitude of vibration signals.
The raw signal captures real-time vibration data from a faulty bearing.
The fluctuations in amplitude indicate changes in the vibration intensity, but the noise may obscure meaningful patterns.


What will change after CEEMDAN?
The signal will become cleaner, making fault patterns more visible.
CEEMDAN will decompose the raw signal into different frequency components, helping separate normal vibrations from faulty ones.

2.Histogram of Statistical Features

What These Plots Show:
Each histogram represents the distribution of a statistical feature across the dataset:

#Variance Distribution (Red Histogram)

Variance measures how much the vibration values deviate from the mean.
Higher variance → More irregular vibrations → Likely fault presence.
If the histogram is spread out, it indicates unstable bearing behavior.

#Skewness Distribution (Green Histogram)

Skewness tells if the signal is symmetrically distributed or not.
If skewness is ≠ 0, the vibration signal is not evenly distributed, indicating a possible imbalance or localized damage.
High positive skewness → Sudden impact faults (e.g., cracks).

#Kurtosis Distribution (Blue Histogram)

Kurtosis measures how sharp the peaks in the vibration signal are.
Higher kurtosis → More frequent sharp spikes → Sudden shocks in the bearing.
Bearings in good condition have a lower kurtosis, while faulty ones show high peaks due to impacts.

RESEARCH GAPS

1.MODE MIXING IN DECOMPOSITION TECHNIQUES : EMD suffers from mode mixing, affecting the accuracy of bearing fault detection. Although CEEMDAN improves this, further refinement is needed.

2.NOISE INTERFERENCE : Residual noise after decomposition still hampers the effectiveness of EEMD. While CEEMDAN addresses this, the separation of noise from signal remains a challenge.

3.LIMITED REAL-TIME DIAGNOSTICS : Existing studies focus more on offline fault diagnosis, with limited attention on real-time monitoring under varying conditions.

4.FEATURE EXTRACTION LIMITATIONS : Current methods for selecting statistical features (e.g., RMS, kurtosis) need to be more automated and efficient to improve fault classification accuracy.

PROJECT OBJECTIVES

The literature review and the gaps found in the existing literature helped in determining the objectives of the present work, which are as follows:

OBJECTIVE 1. Processing of the acquired vibration signals (data from Western Reserve University) through Complete Ensemble Empirical Mode Decomposition with Adaptive Noise (CEEMDAN).

OBJECTIVE 2. To extract the fault related information using statistical features.

CONCLUSIONS

This project emphasizes the critical importance of effective fault detection in ball bearings using the CEEMDAN technique. By accurately decomposing vibration signals into intrinsic mode functions, we can identify fault patterns and enhance the reliability of rotating machinery.

We analyzed statistical features like mean, variance, skewness, and kurtosis to study vibration data from faulty bearings. High variance and kurtosis values revealed fluctuations and impulsive shocks, indicating potential bearing faults.

Traditional statistical features struggle with noise and mode mixing in vibration signals. To overcome this, we will apply CEEMDAN to decompose the signal into intrinsic mode functions (IMFs), enabling more accurate and noise-resilient fault detection.

This study lays the groundwork for further machine learning-based classification of healthy vs. faulty bearings, helping develop a robust predictive maintenance framework for rotating machinery.

Next Steps :

Apply CEEMDAN to remove noise and extract meaningful IMFs.
Recalculate statistical features on CEEMDAN-processed data for improved fault detection.
Compare results before and after CEEMDAN to evaluate its effectiveness.

REFERENCES

Snehsheel Sharma, S.K. Tiwari, Sukhjeet Singh. "Integrated approach based on flexible analytical wavelet transform and permutation entropy for fault detection in rotary machines" , Measurement, 2021
 
Lei, Yaguo, Jing Lin, Zhengjia He, and Ming J. Zuo. "A review on empirical mode decomposition in fault diagnosis of rotating machinery" , Mechanical Systems and Signal Processing, 2013.

MCFADDEN, P.D.. "DETECTION OF GEAR FAULTS BY DECOMPOSITION OF MATCHED DIFFERENCES OF VIBRATION SIGNALS" , Mechanical Systems and Signal Processing, 200009

Amarnath, M., and I.R. Praveen Krishna. "Local fault detection in helical gears via vibration and acoustic signals using EMD based statistical parameter analysis" , Measurement, 2014.

Y Lei. "The use of ensemble empirical mode decomposition to improve bispectral analysis for fault detection in rotating machinery" , Proceedings of the Institution of Mechanical Engineers Part C Journal of Mechanical Engineering Science, 01/01/2010

Xiaoyuan Zhang, Jianzhong Zhou. "Multi-fault diagnosis for rolling element bearings based on ensemble empirical mode decomposition and optimized support vector machines" , Mechanical Systems and Signal Processing, 2013
