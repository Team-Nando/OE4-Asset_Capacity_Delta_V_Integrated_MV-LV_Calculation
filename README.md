# Assessment of Integrated MV-LV OE Calculations to Orchestrate DERs - OE Algorithm 4: Asset Capacity & Delta Voltage
This repository is part of the project [Accelerating the Implementation of Operating Envelopes Across Australia](https://electrical.eng.unimelb.edu.au/power-energy/projects/accelerating-the-implementation-of-operating-envelopes-across-australia) funded by CSIRO. This project provided key metrics, recommendations, and guidance for distribution companies (known as Distribution Network Service Providers [DNSPs] in Australia) and AEMO (the Australian system operator) to assist them in improving and, hence, accelerating the use of Operating Envelopes (OEs) across Australia.

In this repository, we use interactive code via Jupyter Notebook and Python as well as a [realistic integrated medium voltage and low voltage (MV-LV) network](https://github.com/Team-Nando/MV-LV-Networks) to demonstrate the process and necessary calculations for the *Asset Capacity & Delta Voltage OE Algorithm with Integrated MV-LV Calculation* produced by The University of Melbourne. This demonstration is useful for different stakeholders (e.g., DNSPs, AEMO, CSIRO, regulators, consultancy companies, technology providers) as it can help them familiarise with the corresponding algorithm and the required inputs as well as the pros and cons.

## Asset Capacity & Delta Voltage OE with Integrated MV-LV Calculation
The Asset Capacity & Delta Voltage OE with Integrated MV-LV Calculation is also an intermediate approach  - it is more advanced than the Asset Capacity OE as both voltage and thermal aspects are considered, but less advanced than the Ideal OE - that is still relatively simple to be implemented since it does not need network models and only an extra monitoring (e.g., smart meter, temporary network meter) at the critical customer when compared to the Asset Capacity OE. In this OE approach, thermal issues are solved by estimating the spare capacity of MV and LV networks, while voltages issues are solved by estimating the voltage at the critical customer (using two sensitivity curves) of each LV network. One sensitivity curve (called PMVTx-VDTx sensitivity curve) tries to capture the daily voltage variations at the LV HoF due to interactions with the upstream MV network (not captured by the Asset Capacity & Critical Voltage OE), while the other sensitivity curve (called PDTx-∆V sensitivity curve) tries to estimate the delta voltage between the LV HoF and the critical customer.
- Monitoring: At MV and LV head of feeders (P, Q, and V, all per phase), and at the critical customer of each LV network (voltage magnitude V).
- Electrical models: None.

## Pre-Requisites
- Python (Anaconda) and Jupyter Notebook (comes with Anaconda). For download links and more info: https://www.anaconda.com/download. Note that you must install the Anaconda that is compatible with your operating system (e.g., Windows, Mac). Also note that this repository is meant to be used by individuals (who can get free access to Anaconda).
- dss_python module. We use this Python-native module to run power flows based on OpenDSS (https://sourceforge.net/projects/electricdss/). To install, run `pip install dss_python` in the Anaconda Prompt. For more info: https://github.com/Team-Nando/Tutorial-DERHostingCapacity-0-dss_python#part-0-using-dss_python.
- To guarantee that you have all the necessary packages you can also run the **`requirements.txt`** file using **`pip install -r requirements.txt`** in the Anaconda prompt.

## Run the Code
Make sure you have installed all the pre-requisites (Anaconda, dss_python, requirements). Otherwise, you will not be able to go through the repository.

1. Download all the files using the green **`<> Code`** button at the top right.
   - You will get a ZIP file with a folder that contains all the files.
   - Unzip the file and place the folder somewhere on your computer/laptop.
2. To open the Jupyter Notebook file (extension **`ipynb`**) you need to:
   - Open Anaconda Navigator
   - Click on Launch Jupyter Notebook (it will open in your browser)
   - Upload the unzipped folder (with all the corresponding files) to Jupyter Notebook (the location is up to you)
   - Go inside the folder and open the **`ipynb`** file

All the instructions will be in the **`ipynb`** file.

## Credits
Arthur Gonçalves Givisiez (a.goncalvesgivisiez@unimelb.edu.au)

Nando Ochoa (luis.ochoa@unimelb.edu.au ; https://sites.google.com/view/luisfochoa)

## Acknowledgements
We acknowledge AusNet Services for providing the data listed below, which was essential to create this repository.
- Anonymised historical active power demand of some customers (smart meter data)
- The data (i.e., topology, impedances, distribution transformers) of one of their MV feeders (indirectly used by this repository)

More details of this data can be found in the [Team Nando GitHub repository for Australian MV-LV Networks](https://github.com/Team-Nando/MV-LV-Networks), files named "Network_4_Urban_CRE21" and "Profiles".

We also acknowledge the Australian Bureau of Meteorology for providing the solar radiation data.

## Licenses
Since this repository uses dss_python which is based on OpenDSS, both licenses have been included. This repository uses the BSD 3-Clause "New" or "Revised" license. Check all corresponding files (`LICENSE-OpenDSS`, `LICENSE-dss_python`, `LICENSE`).
