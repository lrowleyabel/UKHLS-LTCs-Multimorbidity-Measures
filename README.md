# UKHLS Long-Term Health Conditions and Multimorbidity

This code produces indicators for a number of long-term health conditions as well as several standard measures of multimorbidity in the UK Household Longitudinal Study (UKHLS), the largest nationally representative panel study in the UK. Multimorbidity is a growing public health issue receiving large amounts of attention in the health research community and by sharing this code, we hope to facilitate standardised measurement of multimorbidity in this key longitudinal dataset.

This was produced by a team at the University of Edinburgh, as part of the project Artificial Intelligence and Multimorbidity: Clustering in Individuals, Space and Clinical Context (AIM-CISC), funded by National Institute for Health Research (NIHR) grant NIHR202639. The code was originally produced for the paper [Neighbourhood social cohesion, loneliness and multimorbidity: Evidence from a UK longitudinal panel study](https://doi.org/10.1016/j.healthplace.2025.103414). If you use this code, please cite the paper.

<br>
<p align="center">
  <img src="Assets/aim_cisc_logo.png" alt="AIM-CISC Logo" width="25%">
  <img src="https://img.spacergif.org/spacer.gif" width="40" height="1">
  <img src="Assets/nihr_logo.png" alt="NIHR Logo" width="40%">
</p>
<br><br>


## Details of Long-Term Health Conditions and Multimorbidity Variables

The code produces indicators of whether individuals have each of a set of long-term health conditions and various indicators of multimorbidity in Wave 10 of UKHLS. At this wave, respondents were asked whether a doctor or health professional had ever diagnosed them with certain conditions, the age at which they were diagnosed with the condition, and whether they still had the condition at the time of interview. Table 1 shows the generated health condition variables, grouped by body system (ICD-10 Chapter). In some cases, different names for the same condition or closely related conditions were asked about and so to avoid double-counting, these were grouped together as a single condition (indicated in brackets in Table1).


<table class="tg">
    <thead>
        <tr>
            <th class="tg-head" colspan="3">Table 1: Generated Long-Term Health Condition Variables</th>
        </tr>
        <tr>
            <th class="tg-subhead">ICD-10 Chapter</th>
            <th class="tg-subhead">Health Condition</th>
            <th class="tg-subhead">Generated Variable Name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="tg-0lax" rowspan="2">Respiratory system</td>
            <td class="tg-0lax">Asthma</td>
            <td class="tg-0lax"><code>asthma</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Chronic obstructive pulmonary disease (grouping of chronic obstructive pulmonary disease, emphysema and chronic bronchitis)</td>
            <td class="tg-0lax"><code>copd</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="4">Circulatory system</td>
            <td class="tg-0lax">Congestive heart failure</td>
            <td class="tg-0lax"><code>congestive_heart_failure</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Coronary heart disease (grouping of coronary heart disease, angina, heart attack or myocardial infarction)</td>
            <td class="tg-0lax"><code>coronary_heart_disease</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Stroke</td>
            <td class="tg-0lax"><code>stroke</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">High blood pressure/hypertension</td>
            <td class="tg-0lax"><code>hypertension</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="2">Endocrine, nutritional and metabolic</td>
            <td class="tg-0lax">Diabetes, excluding gestational diabetes (grouping of type 1 diabetes and type 2 diabetes)</td>
            <td class="tg-0lax"><code>diabetes</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Hypothyroidism or an under-active thyroid</td>
            <td class="tg-0lax"><code>hypothyroidism</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="2">Musculoskeletal system and connective tissue</td>
            <td class="tg-0lax">Osteoarthritis</td>
            <td class="tg-0lax"><code>osteoarthritis</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Rheumatoid arthritis</td>
            <td class="tg-0lax"><code>rheumatoid_arthritis</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="2">Nervous system</td>
            <td class="tg-0lax">Epilepsy</td>
            <td class="tg-0lax"><code>epilepsy</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Multiple Sclerosis</td>
            <td class="tg-0lax"><code>multiple_sclerosis</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Digestive system</td>
            <td class="tg-0lax">Any kind of liver condition</td>
            <td class="tg-0lax"><code>liver_condition</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="6">Neoplasms</td>
            <td class="tg-0lax">Bowel/colorectal cancer</td>
            <td class="tg-0lax"><code>bowel_colorectal_cancer</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Lung cancer</td>
            <td class="tg-0lax"><code>lung_cancer</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Breast cancer</td>
            <td class="tg-0lax"><code>breast_cancer</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Prostate cancer</td>
            <td class="tg-0lax"><code>prostate_cancer</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Liver cancer</td>
            <td class="tg-0lax"><code>liver_cancer</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Skin cancer or melanoma</td>
            <td class="tg-0lax"><code>skin_cancer_or_melanoma</code></td>
        </tr>
        <tr>
            <td class="tg-0lax" rowspan="6">Mental and behavioural disorders</td>
            <td class="tg-0lax">Anxiety</td>
            <td class="tg-0lax"><code>anxiety</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Depression</td>
            <td class="tg-0lax"><code>depression</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Psychosis or schizophrenia</td>
            <td class="tg-0lax"><code>psychosis_or_schizophrenia</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Bipolar disorder or manic depression</td>
            <td class="tg-0lax"><code>bipolar_disorder</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">An eating disorder</td>
            <td class="tg-0lax"><code>eating_disorder</code></td>
        </tr>
        <tr>
            <td class="tg-0lax">Post-traumatic stress disorder</td>
            <td class="tg-0lax"><code>post_traumatic_stress_disorder</code></td>
        </tr>
    </tbody>
</table>

We firstly calculated whether each of the above conditions were present for each individual, by checking whether they had ever been diagnosed with the condition and whether they reported still having the condition at the time of interview. Based on this, eight different binary indicators of multimorbidity were then generated, according to the criteria set out in Table 2. All of these variables are coded such that 0 = not multimorbid, 1 = multimorbid. Body systems are defined here as ICD-10 Chapters.


<table class="tg"><thead>
 <tr>
 <th class="tg-head" colspan="2">Table 2: Generated Multimorbidity Variables</th>
 </tr></thead>
<tbody>
 <tr>
 <th class="tg-subhead">Multimorbidity Criteria</td>
 <th class="tg-subhead">Generated Variable Name</td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has two or more long-term health conditions</td>
 <td class="tg-0lax"><code>mm</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has two or more long-term physical health conditions</td>
 <td class="tg-0lax"><code>p_mm</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has two or more long-term mental health conditions</td>
 <td class="tg-0lax"><code>m_mm</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has two or more long-term health conditions from two or more body systems</td>
 <td class="tg-0lax"><code>bs_mm</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has three or more long-term health conditions</td>
 <td class="tg-0lax"><code>mm3</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has three or more long-term physical health conditions</td>
 <td class="tg-0lax"><code>p_mm3</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has three or more long-term mental health conditions</td>
 <td class="tg-0lax"><code>m_mm3</code></td>
 </tr>
 <tr>
 <td class="tg-0lax">Respondent has three or more long-term health conditions from three or more body systems</td>
 <td class="tg-0lax"><code>bs_mm3</code></td>
 </tr>
</tbody></table>


Currently, the measures have only been produced for Wave 10 of UKHLS, however we hope in the future to develop similar code for other waves. Unfortunately, it is not as simple as applying the Wave 10 code to other waves, since the list of conditions being asked about differs at each wave, as well as the way in which the conditions were asked about.

## Details of UKHLS Health Condition Variables


In UKHLS, each health condition is assigned a health condition number (for example, 1 = asthma). There are two lists of health condition numbers - the first is a set of general health conditions, and the second is a list of more detailed conditions. The more detailed list contains subtypes of conditions that are asked about if respondents report having one of the more general conditions (for example, if a respondent says they have cancer, they will be asked whether they have breast cancer, skin cancer etc.). The more detailed list therefore contains all of the detailed subtypes, as well as any of the general conditions that do not have any subtype. If a condition is on both the general list and the more detailed list, it will generally have the same condition number on both lists (though there are some exceptions).

The way in which UKHLS records informaiton about each condition depends on whether they are a new respondent (i.e. this is their first interview) or a continuing respondent (i.e. they have been interviewed before). Details are provided below.

### Variables for new respondents:

For new respondents, the variables relating to health conditions are as below (where [x] represents the condition numbers):

<table class="tg">
    <thead>
        <!-- Title Row -->
        <tr class="tg-head">
            <th colspan="4">Table 3: Relevant UKHLS Variables for New Respondents</th>
        </tr>
        <!-- Column Headers -->
        <tr class="tg-subhead">
            <th>Variable name</th>
            <th>Description</th>
            <th>Substantive values</th>
            <th>Missing values</th>
        </tr>
    </thead>
    <tbody>
        <tr class="tg">
            <td><code>j_hcond[x]</code></td>
            <td>Has respondent ever been diagnosed with condition x (from general conditions list)?</td>
            <td>1 = Mentioned, 2 = Not mentioned</td>
            <td>inapplicable, proxy, refusal, don't know</td>
        </tr>
        <tr class="tg">
            <td><code>j_hcondcode[x]</code></td>
            <td>Has respondent ever been diagnosed with condition x (from detailed conditions list)?</td>
            <td>1 = Yes mentioned, 2 = Not mentioned</td>
            <td>inapplicable, proxy</td>
        </tr>
        <tr class="tg">
            <td><code>j_hconda[x]</code></td>
            <td>For any conditions with j_hcondcode[x] == 1, what age was the respondent diagnosed with condition x?</td>
            <td>Numeric</td>
            <td>inapplicable, proxy, don't know</td>
        </tr>
        <tr class="tg">
            <td><code>j_hconds[x]</code></td>
            <td>For any conditions with j_hcondcode[x] == 1, does the respondent still have the condition?</td>
            <td>1 = Yes, 2 = No</td>
            <td>inapplicable, proxy, don't know</td>
        </tr>
    </tbody>
</table>

Note that there is no j_hconds[x] for the following conditions, as it does not make sense to
talk about 'still' having the condition:

- 06 (heart attack)
- 07 (stroke)
- 19 (multiple scelrosis)

### Variables for continuing respondents:

For continuing respondents, the variables relating to health conditions are as below (where x is the condition number, and z is the index in a list of 1 to n, where n is the total number of conditions a respondent has).


<table class="tg">
    <thead>
        <!-- Title Row -->
        <tr class="tg-head">
            <th colspan="4">Table 4: Relevant UKHLS Variables for Continuing Respondents</th>
        </tr>
        <!-- Column Headers -->
        <tr class="tg-subhead">
            <th>Variable name</th>
            <th>Description</th>
            <th>Substantive values</th>
            <th>Missing values</th>
        </tr>
    </thead>
    <tbody>
        <tr class="tg">
            <td><code>j_hcondever[x]</code></td>
            <td>Has respondent ever been diagnosed with condition x (from general conditions list)?</td>
            <td>1 = Yes mentioned, 0 = Not mentioned</td>
            <td>inapplicable, proxy, refusal, don't know</td>
        </tr>
        <tr class="tg">
            <td><code>j_hcondncode[x]</code></td>
            <td>Has respondent ever been diagnosed with condition x (from detailed conditions list)?</td>
            <td>1 = Yes mentioned, 0 = Not mentioned</td>
            <td>inapplicable, proxy</td>
        </tr>
        <tr class="tg">
            <td><code>j_hcondno[z]</code></td>
            <td>What is the condition number for condition z? Where z is the index in a list of 1 to n, where n is the total number of conditions a respondent has.</td>
            <td>Condition numbers (value labels missing)</td>
            <td>inapplicable, proxy</td>
        </tr>
        <tr class="tg">
            <td><code>j_hcondna[z]</code></td>
            <td>What age was the respondent diagnosed with the condition that is recorded in j_hcondno[z]?</td>
            <td>Numeric</td>
            <td>missing, inapplicable, proxy, refusal, don't know</td>
        </tr>
        <tr class="tg">
            <td><code>j_hcondns[z]</code></td>
            <td>Does the respondent still have the condition that is recorded in j_hcondno[z]?</td>
            <td>1 = Yes, 2 = No</td>
            <td>missing, inapplicable, proxy, don't know</td>
        </tr>
    </tbody>
</table>

Note that the conditions "other arthritis", "other cancer", "other diabetes", "other emotional, nervous or psychiatric problem", and "other long-term/chronic condition" do not have variables indicating whether they still have the condition for continuing respondents. For this reason, these conditions are not included in the calculation of the multimorbidity variables.

## Further details

For further details on the list of conditions asked about at different waves and the questions asked to different types of respondents, see this [guide](Documents/FAQ_HCONDS_Changes_Waves_Description_20230214.pdf) and [spreadsheet](Documents/FAQ_HCOND_Changes_Waves_Table_20230214.xlsx) provided by UKHLS (note that this was draft documentation provided in response to a user request in 2023, so may not be fully up-to-date).
