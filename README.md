# ESCAPE_school_project
Analysis of the first multi-messenger event, GW170817/GRB170817/AT2017gfo  using the Multi Order Coverage map (MOC):

The tutorial aims to analyze the [first multi-messenger event, GW170817/GRB170817/AT2017gfo](https://www.ligo.org/science/Publication-GW170817MMA/index.php) using the Multi Order Coverage map (MOC) to encode the gravitational-wave sky localizations from the LIGO and Virgo collaborations, and the gamma-ray-burst error boxes provided by the GBM instrument on board the Fermi Gamma-Ray Space Telescope and calculate from the IPN triangulation using the delay between Fermi and INTEGRAL. 



We plotted MOC maps with [Matplotlib library](https://matplotlib.org), using the class  **World2ScreenMPL** and we computed the area of the region and of the intersection between the different multi-order maps.


![Unknown](https://user-images.githubusercontent.com/91550119/156723952-6b7ec641-ae7d-4b51-aa30-b114c00847be.png)

Using [ipyAladin](https://github.com/cds-astro/ipyaladin)'s widgets, It's possible to have an interactive visualization of the skymap: select the target, the FoV and the survey.

<img width="429" alt="Schermata 2022-03-04 alle 11 18 51" src="https://user-images.githubusercontent.com/91550119/156749330-29ae196e-14bc-4c60-8c1d-468fb03ed7f4.png">

We used  the class [Space-Time MOC](https://cds-astro.github.io/mocpy/stubs/mocpy.STMOC.html) to obtaiin Spatial and Temporal intersection. The latter is important because Two astrophysics events are considered coincident if they are within a particular time window of each other.


Following [LIGO-Virgo Pubic Alert User Guide](https://emfollow.docs.ligo.org/userguide/index.html) in the section [Coincident with External Trigger Search](https://emfollow.docs.ligo.org/userguide/analysis/searches.html#coincident-with-external-trigger-search), we use the time window from -1 s to 5 s around the GW time. It means that we take into account GRBs up to one
second before or up to 5 seconds after the GW time. Following this prescription, the temporal interval to define the Space and Time MOC ranges from **2017-08-17T12:41:03 UTC to 2017-08-17T12:41:09 UTC**.

In the case of the GRB 170817, we added the trigger time reported in [An Ordinary Short Gamma-Ray Burst with
Extraordinary Implications: Fermi-GBM Detection of GRB 170817A](https://iopscience.iop.org/article/10.3847/2041-8213/aa8f41). The event was observed on 2017 August 17 at
12:41:06 UTC triggered by the Fermi gamma-ray Burst Monitor (GBM). ***T90 is 2.0**   0.5 s, starting at **T0 − 0.192 s**. With these values, we set an approximate time window from **2017-08-17T12:41:05.80 UTC to 2017-08-17T12:41:07.80 UTC**.

At list, we  query the galaxies collected in the [GLADE](https://vizier.u-strasbg.fr/viz-bin/VizieR?-source=VII/275) catalog inside the intersection area between the GW170817 and GRB 170817. Then, we filter those galaxies according to the marginal distance posterior distribution integrated over the whole sky and they are showed in the ipyaladin widget. 
The value reported in the header of GW170817 published in GWTC-1 GW170814_skymap.fits.gz.

<img width="837" alt="Schermata 2022-03-04 alle 11 40 19" src="https://user-images.githubusercontent.com/91550119/156749946-a7b1cc1b-7fd3-427c-912e-2ba56bc480ea.png">
