# Semiconductor Packaging
This GitHub repository documents the [Semiconductor Packaging - Fundamentals of Design and Testing 10-days Workshop](https://www.vlsisystemdesign.com/packaging/) offered by [VSD Corp. Pvt. Ltd.](https://www.vlsisystemdesign.com/about-us/) attended from 9-20 May, 2025.  

The workshop offers a full-pipeline understanding of the semiconductor packaging process, starting from the fundamentals and evolution of packaging to advanced 2.5D/3D architectures. We gain insights into advanced interconnect technologies, RDLs & interposers,  assembly processes, package reliability analysis, and also get to perform hands-on thermal simulations, package design and modeling using ANSYS tools.
<br/>

**Table of Contents**

 | Module # | Topic(s) Covered | Status |
 |---|---|---|
 |[**Mod. 1**](#1---packaging-evolution-from-basics-to-3d-integration) | **Packaging Evolution: From Basics to 3D Integration** <br> <ol> <li>[Introduction To Semiconductor Packaging And Industry Overview](#11---introduction-to-semiconductor-packaging-and-industry-overview)</li> <li>[Understanding Package Requirements And Foundational Package Types](#12---understanding-package-requirements-and-foundational-package-types)</li> <li>[Evolving Package Architectures - From Single Chip To Multi-Chip Modules](#13---evolving-package-architectures---from-single-chip-to-multi-chip-modules)</li> <li>[Interposers Re-distribution Layers And 2.5D/3D Packaging Approaches](#14---interposers-re-distribution-layers-and-25d3d-packaging-approaches)</li> <li>[Comparative Analysis And Selecting The Right Packaging Solution](#15---comparative-analysis-and-selecting-the-right-packaging-solution)</li> </ol> | ![](https://progress-bar.xyz/100/?title=Done) |
 |[**Mod. 2**](#2---from-wafer-to-package-assembly-and-manufacturing-essentials) | **From Wafer to Package: Assembly and Manufacturing Essentials** <br> <ol> <li>[Setting The Stage - Supply Chain And Facilities](#21---setting-the-stage---supply-chain-and-facilities)</li> <li>[Wafer Pre-Preparation - Grinding And Dicing](#22---wafer-pre-preparation---grinding-and-dicing)</li><li>[Wire Bond Packaging - Die Attach To Molding](#23---wire-bond-packaging---die-attach-to-molding)</li> <li>[Flip Chip Assembly - Bump Formation And Underfill](#24---flip-chip-assembly---bump-formation-and-underfill)</li> <li>[Wafer Level Packaging And Conclusion](#25---wafer-level-packaging-and-conclusion)</li> </ol> | ![](https://progress-bar.xyz/100/?title=Done) |
 |[**Mod. 3**](#3---labs-thermal-simulation-of-semiconductor-packages-with-ansys) | **Labs: Thermal Simulation of Semiconductor Packages with ANSYS** <br> <ol> <li>[Introduction And Getting Started With ANSYS Electronics Desktop](#31---introduction-and-getting-started-with-ansys-electronics-desktop)</li> <li>[Setting Up A Flip-Chip BGA Package](#32---setting-up-a-flip-chip-bga-package)</li> <li>[Material Definitions And Thermal Power Sources](#33---material-definitions-and-thermal-power-sources)</li> <li>[Meshing And Running The Thermal Analysis](#34---meshing-and-running-the-thermal-analysis)</li> <li>[Viewing Results And Exploring Other Package Types](#35---viewing-results-and-exploring-other-package-types)</li> </ol> | ![](https://progress-bar.xyz/100/?title=Done) |
 |[**Mod. 4**](#4---ensuring-package-reliability-testing-and-performance-validation) | **Ensuring Package Reliability: Testing and Performance Validation** <br> <ol> <li>[Introduction to Package Testing and Electrical Functionality Checks](#41---introduction-to-package-testing-and-electrical-functionality-checks)</li> <li>[Reliability and Performance Testing of Semiconductor Packages](#42---reliability-and-performance-testing-of-semiconductor-pack--ages)</li> </ol> |  ![](https://progress-bar.xyz/100/?title=Done) |
 |[**Mod. 5**](#5---package-design-and-modeling-building-a-semiconductor-package-from-scratch) | **Package Design and Modeling: Building a Semiconductor Package from Scratch** <br> <ol> <li>[Introduction to Package Cross-Section Modeling in ANSYS Electronics Desktop (AEDT)](#51---introduction-to-package-cross-section-modeling-in-ansys-electronics-desktop-aedt)</li> <li>[Creating the Die and Substrate in AEDT](#52---creating-the-die-and-substrate-in-aedt)</li> <li>[Adding Die Attach Material and Bond Pads](#53---adding-die-attach-material-and-bond-pads)</li> <li>[Wire Bond Creation and Material Assignment](#54---wire-bond-creation-and-material-assignment)</li> <li>[Applying Mold Compound and Finalizing the Package Model](#55---applying-mold-compound-and-finalizing-the-package-model)</li> </ol> | ![](https://progress-bar.xyz/100/?title=Done) |


## 1 - Packaging Evolution: From Basics to 3D Integration
Semiconductor packaging refers to the final stage of semiconductor device fabrication, where the finished semiconductor die is enclosed in a protective package that allows it to be integrated into electronic systems.
**_Basically, the package helps transition a fragile silicon die fabricated in a foundry cleanroom into the real-world system/ product._**

The key Functions of semiconductor package are:
  1. **Protection** from external environmental (physical/ mechanical damage, humidity, corrosion/ contaminants & chemical damage and ESD)
  2. **Electrical connectivity** between the die and the external environment via leads (pins, balls or lands)
  3. **Mechanical support and connection** of the die to the system
  4. **Thermal dissipation** to conduct heat away from the die

### 1.1 - Introduction To Semiconductor Packaging And Industry Overview
<br>

| ![Semiconductor_Packaging](./docs/images/M1_L1_1.png) |
|:---:|

The semiconductor manufacturing process consists of the front-end process which refers to the wafer manufacturing and the back-end process which consists of packaging and testing. (Even the wafer manufacturing process is split into a front-end and back-end process - with the front-end typically consisting of the CMOS-making process, and the back-end comprising the metal wiring formation process that comes after the CMOS is made.)

The following figure is a flow chart that shows the relationship between the semiconductor manufacturing process and the semiconductor industry. The first phase of the packaging and testing process is wafer testing. Afterwards, packages are made in the packaging process and followed by the package test stage.  

| ![Semiconductor_Manufacturing](./docs/images/M1_L1_2.png) |
|:---:|

_Ref:_ [_SK Hynix Newsroom: Semiconductor Back-End Process Episode 3_](https://news.skhynix.com/semiconductor-back-end-process-episode-1-understanding-semiconductor-testing/)

  - Companies like Nvidia, Qualcomm and Apple that only design semiconductors are called “fabless.”
  - Products designed by fabless companies are made into wafers, and the facilities that produce these wafers are called “foundries.” Global companies with these facilities include TSMC, Global Foundries and UMC.
  - Then, there are companies that test and package products that were designed by fabless vendors and, later, made into wafers at foundries. These are called OSAT (Out-Sourced Assembly and Test) which include companies such as ASE and Amkor.
  - Finally, there are the companies that do everything from design, wafer production, and packaging, to testing. These companies are called IDMs (Integrated Device Manufacturer).

### 1.2 - Understanding Package Requirements And Foundational Package Types
#### 1.2.1 - Package Requirements
Selecting the right semiconductor package is a critical step in electronic system design, as it affects performance, cost, thermal management, size, and reliability. 

| ![Package_Requirements](./docs/images/M1_L2_2.png) |
|:---:|

The criteria for semiconductor package selection generally fall into the following key categories:
  - **Application-specific Requirements**
    - Logic/ Memory die
    - Power semiconductor die)
  - **Electrical Requirements**
    - I/O Pin Count
    - Signal Integrity for high speed I/Os
    - Power Delivery
  - **Thermal Requirements**
    - Thermal Dissipation
    - Operating Temperature Range
  - **Mechanical and Physical constraints**
    - Form Factor: Footprint and chip height requirements for the system
    - System Integration needs: MCM, SiP, 2.5/3D packaging for tighter integration
  - **Cost Considerations**
    - Package cost
    - Board/ System Assembly cost
  - **Reliability and Durability**
    - Mechanical stress
    - Thermal cycling
    - Moisture and other environmental factors

#### 1.2.2 - Typical Package Structure
The following figure below shows the structure of a typical chip package and the connection hierarchy:

| ![Package_Structure](./docs/images/M1_L2_3.png) |
|:---:|

A typical IC package consists of:
  1. **Die**: The semiconductor die itself.
  2. **Carrier/ Substrate**: The carrier or substrate is the intermediate structure on which the die sits and provides both mechanical support and electrical contact.
  3. **Die-to-carrier interconnections**: The die is connected to the substrate using bond wires or solder bumps
  4. **Carrier-to-Board interconnections**: The substrate is often soldered/ connected to the PCB for integration into larger systems using pins, leads balls or lands.
  - **Mold Compound**: A molding compound (commonly epoxy or plastic) encapsulates the whole die & other components, and provides protection from moisture, contaminants, and physical damage.

**Mounting Technologies:**
  - **Through-hole Mounting**
    - TO : Transistor Outline
    - SIP : Single In-line Package
    - DIP : Dual In-line Package
    - PGA : Pin Grid Array
  - **Surface Mount Technology**:
    - (T)SOT : (Thin) Small Outline Transistor
    - (T)SOP : (Thin) Small Outline Package
    - SOIC : Small Outline IC Package
    - QFN : Quad Flat No-leads
    - QFP : Quad Flat Package
    - PBGA : Plastic Ball Grid Array
    - LGA : Land Grid Array
    - FCBGA : Flip Chip Ball Grid Array
    - CSP : Chip Scale Package
  - **Advanced Packages**
    - PoP : Package on Package (Qualcomm SD series, Apple A-Series, Samsung Exynos etc.)
    - MCM : Multi-Chip Module (eg: Intel Broadwell)
    - SiP : System-in-Package (Apple S1)
    - CoWoS : Chip on Wafer on Substrate (eg: Nvidia GP100, GV100, GA100, etc.)

### 1.3 - Evolving Package Architectures - From Single Chip To Multi-Chip Modules
#### 1.3.1 Classification and Anatomy of Semiconductor Packages

The various types of semiconductor packages can be broadly grouped into two main categories:
  - Conventional Packages
  - Wafer-level packages

In conventional packaging, the wafer is sawed into dice before the chip is packaged, while wafer-level packaging involves a part, or all, of the packaging process being performed at the wafer level before proceeding with wafer sawing.

| ![Package_Classification](./docs/images/M1_L3_2.png) |
|:---|
| _Ref:_ [_SK Hynix Newsroom: Semiconductor Back-End Process Episode 3_](https://news.skhynix.com/semiconductor-back-end-process-episode-3-understanding-the-different-types-of-semiconductor-packages/)_ |

Depending on the medium of the package, packages can be further categorized into leadframe and laminate packages.
  - **Leadframe-Based Packages**
    - **DIP**: Traditional, with wirebonds and external leads
    - **QFN**: Compact with exposed thermal pads
    - **Leadframe CSP & QFP**: Scaled for density and SMT

  - **Laminate-Based Packages**
    - **PBGA**: Wirebonded to laminated substrates
    - **Flip Chip PBGA**: Superior signal and thermal performance
    - **LGA, FCCSP**: Common in modern devices

  - **Advanced Substrates**
    - **2D**: Dies placed side-by-side on the same substrate
    - **2.1D**: Adds RDL for better routing
    - **2.3D**: Uses organic interposers
    - **2.5D**: Silicon interposer for high-speed interconnects (e.g.: CoWoS)

The below figure shows the anatomy of some of the commonly used leadframe and laminate based packages and advanced substrates:

| ![Package_Anatomy](./docs/images/M1_L3_1.png) |
|:---|

### 1.4 - Interposers, RDLs And 2.5D/3D Packaging Approaches

| ![Package_Interposers_RDLs](./docs/images/M1_L4_1.png) |
|:---|

#### 1.4.1 - Redistribution Layers (RDL)
RDL (Redistribution Layer) is a metal layer added on top of a die or wafer to reroute the I/O pads to new locations. This enables more flexible bump layouts, especially important for fan-out packages or wafer-level chip scale packaging (WLCSP).

  - Applications
    - Fan-out wafer-level packaging (FO-WLP, FO-BGA)
    - Panel-level packaging (PLP)
    - Multi-die integration
    - System-in-Package (SiP)

  - Advantages:
    - Allows larger bump pitch for finer pad layouts
    - Reduces package size and thickness
    - Enables multi-chip placement and interconnect on a single substrate

#### 1.4.2 - Interposers
An interposer is a passive or active layer inserted between the die and the substrate, acting as an intermediate routing interface. It enables dense signal routing, power delivery, and die-to-die interconnect.

  - Types: Silicon, Organic, Glass

  -  Functions:
    - Routes signals between multiple dies (e.g., chiplets)
    - Provides thermal expansion management
    - Enables high bandwidth communication

  - Passive vs. Active Interposers:
    - Passive: No logic, just routing and vias
    - Active: Includes power delivery, clocking, or even memory logic

#### 1.4.3 - 2.5D/3D Integration
  - **2.5D**: Multiple dies (e.g., CPU + HBM) placed side-by-side on a common interposer. Interposer provides connectivity, not the substrate directly. Popular in HPC and AI (e.g., AMD Instinct, NVIDIA GPUs with HBM).
  - **3D**: Dies are stacked vertically, interconnected through Through-Silicon Vias (TSVs). 3D NAND, HBM memory stacks, logic-on-logic stacking.

### 1.5 - Comparative Analysis And Selecting The Right Packaging Solution
The following table provides a comparison of the various IC package types and their typical applications:

| ![Packages_Comparison](./docs/images/M1_L5_1.png) |
|:---|

Selecting the right semiconductor packaging depends on multiple criteria across performance, reliability, form factor and cost.
_________________________________________________________________________________________________________  

## 2 - From Wafer to Package: Assembly and Manufacturing Essentials
This section covers the semiconductor supply chain and provides a detailed look into a package manufacturing unit (**ATMP** – Assembly, Testing, Marking, and Packaging).

### 2.1 - Setting The Stage - Supply Chain And Facilities
#### 2.1.1 - Semiconductor Supply Chain Overview
The semiconductor supply chain is a multi-step process that transforms raw silicon into fully functional electronic products. The major steps are:

| Semiconductor Supply Chain Review|
|:---|
| **1. Design : Chip design and verification** <br> <ul> <li>**Input** : Product requirements specification, EDA tools, Foundry PDKs, IPs</li> <li>**Output** : GDSII layout file is _taped out_ to the foundry for mask creation and wafer fabrication. Test programs are also provided by the Design house for Wafer and Package level testing.</li> <li>Examples: Nvidia, AMD, MediaTek, Intel, TI, Apple, ARM etc.</li> </ul> |
| **2. Wafer Fabrication (Foundry) : Physical ICs are manufactured onto wafers using photolithography and other processes** <br> <ul> <li> **Input** : GDSII layout, Silicon wafers, Equipment, Gases, chemicals, Materials</li> <li> **Output**: Processed wafers with patterned dies</li> <li> Examples: TSMC, Samsung, Intel, GlobalFoundries</li> </ul> |
| **3. Packaging Assembly & Test : ICs are cut (diced), bonded, encapsulated, and tested** <br> <ul> <li>**Input**: Test programs, Singulated dies, substrate materials (e.g., ABF, BT resin), solder bumps</li> <li> **Output**: Packaged IC (e.g., BGA, QFN, FCBGA, 2.5D/3D)</li> <li> Examples: ASE, Amkor, JCET, Shinko, Ibiden</li> </ul> |
| **4. Board Assembly & Test : Multiple packaged ICs are mounted and board-level validation** <br> <ul> <li>**Input**: Packaged ICs, test programs, ATE systems</li> **Output**: Qualified ICs, binned by performance. Yield improvement and binning are critical for profitability.</li> <li> Examples: ASE, Powertech, Amkor, UTAC</li> </ul> |
| **5. System Integration & Distribution** <br> <ul> <li>**Input**: Packaged, tested ICs; PCBs; passive components </li> <li> **Process**: SMT assembly, system-level integration, validation </li> <li>**Output**: Complete electronic systems (e.g., smartphones, servers) </li> <li>Examples: OEMs Original Equipment Manufacturer (Apple, Cisco), ODMs Original Design Manufacturer (Foxconn, Pegatron), EMS Electronics Manufacturing Services (Flex, Jabil)</li> </ul> |

| ![Semiconductor_Supply_Chain](./docs/images/M2_L1_1.png) |
|:---|

#### 2.1.2 - Introduction to a Package Manufacturing Unit (ATMP)
The ATMP process involves four core activities: Assembly, Testing, Marking, and Packaging.
The ATMPs could be OSATs (like ASE, Amkor, TATA etc.) or in-house ATMPs of IDMs (like Intel, Samsung, Micron) or Foundries (like TSMC, Samsung Foundry)

| **Typical layout of an ATMP:** <br> ![Typical_ATMP_Layout](./docs/images/M2_L1_2.png) |
|:---|

  1. Material Preparation and Storage
    - Incoming Wafers, Substrates, Leadframes, Mold Compounds, Consumables
  2. Processing Zone (Clean Room: ISO Class 6 & 7)
    - Major activities:
      - Die Attach & Mount
      - Wire or Flip-Chip Bonding
      - RDL formation
      - Encapsulation/ molding.
  3. Testing Area
    - Electrical Tests
    - Burn-in Test
    - Reliability chamber testing
  4. Warehouse
    - Storage of packaged ICs

### 2.2 - Wafer Pre-Preparation - Grinding And Dicing

This section explains the wafer preparation process inside an ISO Class 7 cleanroom of an ATMP (Assembly, Testing, Marking, and Packaging) facility. 

| ![Wafer_Grinding_Dicing](./docs/images/M2_L2_1.png) |
|:---|

1. **Incoming Wafer Carrier**: Wafers arrive in a protective carrier that ensures they remain uncontaminated before entering the processing line.

2. **Wafer Inspection**: The wafers are visually and optically inspected for surface defects, contamination, or damage before further processing.

3. **Wafer Front Tape Lamination**: A protective tape is laminated on the front (device side) of the wafer to protect it during subsequent processes like grinding and dicing.

4. **Wafer Backside Grinding**: The wafer’s backside is ground using a rotating grinding wheel to reduce the wafer thickness from the ~700um to around 200um and enable better thermal performance and flexibility for final packaging.

5. **Tape Frame Mounting to Wafer Backside**: After grinding, the wafer is mounted on a ring frame using an adhesive tape. This stabilizes the wafer and keeps individual die in place during dicing.

6. **Two-step Wafer Dicing (Laser Grooving + Blade Dicing)**: <br>
6.1 **Laser Grooving**: Precision laser cuts grooves along scribe lines to weaken the wafer structure. <br>
6.2 **Blade Dicing**: A high-precision blade is then used to physically dice the wafer into individual dies or chips. <br>

### 2.3 - Wire Bond Packaging - Die Attach To Molding

| ![Wire_Bond_Packaging](./docs/images/M2_L3_1.png) |
|:---|

1. **Die Attach**: The individual (die) is attached to a substrate or lead frame using epoxy. <br>
1.1 The Epoxy is dispensed onto the die in some pattern so as to avoid any voids during attach. (Pattern complexity vs. speed of processing trade-off) <br>
1.2 The die is picked up by the pick-up head, and <br>
1.3 Placed on the Die Attach Film (DAF) <br>

2. **Curing**: The die-attached unit is subjected to a heating process to cure the epoxy, ensuring a strong and stable bond between the die and the substrate.

3. **Wire Bonding**: Fine gold or aluminum wires are bonded between the die and the package substrate pads using thermal and ultrasonic energy. <br>
3.1 Formation of a ball bond using an EFO (Electronic Flame-Off) spark
3.2 Bonding the ball to the die pad (using pressure, vibration, heat)
3.3 Creating a wire loop
3.4 Forming a crescent bond on the substrate side

4. **Molding (Transfer Molding)**: A mold compound is injected to encapsulate the wire-bonded die, providing protection from environmental damage and mechanical stress. Resin flows uniformly to cover the entire chip.

5. **Marking (Laser)**: Laser marking is used to engrave identification codes, logos, or batch numbers on the molded package surface.

6. **Singulation (Dicing Blade)**: The molded wafer is cut into individual units (ICs) using a dicing blade. A thinner blade is typically used to minimize chipping and maximize precision.



### 2.4 - Flip Chip Assembly - Bump Formation And Underfill

Flip chip packaging enhances electrical performance and I/O density by mounting the die face-down on the substrate.

| ![FlipChip_Packaging](./docs/images/M2_L4_1.png) |
|:---|

1. **Bump Formation on Silicon (Si)**:
1.1 Solder bumps are created on the die. <br>
1.2 The bumps are then reflowed to form strong electrical and mechanical connections. <br>

2. **Chip Flip and Placement**:
2.1 The chip is flipped upside down. <br>
2.3 Flux is dispensed on to the substrate to aid solder wetting. <br>
2.2 Solder balls are aligned with the substrate’s bond pads. <br>

3. **Solder Reflow**: The chip is heated so that the solder balls melt and bond with the substrate.

4. **Flux Cleansing**: The excess residual flux is removed using solvent spray to prevent corrosion.

5. **Underfill Dispensing**: Underfill material is applied to improve mechanical strength and thermal conductivity between the die and substrate.

6. **Underfill Cure**: Heated to cure the underfill.

7. **Molding**: A protective mold compound is applied.

8. **Marking**: Laser marking is done for identification (part number, lot, batch, date of manufacture etc.) and traceability.

9. **Ball Mounting and Reflow**: Solder balls are mounted on the substrate. A final reflow process ensures firm attachment of solder balls.

### 2.5 - Wafer Level Packaging And Conclusion

Wafer-Level Packaging (WLP) is a technique where the entire packaging process is done at the wafer level, before dicing and offers smaller size, and lower cost.  
There are two main types of WLP:
  - Fan-in WLP (FI-WLP) : I/O pads are redistributed within the die area to match the solder bumps.
  - Fan-out WLP (FO-WLP) : Uses RDLs to extend the I/O pads beyond the die area, enabling higher I/O density.

**<U>FO-WLP Process</U>**

| ![WLP](./docs/images/M2_L5_1.png) |
|:---|

1. **Reconstitution Process:**
1.1 Diced Wafer is taken <br>
1.2 From this, only the known-good dies are picked and placed onto a temporary carrier. <br>
1.3 Molding to form a single reconstituted wafer after releasing the carrier. <br>

2. **RDL (Redistribution Layer) Preparation**:
2.1 Dielectric & Metal are layers are deposited on to the reconstituted wafer and patterned. <br>
2.2 Multiple such RDL layers are patterned to form the final RDL, similar to the metallization stages in FEOL/ CMOS facbrication <br>

3. **Solder Ball Attach**: Solder Balls are mounted on the final RDL pads to enable surface mounting. <br>

4. **Final Laser Marking and Singulation**: Each packaged die is marked and the reconstituted wafer is diced (singulated) into individual packages.

_________________________________________________________________________________________________________  

## 3 - Labs: Thermal Simulation of Semiconductor Packages with ANSYS tools

### 3.1 - Introduction And Getting Started With ANSYS Electronics Desktop

ANSYS Electronics Desktop (AEDT) is a multi-physics simulation software that combines Electromagnetic, Signal Integrity, Thermal and Electro-Mechanical simulation tools in a single integrated platform. It is widely used for designing and analyzing high-speed electronic circuits and systems.

### 3.2 - Setting Up A Flip-Chip BGA Package

We will be taking an already available FC-BGA package within the Icepak Toolkit for this simulation exercise.


  - **Step 1 : Open AEDT and launch Icepak**

| ![AEDT_IcePak_1](./docs/images/Lab1_FCBGA_ThermalSim_1.png) |
|:---|

  - **Step 2.1 : Create a Flipchip BGA Package**
    - `Icepak -> Toolkit -> Geometry -> Packages -> Flipchip_BGA`

| ![AEDT_IcePak_2](./docs/images/Lab1_FCBGA_ThermalSim_2.png) |
|:---|

  - **Step 2.2 : The Package Configuration window opens up**
    - The dimensions and other aspects of the package, substrate, die, die underfill and the solder balls can be configured here.
    - Once configured, click OK to generate the package model. 

| ![AEDT_IcePak_3](./docs/images/Lab1_FCBGA_ThermalSim_3.png) | ![AEDT_IcePak_4](./docs/images/Lab1_FCBGA_ThermalSim_4.png) |
|:---|:---|
| ![AEDT_IcePak_5](./docs/images/Lab1_FCBGA_ThermalSim_5.png) | ![AEDT_IcePak_6](./docs/images/Lab1_FCBGA_ThermalSim_6.png) |

| Package generated in Icepak <br> ![AEDT_IcePak_7](./docs/images/Lab1_FCBGA_ThermalSim_7.png) |
|:---|

  - **Step 3 : Explore the 3D Package Model Structure in Icepak**

| **Ball Group** <br> ![AEDT_IcePak_8](./docs/images/Lab1_FCBGA_ThermalSim_8.png) | **Substrate** <br> ![AEDT_IcePak_9](./docs/images/Lab1_FCBGA_ThermalSim_9.png) |
|:---|:---|
| **Die Underfill** <br> ![AEDT_IcePak_10](./docs/images/Lab1_FCBGA_ThermalSim_10.png) | **Die** <br> ![AEDT_IcePak_11](./docs/images/Lab1_FCBGA_ThermalSim_11.png) |

### 3.3 - Material Definitions And Thermal Power Sources

  - **Step 4 : Review and modify the material and definition types for the different components of the model.**

| Material Definitions <br> ![AEDT_IcePak_12](./docs/images/Lab1_FCBGA_ThermalSim_12.png) |
|:---|

  - **Step 5.1 : Add/ Assign Source Thermal Model for Die**
    - In "Project Manager" sub-window, expand Thermal section and open the **_BGA1_die_source_** and configure the thermal condition as shown below:

| Source Thermal Model for Die <br> ![AEDT_IcePak_13](./docs/images/Lab1_FCBGA_ThermalSim_13.png) |
|:---|

- **Step 5.2 : Add/ Assign Source Thermal Model for Substrate**
    - To add a thermal boundary condition for the substrate, right click on **_Flipchip_BGA1_substrate_** under `Models -> Flipchip_BGA1_Group -> Solids` and assign a Thermal Source.
    - Set the thermal condition on the substrate to Fixed Temperatue and the temperature as Ambient.

| Add Source Thermal Model for Substrate <br> ![AEDT_IcePak_14.1](./docs/images/Lab1_FCBGA_ThermalSim_14.1.png) | ![AEDT_IcePak_14.2](./docs/images/Lab1_FCBGA_ThermalSim_14.2.png) |
|:---|:---|

  - **Step 6 : Add Thermal monitors for the different components**
    - To add a Thermal monitor to the substrate, right click on the **_Flipchip_BGA1_substrate_** under `Models -> Flipchip_BGA1_Group -> Solids` and then choose `Assign Monitor -> Point...`
    - In the sub-window that appears, select **Temperature**
    - Repeat the same to add thermal monitors for the die and the die-underfill.

| Add Thermal monitor for Substrate <br> ![AEDT_IcePak_15.1](./docs/images/Lab1_FCBGA_ThermalSim_15.1.png) | ![AEDT_IcePak_15.2](./docs/images/Lab1_FCBGA_ThermalSim_15.2.png) |
|:---|:---|

| Thermal monitors added <br> ![AEDT_IcePak_16](./docs/images/Lab1_FCBGA_ThermalSim_16.png) |
|:---|

### 3.4 - Meshing And Running The Thermal Analysis

  - **Step 7.1 : Generate Mesh**
    - Go to the Simulation tab and click on `Generate Mesh`
    - Save the project if prompted and wait for the mesh generation to get completed.
    - Take a note of any error(s) and warning(s) that are shown and ignore/ take steps to debug & fix the issue(s) as required.

  - **Step 7.2 : Review Mesh Quality metrics**
    - Once the mesh is generated, review the quality metrics of the generated mesh such as Face Alignment, Skewness and Volume.

| **Mesh Generation** <br> ![AEDT_IcePak_17](./docs/images/Lab1_FCBGA_ThermalSim_17.png) |
|:---|

| **Mesh Quality - Face Alignment** ![AEDT_IcePak_17.1](./docs/images/Lab1_FCBGA_ThermalSim_17.1.png) | **Mesh Quality - Skewness** ![AEDT_IcePak_17.2](./docs/images/Lab1_FCBGA_ThermalSim_17.2.png) |
|:---|:---|
| **Mesh Quality - Volume** ![AEDT_IcePak_17.3](./docs/images/Lab1_FCBGA_ThermalSim_17.3.png) | |

  - **Step 8 : Add Thermal Analysis**
    - Under `Project Manager`, right click on `Analysis and then, select Add Analysis Setup` and configure the solver settings as required. (We will choose all default settings for our analysis)

| **Add Analysis Setup** <br> ![AEDT_IcePak_18](./docs/images/Lab1_FCBGA_ThermalSim_18.png) |
|:---|

### 3.5 - Viewing Results And Exploring Other Package Types

  - **Step 9 : Now, Validate the Simulation setup**
    - Click on the **Validate** button in the top ribbon
    - Ensure all checks are validated successfully

| **Validate the setup** <br> ![AEDT_IcePak_19](./docs/images/Lab1_FCBGA_ThermalSim_19.png) |
|:---|

  - **Step 10: Run the simulation and plot the temperature map**
    - Click on **Analyze All** button in the top ribbon
    - Wait for the simulation to get completed successfully. Take note of any warning(s) or errors that may need further debug or setup modification(s).
    - Once the simulation is completed, select the complete FC-BGA package in the 3D view by drawing a selection rectangle using the left-mouse button.
    - Right click and then select `Plot Fields -> Temperature -> Temperature`
    - Configure the different plot options:
      - Specify Name, Folder
      - Plot on Surface only
      - Surface Smoothing -> Enable Gaussian Smoothing

| **Plot Fields** ![AEDT_IcePak_20](./docs/images/Lab1_FCBGA_ThermalSim_20.png) | **Field Plot Settings** ![AEDT_IcePak_21](./docs/images/Lab1_FCBGA_ThermalSim_21.png) |
|:---|:---|
| **Field Plot - Top view** ![AEDT_IcePak_22](./docs/images/Lab1_FCBGA_ThermalSim_22.png) | **Field Plot - Bottom view** ![AEDT_IcePak_23](./docs/images/Lab1_FCBGA_ThermalSim_23.png) |


_________________________________________________________________________________________________________  

## 4 - Ensuring Package Reliability: Testing and Performance Validation

### 4.1 - Introduction to Package Testing and Electrical Functionality Checks

ICs are tested at multiple points during the manufacturing process to ensure they meet performance, reliability, and functionality requirements. Testing takes place both at the foundry and at OSAT facilities.

| ![Testing_at_Different_Stages](./docs/images/M4_L1_1.png) |
|:---|

#### 4.1.1 - Foundry Testing Stages
**1. Front-End Manufacturing**
  - Involves fabrication of integrated circuits on silicon wafers.
  - Leads to fine tuning of the Process parameters to improve yield, reduce IDDQ/ leakage and improve speed/ performance.

**2. Wafer Probe Test**
  - Wafer is mounted on a probe station and a probe card with makes contact with the bond pads or bump pads of each die.
  - An ATE can now send test patterns to mark the die as good or bad.

#### 4.1.2 - OSAT Testing Stages
**1. Wafer Sorting**
  - Dies are sorted based on probe test results.
  - Only functional dies proceed to packaging.

**2. Package Manufacturing**
  - Functional dies are packaged

**3. Package Testing**
  - Conducted in ISO Class 6/7 cleanroom zones
  - Testing includes:
    - AOST (Assembly Open and Short Test): Shorts/ Opens in Packages
    - Burn-in Test: Elevated temperature and voltage and power cycling are applied to accelerate ageing to catch early failures.
    - Final Test: Validate the electrical performance of the packaged IC across temperature and voltage corners and ensure it meets the datasheet specifications.

| ![Package_Testing_1](./docs/images/M4_L1_2.png) | ![Package_Testing_2](./docs/images/M4_L1_3.png) |
|:---|:---|

**4. System Level Testing (SLT)**
  - Testing is performed in conditions that closely mimic real-world system operation. SLT verifies how a chip behaves when it runs actual software or firmware inside a system-like environment.

### 4.2 - Reliability and Performance Testing of Semiconductor Packages

#### 4.2.1 Burn-in and Final Test

**1. Burn-In Test**
  - Burn-in testing is a reliability screening process where semiconductor devices are exposed to elevated temperatures, voltages, and operating conditions for an extended period to accelerate aging and failure mechanisms.
  - It is used to identify and eliminate early-life failures (also called "infant mortality") in ICs before they are shipped to end users.

| ![Package_Testing_3](./docs/images/M4_L2_1.png) |
|:---|

**2. Final Test (FT)**
  - Final Test is the last major electrical test phase after the semiconductor die has been packaged.
  - It verifies that the packaged device meets all functional, parametric, and performance specifications before it is shipped to customers.
  - It is typically performed by OSATs (Outsourced Semiconductor Assembly and Test providers) or in-house test facilities.

| ![Package_Testing_4](./docs/images/M4_L2_2.png) |
|:---|


**Summary: ATE & Test Categories**

| ![Package_Testing_5](./docs/images/M4_L2_3.png) |
|:---|
_________________________________________________________________________________________________________  

## 5 - Package Design and Modeling: Building a Semiconductor Package from Scratch

This is a hands-on lab to design a semiconductor wire bond package from scratch using Ansys Electronics Desktop (AEDT). 

### 5.1 - Introduction to Package Cross-Section Modeling in ANSYS Electronics Desktop (AEDT)

The main focus of this lab exercise is to build the complete cross-section of a wire bond package, including die, substrate, bonding wires, and mold compound, rather than performing any simulation or analyses.

**<U>Package Specifications:</U>**
| Component | Properties |
|:---|:---|
| 1. Die | <ul> <li>Material : Silicon</li> <li>Dimensions : 3mm x 3mm</li> <li>Die Height : 200 micron</li> </ul> |
| 2. Substrate | <ul> <li>Material : FR4</li> <li>Dimensions : 5mm x 5mm</li> <li>Height : 500 micron</li> </ul> |
| 3. Die Attach | <ul> <li>Material : Modified Epoxy</li> <li>Dimensions : 3mm x 3mm</li> <li>Thickness : 100 micron</li> </ul> |
| 4. Die Bond Pads | <ul> <li>Material : Copper</li> <li>Dimensions : 0.2mm x 0.2mm</li> <li>Thickness : 5 micron</li> </ul> |
| 5. Substrate Bond Pads | <ul> <li>Material : Copper</li> <li>Dimensions : 0.2mm x 0.2mm</li> <li>Thickness : 10 micron</li> </ul> |
| 6. Bond Wire | <ul> <li>Material : Gold wire</li> <li>Type: JEDEC 4-point</li> </ul> |
| 7. Mold Compound | <ul> <li>Material : Epoxy</li> <li>Thickness : 1.2mm</li> </ul> |

  - **Step 1 : Launch AEDT and select Q3D (or Icepak, Maxwell 3D)**

| ![AEDT_Q3D_1](./docs/images/Lab2_PackageModeling_1.png) |
|:---|

### 5.2 - Creating the Die and Substrate in AEDT

  - **Step 2 : Define the working unit**
    - `Modeler -> Units...`
    - Choose **mm** or **um** as the working unit for creating the model.

| Set working Units <br> ![AEDT_Q3D_2.1](./docs/images/Lab2_PackageModeling_2.1.png) | ![AEDT_Q3D_2.2](./docs/images/Lab2_PackageModeling_2.2.png) |
|:---|:---|

  - **Step 3.1 : Create the Die Geometry**
    - Select the rectangle tool from the ribbon or using the Menus (`Draw -> Rectangle`) to draw a rectangle
    - Now, double click on **CreateRectangle** `Model -> Rectangle1` to open up its Properties Dialog box.
    - Specify the position with one corner at the origin (0, 0, 0) and the dimensions as 3mm x 3mm
    - Select `Model -> Rectangle1` and from the menu bar: `Modeler -> Surface -> Thicken Sheet...` and set the thickness to 200 microns (0.2mm)

  - **Step 3.2 : Assign Material Properties**
    - Open up the Properties Dialog box either by double clicking on `Model -> Rectangle1`
    - Rename the geometry to **Die**
    - Choose **Silicon** as the material from the Material Library.

| **Die Geometry** <br> ![AEDT_Q3D_3.1](./docs/images/Lab2_PackageModeling_3.1.png) | **Die Thickness** ![AEDT_Q3D_3.2](./docs/images/Lab2_PackageModeling_3.2.png) |
|:---|:---|
| **Die Material** <br> ![AEDT_Q3D_3.3](./docs/images/Lab2_PackageModeling_3.3.png) |  |

  - **Step 4.1 : Create the Substrate Geometry**
    - Draw another rectangle for the substrate (5mm x 5mm) and position (-1, -1, 0) it such that the die is at the center.
    - Set the thickness as -500 microns (-0.5mm). Note the negative sign so as to have the substrate lie beneath the die.
    - Adjust the substrate position along Z-axis to account for the die attach thickness. **Adjusted position: (-1, -1, -0.1)**

| **Substrate Geometry** <br> ![AEDT_Q3D_4.1](./docs/images/Lab2_PackageModeling_4.1.png) | **Substrate Material** ![AEDT_Q3D_4.2](./docs/images/Lab2_PackageModeling_4.2.png) |
|:---|:---|
| **Substrate position considering Die attach thickness** <br> ![AEDT_Q3D_4.3](./docs/images/Lab2_PackageModeling_4.3.png) |  |

### 5.3 - Adding Die Attach Material and Bond Pads

  - **Step 5 : Create the Die Attach Material**
    - Draw a rectangle of the same size as that of the die (3mm x 3mm) and at the same co-ordinates (0, 0, 0).
    - Set the thickness to -100 microns (-0.1mm) as the DAM lies beneath the die and the substrate
    - Assign the material to _**Modified Eopxy**_
    - **NOTE:** Assign different shades/ colours to adjacent components to easily discern in 3D view.

| **Die Attach Material** <br> ![AEDT_Q3D_5.1](./docs/images/Lab2_PackageModeling_5.1.png) | **Geometry** ![AEDT_Q3D_5.2](./docs/images/Lab2_PackageModeling_5.2.png) |
|:---|:---|
| **Material** <br> ![AEDT_Q3D_5.3](./docs/images/Lab2_PackageModeling_5.3.png) |  |

  - **Step 6 : Create Bond pads on Die and Substrate**
  - Draw a small rectangle and configure its size to to that of the die pad (0.2mm x 0.2mm). We will place the first Die Pad at the co-ordinates (0.2, 0.2, 0.2) so that it sits on top of the die and is at one of the edges.
  - Set the thickness to 5 microns (0.005mm)

| **Die Bond Pad** <br> ![AEDT_Q3D_6.1](./docs/images/Lab2_PackageModeling_6.1.png) |
|:---|

  - Similarly, draw a small rectangle and configure its size to to that of the substrate bond pad (0.2mm x 0.2mm).
  - We will place this Substrate Bind Pad at the co-ordinates (0.2, -0.7, -0.1) so that it sits aligned to the Die bond pad created in the previous step, and also on top of the substrate.
  - Set the substrate bond pad thickness to 10 microns (0.010mm)

| **Substrate Bond Pad** <br> ![AEDT_Q3D_6.2](./docs/images/Lab2_PackageModeling_6.2.png) |
|:---|

### 5.4 - Wire Bond Creation and Material Assignment

  - **Step 7 : Create Bond Wires**
    - Use the **Bondwire tool** under: `Draw -> Bondwire`
    - Connect the centre of the Die Bond pad to the centre of the Substrate Bond Pad. It might be easier to draw the wires from the Top view orientation.
    - Select the Bondwire type as JEDEC 4-point
    - Assign gold as the Bondwire material

| **Draw the Bondwire connecting the die & substrate pad centers** <br> ![AEDT_Q3D_7.1](./docs/images/Lab2_PackageModeling_7.1.png) | ![AEDT_Q3D_7.2](./docs/images/Lab2_PackageModeling_7.2.png) |
|:---|:---|
| **Gold Bondwire** <br> ![AEDT_Q3D_7.3](./docs/images/Lab2_PackageModeling_7.3.png) |  |

Now, repeat the steps 6 and 7 to create and connect all the die and substrate bond pads using bondwires.

### 5.5 - Applying Mold Compound and Finalizing the Package Model

  - **Step 8 : Build the mold compound around the die**
    - Create a rectangular enclosure around the die and wires (5mm x 5mm, 1.2mm thickness)
    - Position at (-1, -1, -0.1) covering the top side of the substrate.
    - Set the thickness to 1.2mm so that it covers the die and the bondwires, while also leaving margin for any laser marking processes

| **Mold** <br> ![AEDT_Q3D_8.1](./docs/images/Lab2_PackageModeling_8.1.png) | ![AEDT_Q3D_8.2](./docs/images/Lab2_PackageModeling_8.2.png) |
|:---|:---|

_________________________________________________________________________________________________________  