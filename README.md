# Computer Science Course Access in Oregon

In this project, I intend to explore the likelihood of offering computer science courses associated with geographic distance to technology hubs among Oregon high schools.

## Data Source

My primary data source is the Civil Rights Data Collection (CRDC). The data system is built on a biennial federal survey administered by the U.S. Department of Education’s Office of Civil Rights. For this study, I drew on information from the 2021-2022 school year. The downloaded dataset includes school enrollment, the raw count of computer science courses, and school instruction type. Another data source for this analysis is the 2022 Common Core of Data (CCD). It is the Department of Education’s primary database on U.S. public elementary and secondary schools. I derive school-level characteristics from this data, including enrollment, locale classification, socioeconomic status (identified by eligibility for Free/Reduced Price Lunch), and school geographic coordinates.

## Analytic Sample and Summary Statistics

My analytic sample focuses on school enrollment in the 2021-2022 academic year because these are the most up-to-date datasets and reflect a post-COVID pandemic recovery period, when most schools had returned to in-person instruction. Given the study’s narrowed focus, I restrict my sample to school-level observations of Oregon. Although CRDC data are from the 2021-22 academic year, CCD data are from 2022. This accommodation is due to the lack of Free/Reduced Price Lunch (FRPL) information, as CCD data were collected in 2021 when the collection process was disrupted during the pandemic.

I merged CRDC and CCD data using the National Center for Education Statistics (NCES) school identifiers as the unique key and applied a systematic filter to include schools that served grades 9 through 12 and were categorized as non-virtual, non-alternative, and non-juvenile-justice institutions. The completed dataset consists of 325 Oregon public high schools. For the subsequent analysis, I restricted the sample to schools with geographic locale, location coordinates, FRPL, and student enrollment. Thus, my main analytic sample is narrowed down to 264 high schools in Oregon.

###  *Outcome Variable*

The key dependent variable in this study is a dichotomous outcome, whether schools offer CS courses. Schools reported having at least 1 CS course are coded as 1, else 0.

###  *Predictor Variable*

The primary predictor of interest in this study is the school’s distance to the nearest technology hubs. To construct this variable, I first obtained the geographic coordinates of Portland, Salem, and Corvallis because these three cities are the home of three tech centers recognized at both the state and federal levels (Business Oregon, 2026; U.S. Economic Development Administration, 2023). The coordinates of each city were retrieved from Google Maps, using the city center coordinates as the representative point for each tech hub. I calculated distance using the haversine formula, which accounts for Earth’s spherical shape when computing great-circle distances between geographical points (Robusto, 1957). This process produced distance variables representing each school’s proximity to every technology hub, from which I obtain the primary predictor variable: the distance from each school to the nearest of the three technology hubs.
