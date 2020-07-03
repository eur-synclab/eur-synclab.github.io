# When can I share my data and with whom?

Whether you can share your research data with others depends on:
1. The anonymity of your data
2. Who owns your data
3. The infrastructure available to share the data

In this chapter, we will go into nr. 1 and talk about the EU privacy law: the General Data Protection Regulation.

## The GDPR
Since May 2018, the General Data Protection Regulation (Dutch: Algemene Verordening Gegevensbescherming [AVG]) has been in place to better protect personal data. The most important aspects of the GDPR are:

- *Privacy by Design*: build privacy-increasing measures into your study design
- *Privacy by Default*: make sure your default settings already improve your participants' privacy
- *Data minimization*: Only collect and use personal data necessary for your research goal
- *Legal basis*: Make sure there is a legal basis (6 possible) to process (and share) the personal data you collect (e.g., informed consent or public interest [more info (Dutch)](https://autoriteitpersoonsgegevens.nl/nl/onderwerpen/algemene-informatie-avg/mag-u-persoonsgegevens-verwerken)
- *DPIA*: Conduct a Data Protection Impact Assessment whenever you collect (highly) sensitive data, such as names, addresses, race or health data.
- Inform participants about the goal of the personal data collection and which data you collect.

## What is personal data?
Data is personal when you can identify someone by it, either directly (e.g., name, address) *or* indirectly (e.g., height, job, income, education). Indirect indicators are personal data if they can identify someone:

- when it concerns an extreme case (e.g., someone 2.20m tall)
- when combining data so that they can only be applicable to one person (NB. this can also concern publicly available data)
- when re-identification is still possible (e.g., with a name-number key conversion file)

By law, data is considered identifiable when identification can occur with reasonable (proportionate) effort. Thus, it is **not** about the *hypothetical* possibility that data can be linked or combined.  Because not everyone has access to the same data, the definition of "identifiable" may differ per situation.

## Important types of data
- **Pseudonymous data**: Data that is only identifiable with a key (that still exists). This is the case when after encryption, it is still possible to identify someone, e.g., because the key or the source data still exist. Pseudonymous data are still considered **personal data**, because the encryption is **reversible**, thus requiring a legal basis for processing.
- **Special personal data**: special sensitive categories of personal data that may be difficult to anonymize, they require additional measures: 
  - race or ethnic descent
  - political views
  - religion
  - union membership
  - genetic or biometric data aimed at unique identification
  - health data
  - sexual life and preference
  - criminal records
  - in the Netherlands: Burgerservicenummer (BSN)
- **Anonymous data**: Data that are **not** (re)identifiable anymore: neiher by a name-number key, nor by combining with other publicly available data. Anonymous data are **not considered personal data**, so processing and sharing this kind of data do not require a legal basis.

## Sharing data under the GDPR
Anonymous data can be shared without restriction if they are **really** anonymous. You may share non-anonymous data only when:

- You have attained explicit informed consent from the participant to do so (most used legal basis). For special personal data, this consent should be *very explicit* ("I agree to share x, y and z" with A, B and C): there cannot be any doubt about this. See some [example sentences](https://www.uu.nl/en/research/research-data-management/guides/informed-consent-for-data-sharing) and a [GDPR version of the Open Brain Consent initiative](https://open-brain-consent.readthedocs.io/en/latest/gdpr/ultimate_gdpr.html)
- You reduce the amount of personal data shared to a minimum (data minimization principle)
- You take the necessary measures to protect your participants' privacy
- Always write a Data Management Plan (DMP) and  Data Protection Impact Assessment (DPIA) before starting a project with personal data
- When sharing data with researchers outside of the EU, Norway, Liechtenstein and Iceland (no GDPR present), make sure that country has an [adequacy decision](https://ec.europa.eu/info/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en). If the country does not have one, you need to take extra protection measures, such as standard contractual clauses or agreements.

In case your data are not anonymous, but you have attained consent and still want to protect your participants' privacy better, you may always use a **data sharing agreement**. This document contains what users can and cannot do with your data, for how long and if you will get credit if the user publishes about your data. A good example is the agreement used by [the Donders repository](https://data.donders.ru.nl/?2). The Open Brain Consent initiative is also working on a [template agreement](https://open-brain-consent.readthedocs.io/en/latest/gdpr/data_user_agreement.html), or  find an example template in the [template chapter](dsa-template.md).

## Anonymizing data
### General tips
- Remove identifiers (name, address)
- Replace identifiers (e.g., date of birth by age or age groups)
- Use pseudonyms (e.g., participant numbers)
- Randomize the pseudonyms (participant numbers)
- Use only the middle range of the data: extreme cases may lead to identification because by definition, there are only few of them
- Remove the name-participant number key
- Plan how to anonymize the data up front and keep a log of your procedures
- Store original data in a safe location
- Determine whether different measures combined could lead to identification. If needed, consult a privacy officer.

### Deidentifying MRI-data
There is some debate as to whether or not MRI data can be anonymized. One paper, for example, found that brain morphology, although preprocessed, was personally identifiable ([Takao, Hayashi, & Ohtomo, 2015](https://doi.org/10.1016/j.mri.2015.03.010)). Moreover, it could be argued that, when combining multiple databases, the data may be identifiable in that way as well. Therefore, we do not speak of anonymizing MRI-data, but *deidentifying* it: MRI-data will always remain *pseudonymous at best* and therefore require a legal basis before sharing.

- Anonymize the filenames: replace names with codes
- [Remove the header information](https://loni.usc.edu/research/software?name=DiD ) (when using hdr and img files, not for nifti files)
- Deface the MRI-scans if your software does not do that automatically already. We recommend using [pydeface](https://pypi.org/project/pydeface/), which is implemented in [bidsify](https://github.com/NILAB-UvA/bidsify)

If you are uncertain whether your data are anonymous, please don't hesitate to contact a privacy officer.

Have a look at [this MRI data sharing guide](https://doi.org/10.5281/zenodo.3822290) for more info!

## GDPR resources
- [Open Brain Consent initiative](https://open-brain-consent.readthedocs.io/en/stable/), a bottom-up initiative to make sense of the GDPR in sharing MRI data
- Stephan Heunis's (TU Eindhoven) [GDPR summary doc](https://docs.google.com/document/d/1Mfbl4DZAw7MRPjSxIiM5sfYU4gX-pcghgj5M1qb84jg/edit?usp=sharing)
- Course about [privacy in research](https://maken.wikiwijs.nl/125518/Privacy_in__Researc)
- [Privacy dos and donts](https://www.edugroepen.nl/sites/RDM_platform/RDM_Blog/SiteAssets/Presentatie%20Jacques_Flores_UU.pdf)
- [Guide for sensitive data](https://www.openaire.eu/sensitive-data-guide)
- UU guides for [handling personal data](https://www.uu.nl/en/research/research-data-management/guides/handling-personal-data) and [informed consent](https://www.uu.nl/en/research/research-data-management/guides/informed-consent-for-data-sharing)
- [Legal instruments protecting data (agreements)](https://www.uu.nl/en/research/research-data-management/guides/legal-instruments-and-agreements)

## Erasmus University contacts
- Privacy office ESSB: privacy@essb.eur.nl
  - Priscilla van Berkel: priscilla.vanberkel@eur.nl
- Legal counsel: Renee Hanegraaf: hanegraaf@eur.nl
- Research support: Geert van den Hoek: vandenhoek@eur.nl
- Information manager ESSB: Andre Cheung Tam He: cheungtamhe@eur.nl

See all support staff [here](https://my.eur.nl/en/essb-employee/contact/team-overview-support-staff-essb)
