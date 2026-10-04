# Ultrasound Signal and Image Processing: Curriculum Master Plan

## 1. Purpose

A curriculum that takes a learner from engineering fundamentals to the level
expected of a PhD researcher or an industry engineer in medical ultrasound. It
covers the full chain: mathematics, physics and mechanics, signal processing,
transducers, RF and digital hardware, system operation, beamforming, image
formation, image processing, flow and tissue estimation, product and regulatory
practice, professional skills, and interview preparation.

Target roles: algorithm or signal processing engineer, systems or image quality
engineer, imaging machine-learning scientist, transducer engineer, hardware
engineer, and research scientist.

## 2. Audience and prerequisites

- An undergraduate degree, or equivalent, in electrical engineering, physics,
  biomedical engineering, mechanical engineering or computer science.
- Calculus, basic linear algebra, basic probability and a first programming
  course. Everything else is taught, starting from the fundamentals.

## 3. Structure

The curriculum has 100 modules in 13 parts, grouped into five courses. Each
course can be taken on its own once its prerequisites are met.

| Course | Parts | Modules | Prerequisite |
| --- | --- | --- | --- |
| A. Foundations | 1–3 | 1–29 | None |
| B. Hardware and systems | 4–6 | 30–50 | A |
| C. Image formation | 7–8 | 51–63 | A, modules 31–34 |
| D. Image processing and estimation | 9–10 | 64–76 | A, C |
| E. Product and professional practice | 11–13 | 77–100 | B, C, D |

Modules 82 and 84 (programming and software engineering practice) are taken
first, before Course A, because every coding exercise depends on them. Module
83 (C++) is taken just before module 77, the first module that needs it. A
few other modules depend on a module with a higher number. Section 14 gives
the order that resolves these dependencies.

Planning estimate: 6 to 10 hours per module, so 600 to 1000 hours in total.
This is a starting figure to calibrate against the first modules written, not a
measured duration.

## 4. Module format

Every technical module has the same six elements.

1. **Concept:** the idea in plain terms, with the physical or engineering
   intuition.
2. **Derivation:** the mathematics from first principles, with assumptions and
   range of validity stated.
3. **Implementation:** how it is built in software or hardware, and the
   constraints a product imposes (compute, memory, noise, cost, regulation).
4. **Coding exercise:** a tested implementation that later modules reuse.
5. **Reading:** a textbook section and one or two primary papers.
6. **Interview questions:** five to ten questions with model answers, which
   accumulate into the question bank used in Part 13.

## 5. Course A: Foundations

### Part 1: Mathematics

1. **Vector and tensor calculus:** multivariable calculus, gradient, divergence
   and curl, integral theorems, curvilinear coordinates, index notation.
2. **Complex analysis and transforms:** contour integration, Fourier, Laplace,
   z, Hilbert and Hankel transforms, causality and Kramers–Kronig relations.
3. **Linear algebra:** vector spaces, eigen-decomposition, SVD, pseudo-inverse,
   conditioning, matrix calculus.
4. **Differential equations:** second-order systems, wave, Helmholtz and
   diffusion equations, Green's functions, boundary conditions, Bessel
   functions.
5. **Probability and stochastic processes:** Rayleigh, Rician, Nakagami and K
   distributions, stationarity, power spectral density.
6. **Estimation and detection:** maximum likelihood, Bayesian estimation,
   Cramér–Rao bounds, hypothesis testing, ROC analysis.
7. **Optimisation and inverse problems:** least squares, regularisation, convex
   and gradient methods, ill-posedness.
8. **Numerical methods:** finite difference, finite element and pseudospectral
   schemes, stability and numerical dispersion, interpolation, floating- and
   fixed-point arithmetic.

### Part 2: Physics and mechanics

9. **Vibration:** single- and multi-degree-of-freedom systems, resonance,
   damping, quality factor, modes.
10. **Continuum mechanics:** stress, strain, constitutive laws, elastic moduli.
11. **Elastic waves in solids:** longitudinal, shear, surface and guided waves,
    anisotropy.
12. **Fluid acoustics:** conservation laws, linearisation, wave equation,
    impedance, intensity and energy.
13. **Propagation:** reflection, refraction, diffraction, scattering theory
    (Born approximation, Rayleigh scattering), absorption mechanisms, power-law
    attenuation and dispersion, sound-speed variation and aberration.
14. **Nonlinear acoustics:** harmonic generation, Westervelt, KZK and Burgers
    equations, radiation force, cavitation.
15. **Tissue mechanics:** viscoelastic models (Kelvin–Voigt, Maxwell), shear
    modulus, poroelasticity.
16. **Haemodynamics:** steady and pulsatile flow, velocity profiles,
    turbulence, blood rheology.
17. **Thermal physics and bioeffects:** bioheat equation, tissue heating,
    thermal and mechanical mechanisms of bioeffects.
18. **Piezoelectricity:** constitutive equations, coupling coefficients,
    dielectric and ferroelectric behaviour.

### Part 3: Signal processing

19. **Signals and systems:** linear time-invariant systems, convolution,
    transfer functions, stability.
20. **Sampling and quantisation:** Nyquist and bandpass sampling, quantisation
    noise, jitter, oversampling.
21. **Filter design:** FIR and IIR methods, linear phase, matched and Wiener
    filters.
22. **Multirate processing:** decimation, polyphase and CIC filters,
    fractional-delay interpolation.
23. **Spectral analysis:** periodogram and Welch methods, autoregressive
    models, time-frequency analysis, wavelets.
24. **Analytic signals and modulation:** Hilbert transform, IQ demodulation,
    mixing, baseband processing.
25. **Statistical and adaptive filtering:** LMS and RLS, Kalman filtering,
    subspace and SVD methods.
26. **Array signal processing:** spatial sampling, array factor and beam
    pattern, delay-and-sum as a spatial filter, MVDR, MUSIC, spatial coherence
    and the van Cittert–Zernike theorem.
27. **Time-delay estimation:** cross-correlation, phase-based methods,
    sub-sample interpolation, performance bounds.
28. **Multidimensional processing:** 2D and 3D sampling, filtering and
    interpolation, point spread and modulation transfer functions, k-space
    description of imaging systems.
29. **Sparse methods:** compressed sensing and sparse recovery.

**Course A project:** a 2D finite-difference acoustic wave simulator verified
against an analytic solution, plus a small signal processing library (filters,
IQ demodulation, fractional delay, delay estimation) with unit tests.

## 6. Course B: Hardware and systems

### Part 4: Transducers, fields and arrays

30. **Transducer engineering:** piezoelectric materials, composites, CMUT and
    PMUT, KLM and Mason models, matching, backing and lens design, bandwidth
    and impulse response, finite-element modelling, fabrication.
31. **Radiated fields:** Rayleigh–Sommerfeld integral, spatial impulse
    response, near and far field, focusing, depth of field, directivity.
32. **Arrays:** linear, convex, phased, matrix, sparse and row-column arrays;
    pitch, grating lobes, steering, apodisation, element directivity, elevation
    focus.
33. **Pulse-echo signal model:** point spread function, axial, lateral and
    elevational resolution, speckle as a random-phasor sum and its first- and
    second-order statistics, signal-to-noise ratio, contrast.
34. **Simulation:** spatial impulse response tools (Field II), frequency-domain
    tools (SIMUS), full-wave tools (k-Wave), angular spectrum methods,
    numerical phantoms.

### Part 5: RF, analog and digital hardware

35. **Analog circuits:** amplifiers, feedback and stability, active filters.
36. **RF fundamentals:** transmission lines, reflections, impedance matching,
    Smith chart, S-parameters, cable effects.
37. **Noise and dynamic range:** thermal noise, noise figure, cascaded noise,
    linearity, SNR budgets.
38. **Transmit electronics:** high-voltage pulsers, multi-level and linear
    transmitters, transmit/receive switches, multiplexers, transmit timing.
39. **Receive front end:** low-noise amplifiers, variable gain and time gain
    compensation, anti-alias filtering, continuous-wave Doppler path,
    integrated front-end chips.
40. **Data conversion and clocking:** ADC architectures, effective number of
    bits, clock jitter and distribution, high-speed serial interfaces.
41. **Digital hardware:** FPGA architecture, HDL design, pipelining,
    fixed-point DSP, memory, GPUs and system-on-chip platforms.
42. **Power, thermal and mechanical design:** supplies and high-voltage rails,
    heat dissipation, probe surface temperature, enclosure and cable design.
43. **Signal integrity and EMC:** PCB layout, grounding, crosstalk, shielding,
    electromagnetic compatibility.
44. **Test and measurement:** oscilloscope, network and impedance analysers,
    hydrophone field scans, radiation force balance, phantoms.

### Part 6: System operation and systems engineering

45. **System architecture:** end-to-end block diagram, cart, portable and
    handheld designs, channel count, analog versus digital and software
    beamforming.
46. **Scan sequencing and timing:** pulse repetition frequency, depth and
    frame-rate limits, line density, interleaving of modes.
47. **Operating modes and controls:** B, M, colour, pulsed and continuous-wave
    Doppler, harmonic, contrast and elastography modes; gain, time gain
    compensation, focus, dynamic range and presets.
48. **System budgets:** penetration and SNR from transmit voltage to display,
    dynamic range, data rate, compute and power.
49. **Systems engineering practice:** requirements, trade studies, failure mode
    analysis, verification planning.
50. **Reliability and production:** calibration, manufacturing test, service
    and field failures.

**Course B project:** a paper design of a scanner front end. Model a transducer
with a KLM equivalent circuit, simulate the field of a linear array, and produce
a penetration, noise and data-rate budget for a stated specification.

## 7. Course C: Image formation

### Part 7: Beamforming

51. **RF and IQ processing chain:** bandpass filtering, demodulation,
    decimation, digital time gain compensation.
52. **Transmit design and coded excitation:** pulse shaping, chirps, Golay
    codes, pulse compression, matched and mismatched filtering, range
    sidelobes.
53. **Conventional beamforming:** delay-and-sum, transmit and dynamic receive
    focusing, apodisation, f-number, multi-line acquisition.
54. **Synthetic aperture and ultrafast imaging:** synthetic transmit aperture,
    plane and diverging waves, coherent compounding, virtual sources.
55. **Fourier-domain beamforming:** f-k (Stolt) migration and wavenumber
    algorithms.
56. **Adaptive and coherence-based beamforming:** minimum variance with
    covariance estimation and diagonal loading, coherence factor,
    delay-multiply-and-sum, short-lag spatial coherence.
57. **Aberration and sound-speed correction:** phase-screen models,
    sound-speed estimation, distortion-matrix methods.
58. **Model-based and learned reconstruction:** inverse-problem formulations,
    compressed sensing, differentiable and deep-learning beamformers.
59. **3D and 4D imaging:** matrix arrays, micro-beamforming, row-column
    addressing.

### Part 8: Image formation and display

60. **Detection and compression:** envelope detection, log compression,
    dynamic range, grey maps, M-mode.
61. **Scan conversion:** polar-to-Cartesian mapping, interpolation kernels, 3D
    resampling.
62. **Compounding and persistence:** spatial, frequency and temporal
    compounding.
63. **Image quality and artefacts:** resolution, contrast, CNR, gCNR, speckle
    SNR, penetration, phantoms; reverberation, shadowing, enhancement, mirror
    and side-lobe artefacts.

**Course C project:** a beamforming library that turns channel data into B-mode
images using delay-and-sum, plane-wave compounding, f-k migration and minimum
variance, evaluated with resolution and contrast metrics on simulated data and
on an open channel-data benchmark.

## 8. Course D: Image processing and estimation

### Part 9: Image processing and analysis

64. **Speckle reduction and denoising:** multiplicative noise models, Lee,
    Frost and Kuan filters, speckle-reducing anisotropic diffusion, wavelets,
    non-local means, deep denoisers.
65. **Enhancement and restoration:** contrast and edge enhancement,
    deconvolution, super-resolution, artefact suppression.
66. **Segmentation:** thresholding, active contours, level sets, graph cuts,
    shape models, U-Net variants, transformers, foundation models; Dice and
    Hausdorff metrics, observer variability.
67. **Registration and fusion:** rigid and deformable registration,
    ultrasound-specific similarity measures, fusion with MRI and CT.
68. **Motion estimation in images:** block matching, optical flow,
    speckle-tracking echocardiography, strain.
69. **3D reconstruction and visualisation:** freehand 3D, probe calibration,
    sensorless reconstruction, volume rendering, panoramic imaging.
70. **Detection, classification and measurement:** computer-aided diagnosis,
    biometry, landmark and standard-plane detection, texture analysis and
    radiomics, automated quality assessment.
71. **Deep learning for ultrasound images:** limited and noisy labels,
    augmentation, self-supervised learning, domain shift across scanners, video
    models, uncertainty, evaluation pitfalls such as patient-level leakage.

### Part 10: Flow, motion and tissue characterisation

72. **Doppler and flow:** continuous and pulsed wave, spectral, colour and
    power Doppler, autocorrelation estimators with bias and variance, clutter
    filtering including SVD, vector flow, ultrafast Doppler.
73. **Elastography:** strain imaging, acoustic radiation force, shear wave
    methods, viscoelastic inversion.
74. **Harmonic and contrast imaging:** tissue harmonics, pulse inversion,
    amplitude modulation, perfusion quantification, ultrasound localisation
    microscopy.
75. **Quantitative ultrasound:** attenuation, backscatter coefficient, envelope
    statistics, speed-of-sound imaging.
76. **Emerging modalities:** functional ultrasound, photoacoustics, ultrasound
    tomography and full-waveform inversion, transcranial imaging.

**Course D projects:** an image analysis project on an openly licensed dataset
(for example muscle architecture or fetal head circumference) with a
cross-dataset test, and a colour Doppler or shear wave estimator validated on
simulated data with known ground truth.

## 9. Course E: Product and professional practice

### Part 11: Product, regulation and software

77. **Real-time implementation:** FPGA and GPU pipelines, fixed-point
    arithmetic, delay interpolation, latency, memory and power budgets.
78. **Commercial image chain and tuning:** presets, gain and dynamic-range
    mapping, shipped speckle reduction and edge enhancement, tuning trade-offs,
    handheld constraints.
79. **Safety, standards and regulation:** acoustic output measurement, MI, TI
    and intensity measures, ALARA, IEC 60601-2-37, IEC 62359, IEC 61391, FDA
    guidance for diagnostic ultrasound.
80. **Medical software and data formats:** IEC 62304 software lifecycle, ISO
    14971 risk management, ISO 13485 quality systems, DICOM and channel-data
    formats, verification and validation.
81. **Deploying machine learning:** generalisation across probes and scanners,
    dataset shift, clinical validation design, regulatory expectations for
    AI-enabled devices, on-device inference.

### Part 12: Professional skills

82. **Prototyping languages:** MATLAB and Python (NumPy, SciPy, PyTorch);
    vectorised, tested, reproducible research code.
83. **Production languages:** modern C++ for real-time processing, memory and
    threading, profiling, CUDA.
84. **Software engineering practice:** version control, code review, unit and
    regression testing, continuous integration, documentation, requirements
    traceability.
85. **Hands-on acquisition:** programming a research scanner, acquiring channel
    data, working with phantoms, measuring image quality on hardware.
86. **Image quality optimisation:** tuning transmit and receive parameters per
    probe and application; trading penetration, resolution and frame rate;
    working with clinical feedback.
87. **Clinical context:** anatomy and standard views for cardiac, abdominal,
    obstetric, vascular, musculoskeletal and point-of-care imaging; what
    clinicians look for in an image.
88. **Technical communication:** design specifications, verification reports,
    papers, patents, presentations to mixed audiences.

### Part 13: Career and interview preparation

89. **Roles and career paths:** what each target role does and which parts of
    the curriculum it draws on.
90. **Portfolio:** selecting, documenting and presenting the course projects as
    public repositories.
91. **The interview process:** recruiter screen, technical screen, take-home or
    live coding, on-site loop.
92. **Reference numbers:** sound speed in tissue (about 1540 m/s), attenuation
    (roughly 0.5 dB/cm/MHz), wavelengths at common frequencies, ADC dynamic
    range (about 6 dB per bit), maximum pulse repetition frequency for a depth
    (c/2d).
93. **Fundamentals question bank:** the questions accumulated from every
    module, organised by topic and by role.
94. **Whiteboard derivations:** axial and lateral resolution, grating-lobe
    condition, receive focusing delays, Doppler equation and aliasing limit,
    cascaded noise figure, speckle statistics.
95. **Coding rounds:** delay-and-sum, envelope detection, fractional-delay
    interpolation, autocorrelation velocity estimation and clutter filtering,
    in Python or MATLAB and in C++.
96. **System design interviews:** budgeting an imaging chain from a
    specification, covering channel count, sampling rate, data rate, compute,
    frame rate and penetration.
97. **Project deep dive and research talk:** a 20 to 45 minute presentation of
    one project, including its limitations.
98. **Take-home assignments:** practice tasks on channel or image data,
    assessed on code quality, validation and a short report.
99. **Behavioural interviews:** structured answers on conflict, failure,
    ambiguity and cross-functional work.
100. **Mock interviews and closing:** timed mock sessions with feedback,
     questions to ask the team, comparing and negotiating offers.

**Course E capstone:** a real-time B-mode and colour Doppler chain on open or
simulated channel data, GPU-accelerated, with a design specification, automated
tests and a verification report of measured image quality.

## 10. Electives

- **Therapeutic ultrasound:** high-intensity focused ultrasound, histotripsy,
  neuromodulation, treatment planning and monitoring.
- **Non-destructive testing:** phased-array inspection, total focusing method,
  guided waves.

## 11. Assessment

| Type | What it tests | Used in |
| --- | --- | --- |
| Problem sets | Derivations and analysis | Courses A–D |
| Coding labs with tests | Correct, reusable implementations | All technical modules |
| Paper reproduction | Reading and reproducing a published figure, then extending it | Courses C–D |
| Design review | A written design and budget defended in front of reviewers | Courses B and E |
| Mock interviews | Fluency under time pressure | Part 13 |

## 12. Open tools and data

- **Simulation:** k-Wave and k-wave-python, Field II (free to use, not open
  source), MUST and PyMUST.
- **Beamforming and processing:** USTB, vbeam, zea, FAST.
- **Image analysis:** MONAI, ITK, 3D Slicer.
- **Channel-data benchmarks:** PICMUS, CUBDL.
- **Image datasets:** HC18 (fetal head), BUS-BRA (breast), DL_Track_US and
  FALLMUD (muscle architecture).

Check the licence or terms of each dataset at its source before redistributing
any files; link to the data and provide a download script rather than
committing it.

## 13. Core references

**Ultrasound**

- Szabo, *Diagnostic Ultrasound Imaging: Inside Out*
- Cobbold, *Foundations of Biomedical Ultrasound*
- Hill, Bamber and ter Haar, *Physical Principles of Medical Ultrasonics*
- Jensen, *Estimation of Blood Velocities Using Ultrasound*
- Kino, *Acoustic Waves: Devices, Imaging, and Analog Signal Processing*

**Physics and mechanics**

- Kinsler, Frey, Coppens and Sanders, *Fundamentals of Acoustics*
- Hamilton and Blackstock, *Nonlinear Acoustics*
- Fung, *Biomechanics: Mechanical Properties of Living Tissues*

**Signal and image processing**

- Oppenheim and Schafer, *Discrete-Time Signal Processing*
- Kay, *Fundamentals of Statistical Signal Processing* (estimation and
  detection volumes)
- Van Trees, *Optimum Array Processing*
- Goodman, *Speckle Phenomena in Optics*
- Prince and Links, *Medical Imaging Signals and Systems*
- Gonzalez and Woods, *Digital Image Processing*
- Kak and Slaney, *Principles of Computerized Tomographic Imaging*

**Mathematics and electronics**

- Boyd and Vandenberghe, *Convex Optimization*
- Pozar, *Microwave Engineering*
- Horowitz and Hill, *The Art of Electronics*

**Primary papers to anchor modules**

- Kasai et al. (1985): autocorrelation colour flow estimator.
- Jensen and Svendsen (1992): field simulation with spatial impulse responses.
- Walker and Trahey (1995): lower bound on time-delay estimation error.
- Yu and Acton (2002): speckle-reducing anisotropic diffusion.
- Synnevåg, Austeng and Holm (2007): minimum variance beamforming in medical
  ultrasound.
- Montaldo et al. (2009): coherent plane-wave compounding.
- Treeby and Cox (2010): the k-Wave toolbox.
- Lediju et al. (2011): short-lag spatial coherence imaging.
- Garcia et al. (2013): Stolt f-k migration for plane-wave imaging.
- Tanter and Fink (2014): ultrafast imaging in biomedical ultrasound.
- Demené et al. (2015): spatiotemporal SVD clutter filtering.
- Errico et al. (2015): ultrafast ultrasound localisation microscopy.
- Liebgott et al. (2016): the PICMUS plane-wave imaging challenge.
- Rodriguez-Molares et al. (2020): the generalised contrast-to-noise ratio.
- Hyun et al. (2021): the CUBDL deep-learning beamforming challenge.

## 14. Build and study order

The modules are written, studied and published in one order, which starts
with the fundamentals. No module comes before a module it depends on. Module
numbers do not change. Within a stage the modules are taken in the order
listed.

| Stage | Modules, in order | Contents |
| --- | --- | --- |
| 1 | 82, 84 | Tools: languages, testing, version control |
| 2 | 1, 2, 3, 4, 8 | Mathematics for waves and numerical methods |
| 3 | 9–18 | Physics and mechanics |
| 4 | 5, 6, 7, 19–29, 88 | Probability, estimation and optimisation; signal processing; technical communication |
| 5 | 31, 32, 33, 34, 87 | Fields, arrays, pulse-echo model and simulation; clinical context |
| 6 | 51, 60, 53, 61, 63, 52, 54, 55, 56, 57, 59, 62 | Image formation |
| 7 | 64–71, 58, 72–76 | Image processing; flow, motion and tissue characterisation |
| 8 | 35, 36, 30, 37–50 | Hardware and systems |
| 9 | 83, 77–81, 85, 86 | Product, regulation and software; acquisition and tuning |
| 10 | 89–100 | Career and interview preparation |

The order departs from the numbering where a dependency or the first use of
a module requires it:

- **82 and 84 first.** Every coding exercise from module 1 onwards needs a
  working setup, tests and version control. Module 83 (C++) waits until just
  before module 77, the first module that uses it.
- **5, 6 and 7 after the physics.** Probability, estimation and optimisation
  are first used by the signal processing modules; the physics modules do not
  use them.
- **88 before the first project report.** It teaches how to write the
  verification report that the Course A project ends with.
- **30 after 36.** The equivalent-circuit models and the matching of a
  transducer rest on the transmission-line theory of module 36, and image
  formation does not need module 30.
- **87 before image formation.** What clinicians look for in an image gives
  the image quality measures of module 63 and the analysis tasks of modules
  66 to 70 their purpose, and module 86 needs it.
- **60 before 53, with 61 and 63 directly after it.** Every beamforming
  module has to display an image and measure it.
- **58 after 71.** It is the only beamforming module that trains a network,
  and the handling of training data is taught in modules 66 to 71.
- **Image processing before hardware.** Section 3 allows either order. The
  system operation modules 46 and 47 describe modes that modules 72 to 74
  teach, and module 47 needs modules 53 and 60.
- **85 and 86 after the hardware.** Module 85 needs the scan sequencing of
  module 46, and module 86 builds on the operating modes and system budgets
  of modules 47 and 48.

The course projects are placed where their prerequisites are complete. The
Course A project is done in two parts: the wave simulator after module 13 and
the signal processing library after module 29. The Course C project follows
stage 6. Of the Course D projects, the image analysis project follows module
71 and the flow or shear-wave estimator follows module 73. The Course B
project follows stage 8, and the capstone follows module 81.

The reference numbers of module 92 and the question bank of module 93 are
collected from the first module on and completed in stage 10.

The module template is fixed before the first module is written. The time
taken to work through the first modules is used to check the planning
estimate of section 3.

## 15. Known limits

- **Scanner access:** module 85 needs a research scanner and phantoms. Without
  a lab, it is limited to open channel data and simulation.
- **Proprietary practice:** commercial tuning and system architecture
  (modules 77 and 78) can only be taught from standards, patents, vendor white
  papers and research systems.
- **Credentials:** many algorithm and research roles ask for an advanced
  degree, which the curriculum does not replace.
