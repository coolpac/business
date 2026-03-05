# Competitive Landscape Research: Sanctions Screening, Compliance Data & Trade Data APIs

*Research date: March 2026*

---

## PART 1: SANCTIONS SCREENING, PEP LISTS & COMPLIANCE DATA APIs

---

### 1. MAJOR ESTABLISHED PROVIDERS

#### 1.1 Dow Jones Risk & Compliance (News Corp)
- **URL:** https://www.dowjones.com/professional/risk/
- **Pricing:** Custom quote only. Vendr.com benchmarks show Dow Jones software contracts ranging from ~$2,300 to ~$564,000/year depending on scope. Risk & Compliance specifically is enterprise-priced; expect $50K-$200K+/year for mid-to-large institutions.
- **Coverage:** Global sanctions lists, PEPs, adverse media (via Factiva), state-owned enterprises, special interest persons. One of the most comprehensive editorial-curated datasets.
- **API Quality:** REST API available. Integrates with cXchange, KYC Portal, OneTrust, RegTechONE, and others. Well-documented but enterprise-gated.
- **Weaknesses:** Opaque pricing, long sales cycles, expensive for SMBs/startups. Data is editorially curated (high quality but slower updates vs. automated systems). Lock-in via annual contracts.

#### 1.2 LSEG World-Check (formerly Refinitiv/Thomson Reuters)
- **URL:** https://www.lseg.com/en/risk-intelligence/screening-solutions/world-check-kyc-screening
- **API Docs:** https://docs-developers.refinitiv.com/
- **Pricing:** Points-based system. Tiered packages: entry-level ~3,000 screens/year, higher tier ~5,556 screens/year. Enterprise pricing is custom-quoted. Estimated $30K-$300K+/year depending on volume and modules. Online exclusive packages available via self-serve.
- **Coverage:** 4.9M+ structured risk profiles. Sanctions, PEPs (with hierarchical links), adverse media (AI-powered "Media Check"), state-owned enterprises. 240+ countries/territories.
- **API Quality:** REST/JSON API. Zero Footprint Screening (ZFS) option for privacy-sensitive use cases. Mature, well-documented.
- **Weaknesses:** Expensive, especially Enhanced Due Diligence (EDD). Points-based pricing is confusing. Part of LSEG bureaucracy post-acquisition. Data breach in 2023 exposed World-Check database.

#### 1.3 ComplyAdvantage
- **URL:** https://complyadvantage.com/
- **Pricing Page:** https://complyadvantage.com/pricing/
- **Pricing:** Not publicly listed. Volume-based. "ComplyLaunch" = 12 months free for early-stage fintechs. Starter plan available. Enterprise plans custom-quoted. Industry estimates suggest $15K-$100K+/year depending on volume.
- **Coverage:** 60+ sanctions jurisdictions (OFAC, EU, HMT, etc.), PEPs with hierarchical links, adverse media across 200+ countries. AI-driven data aggregation from 10,000+ sources. Updated in near-real-time.
- **API Quality:** Excellent. Modular REST API ("ComplyAdvantage Mesh"). Cloud-native, API-first design. SOC 2 Type II, ISO 27001 certified. Can operate as full compliance stack or component.
- **Weaknesses:** Still relatively newer brand vs. Dow Jones/World-Check, which can be a barrier with conservative compliance committees. Not as deep on editorial curation. Pricing opaque despite marketing as "transparent."

#### 1.4 Sanctionssearch.com (Simplified.ID)
- **URL:** https://www.sanctionssearch.com/
- **Pricing:** Very transparent and affordable:
  - Annual membership: GBP 90/year (+VAT)
  - Individual sanctions search: GBP 0.10/search (min bundle of 100)
  - Company search: GBP 0.30/search
  - PEP screening: GBP 0.40/search
  - Enhanced multi-source PEP search: GBP 0.60/search
  - Comprehensive company search: GBP 5.00/search
  - Automatic company monitoring: GBP 50.00/year
- **Coverage:** UK-focused but covers global sanctions lists. Good for UK-regulated entities (law firms, accountants, estate agents).
- **API Quality:** API available for bulk screening. PAYG, SME, and Enterprise tiers.
- **Weaknesses:** Primarily UK market. Less depth than Dow Jones/World-Check on global PEP coverage. Limited brand recognition outside UK.

#### 1.5 OpenSanctions
- **URL:** https://www.opensanctions.org/
- **GitHub:** https://github.com/opensanctions/opensanctions
- **API:** https://api.opensanctions.org/
- **Pricing:**
  - Free for non-commercial use (CC-BY-NC license)
  - SaaS API: EUR 0.10/successful API call, volume discounts above 20K requests/month
  - Bulk data licensing: Custom-quoted (described as "about one engineering day per month" in cost)
  - Financial services flat-rate available
  - Discounts for startups, free for journalists/activists
  - 30-day trial API key available
- **Coverage:** 330+ global sources. Sanctions, PEPs, entities of criminal interest. Aggregates OFAC, EU, UN, UK, plus many smaller jurisdictions. Uses "Follow the Money" (FtM) data model.
- **API Quality:** REST API via "yente" matching engine. Can self-host on own infrastructure. JSON and tabular formats. Daily updates.
- **Weaknesses:** No editorial curation — automated crawlers only. Deduplication quality varies. Not a "compliance-approved" vendor in the way Dow Jones/World-Check are (some regulators/auditors may push back). No built-in case management or workflow tools.

---

### 2. FREE GOVERNMENT SOURCES

#### 2.1 OFAC SDN List (US Treasury)
- **URL:** https://ofac.treasury.gov/sanctions-list-service
- **Search Tool:** https://sanctionssearch.ofac.treas.gov/
- **Formats:** XML, CSV, fixed-field, delimited. Delta/change files available.
- **Cost:** Completely free
- **Coverage:** US sanctions — Specially Designated Nationals (SDN) list + Consolidated (non-SDN) list
- **Update frequency:** As changes occur (usually within hours of designation)
- **Limitations:** US sanctions only. No PEP data. No adverse media. No fuzzy matching API — just raw data files. You must build your own screening engine. No entity resolution.

#### 2.2 EU Consolidated Financial Sanctions List
- **URL:** https://data.europa.eu/data/datasets/consolidated-list-of-persons-groups-and-entities-subject-to-eu-financial-sanctions
- **Sanctions Map:** https://www.sanctionsmap.eu/
- **Sanctions Tracker:** https://data.europa.eu/apps/eusanctionstracker/
- **Formats:** XML, CSV, PDF
- **Cost:** Free
- **Coverage:** All persons, groups, and entities subject to EU asset freezes
- **Limitations:** EU sanctions only. Published in password-protected area (but generated download links work programmatically). No PEP data. No fuzzy matching.

#### 2.3 UN Security Council Consolidated List
- **URL:** https://main.un.org/securitycouncil/en/content/un-sc-consolidated-list
- **Formats:** XML, HTML, PDF
- **Cost:** Free
- **Coverage:** UN Security Council sanctions designations (Taliban, ISIL/Da'esh, etc.)
- **Update frequency:** As resolutions are passed
- **Limitations:** UN sanctions only (subset of most national lists). No PEP data. No matching engine.

#### 2.4 UK HM Treasury Sanctions List (OFSI)
- **URL:** https://www.gov.uk/government/publications/financial-sanctions-consolidated-list-of-targets
- **Formats:** XML, CSV, ODS
- **Cost:** Free
- **Coverage:** UK financial sanctions targets
- **Limitations:** UK only.

**Key takeaway on free sources:** The raw data is available but you must build your own: fuzzy name matching, transliteration handling, entity resolution, deduplication, and screening workflow. This is why commercial providers exist — the value-add is in the matching engine, data normalization, and workflow, not the raw list data.

---

### 3. ANNUAL COST BENCHMARKS

| Buyer Segment | Typical Annual Spend | Notes |
|---|---|---|
| Small fintech / startup (<50 employees) | $5K - $30K/year | Often start with ComplyAdvantage Starter or OpenSanctions |
| Mid-size bank / payment company | $50K - $200K/year | Dow Jones or World-Check, often bundled with other compliance tools |
| Large bank / global institution | $200K - $2M+/year | Multiple vendors, enterprise licenses, custom integrations |
| Crypto exchange / neobank | $15K - $100K/year | High transaction volume screening drives cost |

**Industry-wide spending:**
- Banks allocate 2.9% to 8.7% of non-interest expenses to compliance
- UK banks/fintechs spend GBP 38.3 billion/year collectively on financial crime compliance
- 98-99% of financial institutions reported compliance cost increases in 2023
- Compliance costs have increased 60%+ vs. pre-2008 levels (Deloitte)
- AI adoption projected to save US institutions $23.4 billion (Napier AI forecast)

---

### 4. NEWER / CHEAPER ALTERNATIVES & STARTUPS

| Provider | Pricing | Key Differentiator |
|---|---|---|
| **Dilisense** (dilisense.com) | From EUR 0.01/screening | Cheapest per-screening cost. 80+ sanction lists. REST API + downloadable database. |
| **sanctions.io** (sanctions.io) | From $899/5,000 API calls (~$0.18/call). Enterprise: 25K+ monthly volume, custom pricing | 350ms avg response time, 99.99%+ uptime SLA. Batch screening up to 10K records/request. |
| **NameScan** (namescan.io) | $0.48-$1.80/scan depending on volume (50-2000 scan packages) | PAYG model, no contracts. White-label available. |
| **Sanction Scanner** (sanctionscanner.com) | Custom-quoted subscription | Turkish startup, good transaction monitoring. AML suite beyond just screening. |
| **sanctions.network** | Free | Open-source JSON API against OFAC, UN, EU lists. No PEP data. |
| **Castellum.AI** (castellum.ai) | Free sample (20K designations, static). Commercial: custom | Updates every 5 minutes. Also covers export controls. |
| **Sumsub** (sumsub.com) | Usage-based tiered | Full KYC/AML platform, not just screening. Identity verification + sanctions. |
| **Ondato** (ondato.com) | Scalable plans | AI "Rangers" for sanctions/PEP/adverse media. 30-second reports. |
| **Lucinity** (lucinity.com) | Custom | Icelandic RegTech. "Augmented intelligence" approach. Strong UX. |
| **Beam Solutions** | Budget-friendly | Lightweight AML tool specifically for startups. |
| **Compliancely** (compliancely.com) | API-first, contact for pricing | No-code portal + scalable APIs. Tax + sanctions + identity. |
| **Flagright** (flagright.com) | Contact for pricing | API-first AML platform. Real-time transaction monitoring. |

---

### 5. OPEN-SOURCE ALTERNATIVES

#### 5.1 OpenSanctions Ecosystem (Primary)
- **opensanctions** — Main data pipeline: https://github.com/opensanctions/opensanctions
- **yente** — Self-hosted entity matching/screening API: https://github.com/opensanctions/yente
- **followthemoney** — Data model + tooling for entity/relationship data
- **rigour** — Data cleaning/normalization (names, territories, etc.)
- **zavod** — Data pipeline orchestration toolkit
- **nomenklatura** — Entity data integration with full lineage tracking

This is the most complete open-source sanctions screening stack available. You can self-host yente + OpenSanctions data for a fully on-premise screening solution (still requires commercial license for business use of the data).

#### 5.2 sanctions.network
- **URL:** https://sanctions.network/
- Free, open-source JSON API against OFAC SDN, UN SC, and EU FSF lists
- Uses PostgREST for auto-generated API
- Very basic — no PEP data, limited matching sophistication

#### 5.3 DIY with Government Data
- Download OFAC XML + EU XML + UN XML
- Build own matching engine (fuzzy matching, transliteration)
- Significant engineering effort (3-6 months to build, ongoing maintenance)
- Used by some large banks with dedicated compliance engineering teams

---

### 6. BENEFICIAL OWNERSHIP REGISTRIES WORLDWIDE

#### 6.1 UK — People with Significant Control (PSC) Register
- **API:** https://developer.company-information.service.gov.uk/
- **Bulk Data:** https://download.companieshouse.gov.uk/en_pscdata.html
- **Cost:** Completely free. No subscription, no per-call charges. Just register for API key.
- **Coverage:** All UK companies must declare persons with 25%+ ownership/voting rights
- **Formats:** REST API + bulk CSV/JSON download + streaming API for real-time changes
- **Launched:** 2016 — first publicly accessible beneficial ownership register in G20
- **Limitations:** Only direct declarations. 25% threshold leaves gaps. No multi-layer corporate chain tracing. Overseas entities register is newer and less complete.

#### 6.2 EU — AMLD Requirements & BORIS
- **5th AMLD (2018):** Required public access to beneficial ownership registers. Invalidated by CJEU in Nov 2022 on privacy grounds.
- **6th AMLD (in progress):** New framework for access to beneficial ownership info.
- **BORIS:** Beneficial Ownership Registers Interconnection System — links national central registers across EU member states: https://e-justice.europa.eu/topics/registers-business-insolvency-land/beneficial-ownership-registers-interconnection-system-boris_en
- **UBO Atlas:** Overview of UBO registers across EU: https://uboatlas.eu/
- **Status:** Fragmented. Each member state has own register with varying access levels. Post-CJEU ruling, many registers restricted public access. Access now generally limited to obliged entities, FIUs, and those demonstrating "legitimate interest."

#### 6.3 United States — Corporate Transparency Act (CTA)
- **Agency:** FinCEN (Financial Crimes Enforcement Network)
- **Status:** Beneficial Ownership Information (BOI) reporting requirements enacted. FinCEN building registry. Not publicly accessible — available to law enforcement, financial institutions with consent, and regulators.
- **Note:** Implementation has faced legal challenges and delays.

#### 6.4 Other Countries
| Country | Status | Public Access |
|---|---|---|
| **Singapore** | ACRA central register since July 2020 | Law enforcement only |
| **UAE** | Cabinet Resolution No.58/2020, register required | Limited |
| **Australia** | Public registry planned (consultation phase) | Not yet live |
| **South Africa** | Amendments to Trust Property Control Act + Companies Act | In development |
| **UK Overseas Territories** | Required to have registers | Varies |

**Open Ownership** maintains the definitive global map of beneficial ownership transparency: https://www.openownership.org/en/map/

---

### 7. WHO BUYS THIS?

| Buyer Segment | Use Cases | Budget Range |
|---|---|---|
| **Banks (retail & commercial)** | KYC, CDD, EDD, transaction screening, correspondent banking | $100K - $2M+/year |
| **Payment companies / PSPs** | Real-time transaction screening, customer onboarding | $20K - $200K/year |
| **Fintechs / Neobanks** | KYC onboarding, ongoing monitoring, regulatory requirement | $5K - $100K/year |
| **Crypto exchanges / DeFi platforms** | Travel Rule compliance, wallet screening, token listing due diligence | $15K - $150K/year |
| **Insurance companies** | Policyholder screening, claims fraud | $30K - $200K/year |
| **Law firms** | Client due diligence (CDD), conflict checks | $5K - $50K/year |
| **Accounting firms** | AML obligations under 4th/5th AMLD, client screening | $2K - $30K/year |
| **Real estate agents** | AML obligations in many jurisdictions | $1K - $10K/year |
| **Corporates (trade/export)** | Sanctions screening for trade compliance, denied party screening | $10K - $100K/year |
| **Gaming / gambling companies** | Player verification, sanctions screening | $10K - $50K/year |
| **Compliance consultancies** | Reselling screening as a service to clients | $5K - $50K/year |

**Key buyer personas:**
- Chief Compliance Officer (CCO)
- Money Laundering Reporting Officer (MLRO)
- Head of Financial Crime
- KYC/AML Operations Manager
- Compliance Analyst / Associate
- Chief Risk Officer (CRO)

---

## PART 2: IMPORT/EXPORT & CUSTOMS DATA APIs

---

### 8. MAJOR TRADE DATA PROVIDERS

#### 8.1 ImportGenius
- **URL:** https://www.importgenius.com/
- **Pricing Page:** https://www.importgenius.com/pricing
- **Pricing:**
  - Essentials: ~$149/month (12 months US import data, limited searches)
  - USA Pro: ~$249/month (US data from 2006+, higher limits, AI features)
  - American Pro / North American Pro / Global Pro: Available via sales
  - Enterprise: Custom (25+ countries, unlimited searches, dedicated research team)
  - Annual plans save up to 36%
  - API access: Enterprise-grade, contact sales
- **Coverage:** 2+ billion shipment records, 23+ countries, US data updated daily
- **Strengths:** Transparent pricing, daily US updates, built-in analytics, route maps, trend charts
- **Weaknesses:** API only at enterprise tier. Annual contract lock-in for Business/Enterprise plans. Limited customization.

#### 8.2 Panjiva (S&P Global Market Intelligence)
- **URL:** https://panjiva.com/
- **Pricing:** Not public. Custom quotes. Industry estimates: $1,000-$3,000+/month. Part of S&P Global's broader market intelligence portfolio.
- **Coverage:** 2+ billion shipment records from 22 customs sources. Primarily: US, Brazil, India, Pakistan, Vietnam, Chile, Colombia, Costa Rica, Ecuador, Panama, Paraguay, Peru, Uruguay, Venezuela.
- **API:** Robust API for system integration. Structured, standardized datasets.
- **Strengths:** Part of S&P Global ecosystem (can bundle with PIERS, credit data, etc.). Excellent data standardization. Long-term trade analysis.
- **Weaknesses:** Expensive. Opaque pricing. Part of larger S&P bureaucracy.

#### 8.3 S&P Global PIERS
- **URL:** https://www.spglobal.com/market-intelligence/en/solutions/products/piers
- **Coverage:** 40+ years of US waterborne trade data. 100% US port coverage. 16M+ bills of lading processed in 2023. 2B+ data fields. 18 international markets. Trade statistics for 144+ countries.
- **Pricing:** Enterprise, custom-quoted. Likely $2K-$5K+/month.
- **Strengths:** Gold standard for US maritime import/export data. Deepest historical dataset. Bill-of-lading-level granularity.
- **Weaknesses:** Expensive. US maritime focus — less coverage of air/land transport or non-US markets.

#### 8.4 Descartes Datamyne
- **URL:** https://www.datamyne.com/
- **API:** https://www.datamyne.com/our-product/global-trade-data-api/
- **Pricing:** Not public. Free trial available (no credit card). Custom packages with specialized data fields.
- **Coverage:** 230 markets across 5 continents. 75-85% of world import/export trade by value. 500M+ shipment records added/year. US maritime imports refreshed daily with master + house BOL data (24hr after receipt from CBP).
- **API Quality:** REST API connecting business systems. Produces trade summaries, trends, interactive maps. Integrates with CRM/ERP.
- **Strengths:** Largest searchable trade database. Excellent global coverage. Strong API.
- **Weaknesses:** Expensive. No public pricing. Part of Descartes Systems Group (logistics software company — may bundle).

#### 8.5 TradeInt (Trade Intelligence Global)
- **URL:** https://www.tradeint.com/
- **Pricing Page:** https://www.tradeint.com/product/pricing (contact for details)
- **Coverage:** Claims 95% of worldwide trade flows. 8+ billion global trade records. 400M+ companies. Bill of lading data.
- **Founded:** 2018, Singapore
- **API:** Does NOT currently offer an API. May add in future.
- **Strengths:** Broad coverage claim. AI/ML for data standardization.
- **Weaknesses:** No API (major limitation). Mixed reviews — reports of poor customer service, hard-to-use portal, no-refund policy. Relatively new/unproven vs. Panjiva/Datamyne.

#### 8.6 ImportKey
- **URL:** https://importkey.com/
- **Pricing:** https://importkey.com/pricing — Startup plan ~$25-30/month (pricing shown in INR: ~INR 2,159/month), Business plan ~$40-45/month (~INR 3,599/month)
- **Coverage:** US import/export data from 2008+, updated daily
- **API:** Limited. API page exists but reviews suggest "APIs Available: No."
- **Strengths:** Very affordable. Good for basic US BOL lookups. AI-driven product/buyer/seller identification.
- **Weaknesses:** Very limited API. Primarily US-only. Basic compared to Panjiva/Datamyne. "A bit pricey" for what you get (per some reviews, though objectively cheap).

---

### 9. BILLS OF LADING DATA

#### Availability:
US bills of lading are public record (filed with CBP/Customs and Border Protection via the Automated Commercial Environment/ACE system). This is why US trade data is the most available.

Most other countries do NOT make BOL data public. Notable exceptions with some level of availability: India, Brazil, Vietnam, Pakistan, Colombia, Ecuador, Chile, Peru, Paraguay, Uruguay.

#### Key BOL Data Providers:
| Provider | Coverage | Update Frequency | API |
|---|---|---|---|
| S&P PIERS | US + 18 intl markets | Daily (US) | Yes |
| Descartes Datamyne | 230 markets | Daily (US) | Yes |
| ImportGenius | 23+ countries | Daily (US) | Enterprise only |
| Panjiva | 22 customs sources | Varies | Yes |
| ManifestDB (manifestdb.com) | 65+ countries, 600M+ TEUs | Daily | Yes |
| OEC (oec.world) | US CBP data | Frequent | Premium API |
| ImportKey | US | Daily | Limited |
| billofladingdata.com | US | Varies | From $79 |

#### Common BOL Data Fields:
- Shipper/consignee names and addresses
- Goods description, weight, volume, packaging
- HS/HTS codes
- Port of origin and destination
- Vessel name and carrier
- Container numbers and TEU counts
- Arrival/departure dates

---

### 10. HS CODE DATABASES

#### Free Sources:
| Source | URL | Format | Notes |
|---|---|---|---|
| **GitHub (UN Comtrade sourced)** | https://github.com/datasets/harmonized-system | CSV data package | HS nomenclature from UN Comtrade |
| **GitHub (WCO sourced)** | https://github.com/warrantgroup/WCO-HS-Codes | CSV | WCO HS codes as CSV |
| **US Harmonized Tariff Schedule** | https://hts.usitc.gov/ | Online + downloadable | US-specific HTS (10-digit) |
| **WTO Tariff Download Facility** | https://www.wto.org/english/tratop_e/tariffs_e/database_explanation_e.htm | Excel, XML, CSV | Tariff data across countries |
| **UN Comtrade** | https://comtrade.un.org/ | API + download | HS classification data alongside trade flows |

#### Paid Sources:
| Source | URL | Notes |
|---|---|---|
| **WCO Official HS Database** | http://harmonizedsystem.wcoomdpublications.org/ | Official WCO database. Paid subscription required. |
| **RapidAPI HS Code API** | https://rapidapi.com/appcon-software-appcon-software-default/api/hs-code-harmonized-system | API for HS code lookup. Freemium. |
| **WCO Trade Tools** | https://www.wcotradetools.org/en/harmonized-system | Official HS codes, explanatory notes, classification opinions. Subscription. |

**Note:** The HS system uses 6-digit codes internationally. Countries add additional digits for national tariff lines (US uses 10-digit HTS, EU uses 8-digit CN codes). The WCO updates the HS every 5 years (latest: HS 2022).

---

### 11. TRADE FLOW DATA

#### 11.1 UN Comtrade (Primary Free Source)
- **URL:** https://comtradeplus.un.org/TradeFlow
- **Legacy:** https://comtrade.un.org/
- **API Docs:** https://comtrade.un.org/data/doc/api/
- **Python library:** https://github.com/uncomtrade/comtradeapicall
- **R package:** comtradr (on CRAN)
- **Stata command:** comtrade
- **Pricing:** Free (with hourly request limits). Premium subscription available for bulk downloads and priority access (15-day free trial).
- **Coverage:** Annual trade data from 1988, monthly from 2000. Goods + services. HS-based classification.
- **Strengths:** Most comprehensive free source of bilateral trade flow data. Multiple classification systems supported. Maintained by UN Statistics Division.
- **Weaknesses:** Rate-limited free tier. Data can lag (countries report at different speeds). Discrepancies between reporter and partner data common.

#### 11.2 Other Trade Flow Sources
| Source | URL | Coverage | Cost |
|---|---|---|---|
| **World Bank WITS** | https://wits.worldbank.org/ | Trade, tariff, NTM data | Free |
| **WTO Stats** | https://stats.wto.org/ | WTO trade statistics | Free |
| **ITC Trade Map** | https://www.trademap.org/ | Trade flows, market access | Free (basic) / Paid |
| **OECD Trade Data** | https://data.oecd.org/trade/ | OECD country trade | Free |
| **EU Eurostat/COMEXT** | https://ec.europa.eu/eurostat | Intra/extra EU trade | Free |
| **US Census Foreign Trade** | https://www.census.gov/foreign-trade/ | US trade statistics | Free |
| **Atlas of Economic Complexity** | https://atlas.cid.harvard.edu/ | Trade visualization | Free |

---

## SUMMARY: KEY OPPORTUNITIES & GAPS

### Sanctions/Compliance Space:
1. **Price gap is enormous:** Dow Jones/World-Check charge $50K-$300K+/year. Dilisense charges EUR 0.01/screening. The market is ripe for mid-tier disruption.
2. **Open data + proprietary matching = opportunity:** Free government data (OFAC, EU, UN) is available. The value is in matching algorithms, entity resolution, workflow, and ongoing monitoring. OpenSanctions has proven this model works.
3. **PEP data is the hardest to get:** Sanctions lists are public. PEP lists require editorial curation or scraping government websites globally. This is the key differentiator for premium providers.
4. **Beneficial ownership is fragmenting:** Post-CJEU ruling, EU registers are restricting access. US CTA registry not public. UK PSC remains the gold standard for free, open access.
5. **Crypto/DeFi is a growing buyer segment** with high transaction volumes but lower willingness to pay enterprise prices.

### Trade Data Space:
1. **US BOL data is the foundation:** Public via CBP, but raw data requires significant cleaning/enrichment. Most providers add value through standardization and search.
2. **No dominant API-first player:** Panjiva and Datamyne are enterprise-focused. ImportGenius is more accessible but API is enterprise-gated. Gap for a developer-friendly trade data API.
3. **HS code data is freely available** but fragmented across sources. Opportunity for a unified, well-maintained API.
4. **UN Comtrade is excellent but rate-limited.** Premium access still affordable relative to commercial alternatives.
5. **Most trade data is US-centric.** Global coverage (especially Asia, Africa) remains a premium differentiator.
