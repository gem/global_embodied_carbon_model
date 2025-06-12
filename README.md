# 🌱 Global Embodied Carbon Model

<div align='center'>

<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Global_Earthquake_Model_Logo.png/440px-Global_Earthquake_Model_Logo.png" alt="GEM Foundation" width="300"/>
</p>

<a href='https://hazard.openquake.org/gem/'>
<img src='https://img.shields.io/badge/Global_Hazard_Model-green?style=for-the-badge'>
</a>

<a href='https://github.com/gem/global_vulnerability_model/'>
<img src='https://img.shields.io/badge/Global_Vulnerability_Model-gray?style=for-the-badge'>
</a>

<a href='https://github.com/gem/global_exposure_model'>
<img src='https://img.shields.io/badge/Global_Exposure_Model-orange?style=for-the-badge'>
</a>

<a href='LICENSE.txt'>
<img src='https://img.shields.io/badge/LICENSE-blue?style=for-the-badge'>
</a>

</div>

# ✨ Overview

> The first versions of the GEM's embodied-carbon exposure and seismic risk maps of Europe are now available! 🥳 🚀

This repository hosts data on the embodied carbon associated with the seismic damage repair and replacement of the residential, commercial, and industrial building stock worldwide. Interactive web services are accessible through the [🌐 EPOS Built Environmental Data service](https://embodiedcarbon.builtenvdata.eu).

# 🌍 Region, country and territory list

<p align="center">
  <img src="./World/World_Regions.png" alt="World regions" width="600">
</p>

The following regions, countries and territories are covered in this repository. 

| REGION                    | COUNTRIES AND TERRITORIES |
|---------------------------|---------------------------|
| Africa                    | Algeria, Angola, Benin, Botswana, Burkina_Faso, Burundi, Cameroon, Cape_Verde, Central_African_Republic, Chad, Comoros, Congo, Democratic_Republic_of_the_Congo, Djibouti, Egypt, Equatorial_Guinea, Eritrea, Eswatini, Ethiopia, Gabon, Gambia, Ghana, Guinea, Guinea_Bissau, Ivory_Coast, Kenya, Lesotho, Liberia, Libya, Madagascar, Malawi, Mali, Mauritania, Mauritius, Morocco, Mozambique, Namibia, Niger, Nigeria, Rwanda, Sao_Tome_and_Principe, Senegal, Seychelles, Sierra_Leone, Somalia, South_Africa, South_Sudan, Sudan, Tanzania, Togo, Tunisia, Uganda, Zambia, Zimbabwe |
| Caribbean_Central_America | Anguilla, Antigua_and_Barbuda, Aruba, Bahamas, Barbados, Belize, British_Virgin_Islands, Cayman_Islands, Costa_Rica, Cuba, Dominica, Dominican_Republic, El_Salvador, Grenada, Guadeloupe, Guatemala, Haiti, Honduras, Jamaica, Martinique, Montserrat, Nicaragua, Panama, Puerto_Rico, Saint_Kitts_and_Nevis, Saint_Lucia, Saint_Vincent_and_the_Grenadines, Trinidad_and_Tobago, Turks_and_Caicos_Islands, US_Virgin_Islands |
| Central_Asia              | Kazakhstan, Kyrgyzstan, Tajikistan, Turkmenistan, Uzbekistan |
| East_Asia                 | China, Hong_Kong, Japan, Macao, North_Korea, South_Korea, Taiwan |
| Europe                    | Albania, Andorra, Austria, Belarus, Belgium, Bosnia_and_Herzegovina, Bulgaria, Croatia, Cyprus, Czechia, Denmark, Estonia, Finland, France, Germany, Gibraltar, Greece, Hungary, Iceland, Ireland, Isle_of_Man, Italy, Kosovo, Latvia, Liechtenstein, Lithuania, Luxembourg, Malta, Moldova, Monaco, Montenegro, Netherlands, North_Macedonia, Norway, Poland, Portugal, Romania, Serbia, Slovakia, Slovenia, Spain, Sweden, Switzerland, Turkey, Ukraine, United_Kingdom |
| Middle_East               | Afghanistan, Armenia, Azerbaijan, Bahrain, Georgia, Iran, Iraq, Israel, Jordan, Kuwait, Lebanon, Oman, Pakistan, Palestine, Qatar, Saudi_Arabia, Syria, United_Arab_Emirates, Yemen |
| North_America             | Canada, Mexico, United_States_of_America |
| North_Asia                | Mongolia, Russia |
| Oceania                   | American_Samoa, Australia, Cook_Islands, Fiji, Guam, Kiribati, Marshall_Islands, Micronesia, Nauru, New_Caledonia, New_Zealand, Niue, Northern_Mariana_Islands, Palau, Papua_New_Guinea, Samoa, Solomon_Islands, Tonga, Tuvalu, Vanuatu |
| South_America             | Argentina, Bolivia, Brazil, Chile, Colombia, Ecuador, French_Guiana, Guyana, Paraguay, Peru, Suriname, Uruguay, Venezuela |
| South_Asia                | Afghanistan, Bangladesh, Bhutan, India, Nepal, Pakistan, Sri_Lanka |
| Southeast_Asia            | Brunei, Cambodia, Indonesia, Laos, Malaysia, Myanmar, Philippines, Singapore, Thailand, Timor_Leste, Vietnam |

# 🔎 Explanation of the content

## Regional repositories

Each regional repository contains the following folders and subfolders:

- 🚧 <span style="color: #7cf9d6"><b>Replacement_Embodied_Carbon</b></span>: This folder includes plots, maps and data on embodied carbon associated with replacing existing buildings with new constructions following destructive events (not necessarily earthquakes). It covers material production (modules A1- A3) and construction (modules A4-A5) of new structures, as well as end-of-life processes of existing damaged buildings.

	 The folder contains:

	 - 🧱 <span style="color: #7fccb6"><b>components</b></span>, including:

	    - <span style="color: #7fccb6"><b>carbon_class_mapping</b></span>: A CSV file that maps the existing building types to the carbon building classes of new constructions, reflecting whether a built back better (BBB) approach is followed. If BBB is only partially adopted in some countries of the region, an additional CSV file (Region_countries_bbb.csv) lists those specific countries
	    - <span style="color: #7fccb6"><b>structural</b></span>: CSV files providing quantities per built area and embodied carbon factors of key structural members, categorised by building type and occupancy
	    - <span style="color: #7fccb6"><b>non-structural</b></span>: CSV files providing quantities per built area and embodied carbon factors of key non-structural members, categorised by building type and occupancy

		    Each CSV file for structural and non-structural components contains the following columns:

		    - **NO**: Sequential number of the component
		    - **ITEM**: Type of structural or non-structural component
		    - **QUANTITY**: Quantity of component per built area (in square meters)
		    - **QUANTITY_UNITS**: Units for the quantity (e.g., cubic meters per square meter of built area)
		    - **EC**: Embodied carbon factor (in kg of CO<sub>2</sub>e) per embodied carbon unit (see EC_UNITS)
		    - **EC_UNITS**: Units for the embodied carbon factor (e.g., kg of CO<sub>2</sub>e per cubic meter of component)
		    - **MF**: Mass factor of component (kg per quantity unit). This is set to zero for components excluded from the total building mass calculation, where only structure and envelope are considered
			- **WR**: Waste factor indicating the share of material wasted during construction

	 - ☁️ <span style="color: #7fccb6"><b>embodied_carbon_factors</b></span>: This subfolder contains embodied carbon factors for various life-cycle modules (e.g., A1-A3, A4-A5) across different building types and occupancies, distinguishing between structural and non-structural components. It also includes summaries of replacement embodied carbon (REC) by building type, occupancy and country, and the embodied-carbon exposure map of the region. The Excel file "Region_Embodied_Carbon_Factors" compiles all component-level embodied carbon factors and data sources (e.g., EPD databases, scientific literature)

	  - 🏘️ <span style="color: #7fccb6"><b>exposure</b></span>: This subfolder provides aggregated REC values at the first subnational administrative level for each country in the region, including both structural and non-structural contributions and additional exposure attributes from GEM models (e.g., buildings, total replacement cost)

 - 🏚️ <span style="color: #7cf9d6"><b>Seismic_Embodied_Carbon</b></span>: This folder includes data on embodied carbon resulting from repair and reconstruction activities due to earthquake damage. It contains summaries of average annual embodied carbon (AAEC) for all countries in the region, and a regional embodied-carbon seismic risk map. The <span style="color: #7fccb6"><b>risk</b></span> subfolder contains the aggregated AAEC values at first subnational administrative level of each country in the region, broken down into structural and non-structural contributions.

## How is the embodied carbon of an individual building asset calculated?

The methodology is described in some detail in the dedicated [folder](https://github.com/gem/global_embodied_carbon_model/tree/revised_structure_new/methodology). For further details, refer to the publications listed below.

## Where can I find additional information on the defined building classes?

The building classes defined herein follow the GEM Taxonomy v3.2 convention. Please refer to the [GEM Taxonomy Glossary](https://taxonomy.openquake.org/) for additional details on taxonomy substrings and the `Taxonomy_tables_v3.2.xlsx` available [here](https://github.com/gem/gem_taxonomy/tree/master).

## Where can I find the models at the highest available resolution?

Please contact us at product@globalquakemodel.org.

# 📚 Publications

Martina Caruso, Vitor Silva, Karim Aljawhari, Al Mouayed Bellah Nafeh, Carmine Galasso. Unveiling the Environmental Impact of Earthquakes in Europe, 08 November 2024, PREPRINT (Version 1) available at Research Square [https://doi.org/10.21203/rs.3.rs-5283610/v1].

If you use the data or resources provided in this repository, please acknowledge the GEM Foundation as follows:
Global Earthquake Model (GEM) Foundation. Global Embodied Carbon Model. Available at: https://github.com/gem/global_embodied_carbon_model/tree/main.

# 👨‍👩‍👧‍👦 Related datasets and resources

Users interested in the global embodied carbon model might find the following GEM Foundation products useful:

* [Global Exposure Model](https://www.globalquakemodel.org/product/global-exposure-model)
* [Global Seismic Risk Map](https://www.globalquakemodel.org/products/global-seismic-risk-map)
* [Global Seismic Hazard Map](https://www.globalquakemodel.org/product/global-seismic-hazard-map)
* [Global Vulnerability Model](https://www.globalquakemodel.org/product/global-vulnerability-model)
* [OpenQuake engine](https://www.globalquakemodel.org/product/openquake-engine)

# 🛡 License
[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa], which requires:

* Attribution (you must give appropriate credit, provide a link to the license, and indicate if changes were made)
* Non-commercial (you may not use the material for commercial purposes)
* ShareAlike (derivatives created must be made available under the same license as the original)

If your use case deviates from the requirements of the offered license, but still want to explore the use of the data, please contact us at license@globalquakemodel.org.

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg

If your intended use falls outside the scope of this license, please contact us at license@globalquakemodel.org to explore possible arrangements.
Note: Any use that deviates from these terms constitutes a license violation. For commercial use, a tailored license agreement must be established, please contact us at product@globalquakemodel.org.

# ⚠️ Disclaimer

This model represents the best publicly available information. While efforts have been made to ensure accuracy and usability, the authors assume no liability and offer no warranty for the information provided herein. All responsibility for use of the data rests with the user.
