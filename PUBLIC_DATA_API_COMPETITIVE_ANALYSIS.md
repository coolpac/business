# Public Data API Business: Competitive Analysis & Opportunity Mapping

**Date:** March 2026
**Purpose:** Identify high-value niches for a data-as-a-service (DaaS) business built on government and public records

---

## 1. Executive Summary — Top 10 Opportunities

Ranked by **(market size) × (low competition) × (technical feasibility)**:

### Tier 1: Best Opportunities (Start Here)

| Rank | Niche | Why It's Attractive | Competition | Est. TAM |
|------|-------|--------------------| ------------|----------|
| **1** | **Restaurant / Health Inspection Data (US-wide)** | No affordable national API. HDI (Hazel Analytics/Ecolab) serves enterprise only (700K+ locations, powers Yelp scores) but no public pricing/API. HDScores offers $0.05/query but limited activity. ~1M+ restaurants fragmented across 3,000+ county health depts. Massive demand from food delivery, insurance, real estate. | **Very low** — HDI (enterprise-only), HDScores (limited) | $20-50M/yr |
| **2** | **Professional License Verification (multi-profession, nationwide)** | 50 states × dozens of license types (contractors, doctors, lawyers, nurses, real estate agents). LicensedCheck exists but limited API. Verifiable only does healthcare. No one covers ALL professions via API. | **Very low** — fragmented, no dominant player | $50-100M/yr |
| **3** | **Building Permits + Contractor Data (underserved geos)** | Shovels.ai covers ~85% US pop from 2,000 jurisdictions but leaves 15% uncovered. International markets (UK, EU, Australia) have virtually zero permit API providers. | **Low-medium** — Shovels is early | $100M+/yr |
| **4** | **Secretary of State / Business Entity Data (cheaper alternative)** | Cobalt Intelligence is the main player (bootstrapped, ~6 employees). OpenCorporates starts at £2,250/yr. Massive demand from fintechs, lenders, KYB/KYC. 50-state coverage is hard but doable. | **Low** — 1-2 niche players | $50-100M/yr |
| **5** | **Zoning & Land Use Data** | Zoneomics and Gridics are the only players. Zoneomics pricing is opaque/high. 20,000+ municipalities with zoning codes locked in PDFs. Essential for real estate, proptech, construction. | **Very low** — 2 players | $30-60M/yr |

### Tier 2: Strong Opportunities

| Rank | Niche | Why It's Attractive | Competition | Est. TAM |
|------|-------|--------------------| ------------|----------|
| **6** | **Court Records & Litigation (state-level gaps)** | UniCourt ($49-299/mo) covers 40+ states but not all. PACER charges $0.10/page for federal. CourtListener is free but incomplete. State courts are severely underserved. | **Medium** — UniCourt, PACER, CourtListener | $200M+/yr |
| **7** | **Government Procurement (international)** | US is covered (SAM.gov, HigherGov $500/yr, GovWin $13-119K/yr). Global procurement intelligence market: $2.6B in 2022 → $15.8B by 2030 (25.3% CAGR). India (~$200B+ annual procurement) has ZERO API. Japan, South Korea, Nigeria, Kenya, South Africa all lack APIs. Brazil has good OCDS APIs but is the exception. | **Low internationally** | $50-100M/yr |
| **8** | **Lobbying & Campaign Finance Data** | OpenSecrets has free API but limited features. FEC data is raw/hard to use. State-level lobbying data is completely fragmented. Political intelligence is a growing market. | **Low** — OpenSecrets is nonprofit | $20-40M/yr |
| **9** | **Environmental Permits & Violations** | EPA ECHO database exists but is clunky. State DEQ data is scattered. ESG reporting demand is surging. Lightbox/EDR charge premium prices. | **Low-medium** | $30-50M/yr |
| **10** | **Import/Export & Customs Data (emerging markets)** | Panjiva (S&P Global) and ImportGenius dominate US bills of lading. But many countries' customs data is inaccessible. India, Brazil, Mexico have data but no good API. | **Medium in US; Low elsewhere** | $100M+/yr |

---

## 2. Country-by-Country Findings

### 🇺🇸 United States

**Most data-rich country but extremely fragmented across federal/state/county levels.**

#### Federal Data Sources
| Data Type | Source | Format | API? | Notes |
|-----------|--------|--------|------|-------|
| Corporate filings (SEC) | [EDGAR](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) | JSON/XML | Yes, free | 10 req/sec limit. sec-api.io charges $55-239/mo for enhanced access |
| Federal court records | [PACER](https://pacer.uscourts.gov) | HTML/PDF | Limited API | $0.10/page, widely hated. CourtListener/RECAP provides free alternative |
| Procurement | [SAM.gov](https://sam.gov) | JSON | Yes, free | Complex API. HigherGov and GovWin add value on top |
| Spending | [USAspending.gov](https://usaspending.gov) | JSON | Yes, free | Good API, well-documented |
| Business entities | 50 separate SOS websites | HTML/PDF | Mostly no | Cobalt Intelligence aggregates all 50 states |
| Property records | 3,000+ county assessors | Various | Some counties | ATTOM ($500+/mo) and CoreLogic dominate |
| Building permits | 20,000+ jurisdictions | PDF/HTML | Rare | Shovels.ai ($599/mo) covers 2,000 jurisdictions |
| Restaurant inspections | 3,000+ county health depts | PDF/HTML | **Almost never** | **Major gap — no national API** |
| Professional licenses | 50 states × dozens of boards | HTML | Few state APIs | LicensedCheck exists but limited |
| Environmental | [EPA ECHO](https://echo.epa.gov/) | JSON | Yes | Also state DEQs with varying quality |
| Sanctions | [OFAC SDN](https://sanctionssearch.ofac.treas.gov/) | XML/CSV | Yes, free | ComplyAdvantage ($120+/mo) adds value |
| Recalls | [CPSC](https://www.cpsc.gov/Recalls/CPSC-Recalls-Application-Programming-Interface), [FDA](https://open.fda.gov/apis/food/), [FSIS](https://www.fsis.usda.gov/science-data/developer-resources/recall-api) | JSON | Yes, free | Decent free APIs exist |
| Campaign finance | [FEC](https://api.open.fec.gov/), [OpenSecrets](https://www.opensecrets.org/open-data/api) | JSON/CSV | Yes | OpenSecrets API is free but limited |
| Trade/customs | CBP (via FOIA) | CSV | No | Panjiva/ImportGenius scrape this data |
| Bankruptcy | [PACER](https://pacer.uscourts.gov) | HTML/PDF | Limited | BankruptcyWatch API provides access |

#### Key State-Level Gaps
- **Property tax assessments**: Only ~60% of counties have digital data accessible online
- **UCC filings**: Available at SOS offices but rarely via API
- **Zoning codes**: Locked in municipal PDFs across 20,000+ jurisdictions
- **Building permits**: Only 2,000 of 20,000+ jurisdictions scraped by Shovels
- **Court records**: Many state courts have no electronic filing system

---

### 🇬🇧 United Kingdom

**Relatively well-digitized but still has gaps.**

| Data Type | Source | API? | Commercial Players |
|-----------|--------|------|-------------------|
| Company data | [Companies House](https://developer-specs.company-information.service.gov.uk/) | Yes, free | OpenCorporates, Dun & Bradstreet |
| Property/Land | [HM Land Registry](https://landregistry.data.gov.uk/) | Partial | Rightmove, Zoopla (proprietary) |
| Court records | HMCTS | Limited | Casedo, Westlaw UK |
| Food hygiene | [FHRS API](https://api.ratings.food.gov.uk/help) | Yes, free | Already open — less opportunity |
| Planning permissions | Local councils | Fragmented | PlanningPortal, LandInsight |
| NHS data | [NHS Digital](https://digital.nhs.uk/services/data-services) | Some | Various health data providers |
| Procurement | [Contracts Finder](https://www.contractsfinder.service.gov.uk/) | Yes | Tussell, Spend Network |

**Opportunity**: Planning permission data is fragmented across 300+ local authorities. A unified API would be valuable for proptech and construction.

---

### 🇩🇪 Germany

| Data Type | Source | API? | Notes |
|-----------|--------|------|-------|
| Company registry | [Handelsregister](https://www.handelsregister.de/) | No | Paid access, difficult to use. North Data provides some coverage |
| Financial publications | [Bundesanzeiger](https://www.bundesanzeiger.de/) | No | Locked behind web interface |
| Land registry | Grundbuch (state-level) | No | Not digitally accessible at scale |
| Court records | Various courts | No | Minimal online access |
| Procurement | [TED](https://ted.europa.eu/) + national portals | Partial | EU-wide opportunities on TED |

**Opportunity**: German company data is notoriously hard to access. Handelsregister charges fees and has no API. A reliable German company data API would have strong demand from KYB/compliance buyers.

---

### 🇫🇷 France

| Data Type | Source | API? | Notes |
|-----------|--------|------|-------|
| Company data | [SIRENE/INSEE](https://sirene.fr/) | Yes, free | Good coverage via api.insee.fr |
| Court/commercial data | [Infogreffe](https://www.infogreffe.fr/) | Partial | Commercial registry, paid access |
| Land/property | [Cadastre](https://cadastre.data.gouv.fr/) | Yes | Open data, good quality |
| Procurement | [BOAMP](https://www.boamp.fr/) + TED | Yes | Reasonably accessible |

**Opportunity**: France is relatively open. Less opportunity for pure data arbitrage, but value-add analytics on top of SIRENE data could work.

---

### 🇳🇱 Netherlands

| Data Type | Source | API? | Notes |
|-----------|--------|------|-------|
| Company data | [KVK](https://developers.kvk.nl/) | Yes | Chamber of Commerce API exists |
| Land registry | [Kadaster](https://www.kadaster.nl/) | Yes | Well-digitized |
| Procurement | [TenderNed](https://www.tenderned.nl/) | Yes | Good coverage |

**Opportunity**: Netherlands is well-digitized. Lower opportunity.

---

### 🇪🇸 Spain / 🇮🇹 Italy / 🇵🇱 Poland

- **Spain**: Registro Mercantil (company registry) is paid and difficult to access programmatically. Property data via Catastro is partially open.
- **Italy**: Camera di Commercio data is paid. Visura services charge per-lookup fees. No comprehensive API.
- **Poland**: KRS (court registry) is partially accessible. CEIDG (business registry) has basic API.

**Opportunity**: Southern/Eastern European company data is poorly served by APIs. A pan-European company registry API covering these countries would fill a gap OpenCorporates doesn't fully address.

---

### 🇮🇳 India

| Data Type | Source | API? | Notes |
|-----------|--------|------|-------|
| Company data | [MCA21](https://www.mca.gov.in/MinistryV2/companyreport.html) | Limited | Charges per document. Poorly accessible |
| Court records | [eCourts](https://ecourts.gov.in/) | No API | 100M+ pending cases, massive demand |
| Land records | State portals (Bhoomi, DILRMP) | Fragmented | Different system per state |
| GST data | [GST Portal](https://www.gst.gov.in/) | Limited | Business verification use case |
| Procurement | [CPPP](https://eprocure.gov.in/) | No | Government procurement portal |
| Import/export | [DGFT](https://www.dgft.gov.in/) | No | Trade data locked in the system |

**Opportunity**: India is one of the largest underserved markets. MCA21 company data, eCourts case data, and land records are enormously valuable but locked behind bad interfaces. Surepass.io and similar Indian startups are beginning to address this. Massive TAM due to population and regulatory requirements (GST verification, KYC).

---

### 🇧🇷 Brazil / 🇲🇽 Mexico

- **Brazil**: CNPJ data has official API ([Consulta CNPJ](https://www.gov.br/conecta/catalogo/apis/consulta-cnpj)) + monthly bulk dumps. [OpenCNPJ](https://opencnpj.org/) provides free API (50 req/sec). **Major change for 2026**: CNPJ going alphanumeric (letters + numbers) starting July 2026. Court records fragmented across **91 courts** (federal + state). **Property records are cartório-based (notary offices) with NO digital access** — retrieving a "matrícula do imóvel" takes days to weeks. Commercial providers: ReceitaWS, CNPJá, CPF.CNPJ.
- **Mexico**: SAT (tax authority) data, IMSS data, company registries are difficult to access.

**Opportunity**: Brazil's property records being completely analog (cartório-based) is one of the largest gaps in any major economy. Court records across 91 separate systems are another massive opportunity. CNPJ is well-served but property and courts are wide open.

---

### 🇦🇪 UAE / 🇸🇦 Saudi Arabia

- **UAE**: DED (Dubai), ADGM, and **40+ free zone registries** are all separate. No unified company API. No public APIs for company data.
- **Saudi**: **WATHQ API Platform** ([developer.wathq.sa](https://developer.wathq.sa/en/apis)) is a standout — official APIs for commercial registration, articles of association, power of attorney, **real estate deed data**, and national addresses. 2025 reform unified commercial registration into single national system.

**Opportunity**: Saudi Arabia is **ahead of UAE** in API infrastructure thanks to WATHQ. UAE's fragmentation across emirates and 40+ free zones makes comprehensive data very hard. Both markets underserved by global providers. Gulf company verification for KYB/AML in high demand.

---

### 🇸🇬 Singapore / 🇯🇵 Japan / 🇰🇷 South Korea

- **Singapore**: [ACRA BizFile](https://www.acra.gov.sg/) new portal launched Dec 2024. Open corporate datasets (27 CSV files, monthly) at [data.gov.sg](https://data.gov.sg/). New **Business Profile API** launched Nov 2025. Beneficial ownership (RORC) restricted to law enforcement.
- **Japan**: Two free official APIs: [EDINET](https://disclosure.edinet-fsa.go.jp/) (financial filings, 11K+ companies) and [NTA Corporate Number API](https://www.houjin-bangou.nta.go.jp/en/) (all legal entities, free). But core company registry (法務局/Touki) has **no API** — 5.4M+ companies, individual lookups only. Private company financials completely opaque. EDINET only supports date-based queries (no company name search). Market dominated by Teikoku Databank and Tokyo Shoko Research.
- **South Korea**: [DART](https://dart.fss.or.kr/) provides corporate disclosures. KONEPS procurement is comprehensive but closed (no public API).

**Opportunity**: Japan has the largest gap between available data and API access. An English-language Japanese company data API combining EDINET + NTA + Touki data would be extremely valuable for international compliance, due diligence, and supply chain verification. The Touki registry's lack of API is the key bottleneck.

---

### 🇳🇬 Nigeria / 🇿🇦 South Africa / 🇰🇪 Kenya

- **Nigeria**: [CAC](https://search.cac.gov.ng/) public search available but **no official API**. Basic data: company name, registration number, type, status.
- **South Africa**: [CIPC](https://bizportal.gov.za/) requires login for business search. **No public API**. In 2014, CIPC introduced terms restricting data re-use, effectively blocking open API access. Most restrictive of the three.
- **Kenya**: BRS via [eCitizen](https://brs.ecitizen.go.ke/) portal. **No public API**. BRS Version II launched Feb 2026 with digital certificates replacing physical ones.

**Opportunity**: All three registries lack public APIs. South Africa is most restrictive. Nigeria's CAC has most accessible public search. Growing economies + no APIs + increasing AML/KYB requirements from international banks = massive commercial opportunity with near-zero competition.

---

### 🇨🇦 Canada

- Provincial business registries fragmented across federal + 13 provincial/territorial systems. No unified national registry. Alberta requires designated registry agents (no direct access). Some provinces free to search (Ontario, NS, QC), others pay-per-search (NB, BC).
- [SEDAR+](https://www.sedarplus.ca/) for corporate filings (replaced SEDAR July 2023) — **no official public API**. Third-party access via QuoteMedia.
- [CanLII](https://www.canlii.org/) for court decisions — **free API** (rare globally). [API docs on GitHub](https://github.com/canlii/API_documentation). Also [A2AJ](https://a2aj.ca/canadian-legal-data/) provides 180K+ court decisions via REST API + Hugging Face.
- Property data varies by province

**Opportunity**: Canada mirrors Germany's fragmentation problem. CanLII is a standout free legal data API. SEDAR+ having no public API creates opportunity for securities filing aggregators. Provincial registry unification would be valuable.

---

### 🇦🇺 Australia / 🇳🇿 New Zealand

- **Australia**: [ABR](https://abr.business.gov.au/) provides free ABN lookup API (SOAP/JSON) — handled 1.1B searches in 10 months, 83% via web services. [ASIC](https://www.asic.gov.au/) has APIs for business names/companies registers + free weekly open dataset on Data.gov.au. **$207M beneficial ownership register** announced Aug 2025 (consultation starts early 2027). Property data fragmented across 6 states (NSW LRS, VIC Land Use Victoria, QLD Titles Registry, etc.) — CoreLogic dominates aggregation.
- **New Zealand**: Companies Office has good digital access.

**Opportunity**: ABR API is excellent for basic lookups. Property data state-fragmentation mirrors India but at smaller scale. ASIC open dataset is good for research. CoreLogic near-monopoly on Australian property data creates room for challengers.

---

## 3. Niche Analysis Table

| Niche | Competitive Density (1-5) | Demand Signal Strength | Est. TAM | Top Players | Key Gap |
|-------|--------------------------|----------------------|----------|-------------|---------|
| **Business entity/SOS** | 2 | Very High | $100M+ | Cobalt Intelligence, OpenCorporates, D&B | Affordable all-50-state API |
| **Court records** | 3 | Very High | $200M+ | UniCourt, PACER, CourtListener | State court coverage |
| **Building permits** | 2 | High | $100M+ | Shovels.ai, ATTOM, Construction Monitor | Rural/int'l coverage |
| **Property records** | 4 | Very High | $500M+ | ATTOM, CoreLogic, Regrid | High price barrier to entry |
| **Health inspections** | 1.5 | High | $30M+ | HDI/Ecolab (enterprise-only, 700K+ locations), HDScores ($0.05/query) | **No affordable developer-friendly API** |
| **Professional licenses** | 1 | High | $50M+ | Verifiable (healthcare only), LicensedCheck | Cross-profession API |
| **Govt procurement** | 3 (US) / 1 (intl) | High | $100M+ | HigherGov, GovWin, Govly | International markets |
| **Corporate filings (SEC)** | 3 | High | $50M+ | sec-api.io, SEC Filing Data | Already decent free API |
| **Environmental** | 2 | Medium-High | $40M+ | EDR/Lightbox, EPA ECHO | State-level permits |
| **Transportation** | 3 | Medium | $50M+ | MarineTraffic, Carfax | Fragmented but served |
| **Import/export** | 3 | High | $100M+ | Panjiva, ImportGenius | Emerging market coverage |
| **Sanctions/PEP/AML** | 3 | Very High | $200M+ | ComplyAdvantage, Dow Jones, Refinitiv | OpenSanctions is free competitor |
| **Bankruptcy** | 2 | Medium-High | $30M+ | BankruptcyWatch, CourtListener | Subset of court records |
| **Zoning/land use** | 1 | High | $40M+ | Zoneomics, Gridics | Only 2 players, opaque pricing |
| **Food safety/recalls** | 2 | Medium | $15M+ | FDA/CPSC APIs (free) | Recalls already have free APIs |
| **Lobbying/donations** | 1 | Medium | $20M+ | OpenSecrets (nonprofit) | State-level lobbying data |

---

## 4. Full Competitive Matrix

### Business Entity / Company Registry APIs

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **Cobalt Intelligence** | [cobaltintelligence.com](https://cobaltintelligence.com/) | SOS filings, UCC, TIN/EIN | ~**$0.75/lookup** ($750/1K lookups). Volume discounts. 30 free credits | All 50 US states + DC. Real-time scraping. Officer data in 28 states | REST (2 concurrent/state, 5 total) | Small team (~6), US only, real-time scraping = slower, data varies by state | 2015 | TinySeed (pre-seed) |
| **Middesk** | [middesk.com](https://www.middesk.com/) | SOS filings, UCC, TIN, risk scoring | **$8K/yr** (8 states); **$15K/yr** (all 50 states). UCC/TIN extra | All 52 US jurisdictions. Direct connections to SOS offices + IRS | REST | US-only, premium pricing, aimed at fintech/lending vertical | Unknown | $100M+ raised |
| **OpenCorporates** | [opencorporates.com](https://opencorporates.com/) | Company registrations worldwide | **£2,250/yr** (Essentials) → **£6,600/yr** (Starter) → **£12,000/yr** (Basic). Bulk: custom. Free tier: 200 req/mo | 220M+ companies, 140+ registries | REST (JSON/XML) | ~Half of sources no longer actively updated. Low rate limits (200/day on lower tiers). No financial/UCC/BO data | 2010 | Unknown |
| **Dun & Bradstreet** | [dnb.com](https://www.dnb.com/) | D-U-N-S, firmographics, credit | From $49/mo (Hoovers); D&B Direct+ **$50K+/yr** (50% discounts for multi-year). Per-report via LexisNexis: $39-$629 | 500M+ entities, 220+ countries, 5M updates/day | REST | Extremely expensive, complex pricing, walled garden, slow sales | 1841 | Public (NYSE: DNB) |
| **Enigma** | [enigma.com](https://enigma.com/) | US SMB data, KYB attributes | **$5 per 100 credits** (PAYG). ~$0.55 per detailed profile. Free plan available | 98M legal entities, 48.9M brands, 2.4B data points. US-focused | GraphQL + REST | US only, credit system confusing, not always real-time from registries | 2011 | $135M+ raised |
| **Moody's Orbis (BvD)** | [moodys.com](https://www.moodys.com/) | Global company data, ownership, financials | **$20K-$100K+/yr** (custom) | **600M+ companies**, 170+ sources, 99%+ private companies | REST, bulk, web | Doesn't own most data (resale restrictions), extremely expensive, not API-first | 1991 | Moody's subsidiary |
| **Global Database** | [globaldatabase.com](https://www.globaldatabase.com/) | Company data from 100+ registries | **£3,000/yr** (platform); **$0.10-$1.00/API call**. Larger: EUR 12K/yr + EUR 750 onboarding | 400M+ companies, 195 countries. UBO data, financials | REST (6,000 req/min) | Pricing can escalate, coverage depth varies by country | 2015 | Unknown |
| **Zephira.ai** | [zephira.ai](https://zephira.ai/) | Company registry data, KYB | **$99/mo** (Starter). Free tier for testing | 300M+ companies, 150+ countries | REST | New entrant, limited track record, depth per country unclear | Unknown | Unknown |
| **North Data** | [northdata.com](https://www.northdata.com/) | European company data, publications | **EUR 49/mo** (Premium); **EUR 500/mo** API (1K req/mo); **EUR 2,250/quarter** per country export | 86M+ companies, 530M+ publications, 23 European countries | REST (JSON/XML) | Europe-only, no US, low API limits at starter, exports expensive | Unknown | Unknown |
| **Kyckr** | [kyckr.com](https://www.kyckr.com/) | Real-time registry data, 1,000+ doc types | Custom (expensive) | 300+ registers, 100+ countries. Real-time retrieval | REST (JSON/XML) | Pricing opaque, targets regulated entities, likely expensive | Unknown | Unknown |
| **Creditsafe** | [creditsafe.com](https://www.creditsafe.com/) | Company data, credit scores | Custom. Free trial (100 calls on test DB) | 430M+ companies, 70+ countries | REST (Connect API) | Primarily credit reporting, pricing opaque | Unknown | Unknown |
| **Sayari** | [sayari.com](https://sayari.com/) | Corporate hierarchies, trade networks, ownership | Custom annual license (est. **$50K+**) | 11B+ entities, 250+ jurisdictions, 36B+ records | REST (graph analytics) | Enterprise-only, overkill for basic lookups | Unknown | Unknown |
| **Veridion** | [veridion.com](https://veridion.com/) | AI-enriched business data | Custom pricing | 120M+ companies, 250+ locations | REST | Web-scraped (not official registries), less authoritative for compliance | 2019 | $6M+ raised |
| **Handelsregister.ai** | [handelsregister.ai](https://handelsregister.ai/) | German business registry | 500 free credits on signup | Germany only | REST | Germany-only, very new (July 2025 HN launch), unproven | 2025 | Unknown |

### Court Records & Litigation

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **UniCourt** | [unicourt.com](https://unicourt.com/) | Federal + state court records | $49-299/mo (personal); Enterprise custom | 4,000+ courts, 40+ states, 2B+ dockets | REST | State coverage gaps, court doc fees extra | 2015 | $35M+ raised |
| **PACER** | [pacer.uscourts.gov](https://pacer.uscourts.gov/) | Federal court records | $0.10/page (cap $3/doc) | All federal courts | Limited REST | Expensive at scale, bad UX, no state courts | N/A | Government |
| **CourtListener/RECAP** | [courtlistener.com](https://www.courtlistener.com/) | Federal + some state | Free (donations) | Growing, community-sourced | REST | Incomplete coverage, relies on RECAP users | 2010 | Nonprofit (Free Law Project) |
| **Trellis Law** | [trellislaw.com](https://www.trellis.law/) | State trial court analytics | Custom pricing | 15+ states | Platform | Limited state coverage, no API | 2018 | $15M+ raised |
| **PacerPro** | [pacerpro.com](https://www.pacerpro.com/) | Federal court docket workflow | Custom pricing | Federal courts | Platform | Workflow tool, not a data API | 2012 | Unknown |
| **BankruptcyWatch** | [bankruptcywatch.com](https://www.paceruptime.com/) | Bankruptcy court data | Custom pricing | All federal bankruptcy courts | REST | Bankruptcy only | Unknown | Unknown |

### Property Data

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **ATTOM Data** | [attomdata.com](https://www.attomdata.com/) | Property, tax, deed, AVM, permits | From ~$95/mo; enterprise custom annual license. 30-day free trial | 158M+ properties, 99% US pop, 9,000+ attributes | REST (JSON/XML) | Data lags weeks behind, opaque enterprise pricing | 2012 | Acquired by equity firm |
| **CoreLogic (Cotality)** | [corelogic.com](https://www.corelogic.com/) | Property, MLS, insurance, tax, liens | Median ~**$12K/yr**. Per-call: $0.005 (address lookup) to **$11.50** (lien search) | 99.9% US properties, 200+ data sources | REST | Very expensive, complex sales, inaccessible to startups | 2010 | Public (NYSE: CLGX) |
| **Regrid** | [regrid.com](https://regrid.com/) | Parcel data, boundaries | $10/mo (pro); **$80K/yr** (nationwide enterprise); $400/county download | 151M+ parcels, 156M+ building footprints, US + Canada | REST + Tiles | Expensive nationwide, primarily boundaries not deep property data | 2009 | Unknown |
| **Estated** | [estated.com](https://estated.com/) | Property data | Being migrated to ATTOM (was $179/mo) | US-wide | REST (v4, being deprecated) | Acquired by ATTOM, docs sunset 2026. Not viable for new integrations | 2016 | Acquired |
| **BatchData** | [batchdata.io](https://batchdata.io/) | Property data | From **$0.01/API call** | US properties | REST | Less depth than ATTOM/CoreLogic | Unknown | Unknown |
| **Reonomy (Altus Group)** | [reonomy.com](https://www.reonomy.com/) | Commercial property data | $49-300/mo (individual); enterprise/API custom | 54M+ commercial properties, all 50 states | REST (batch up to 1M) | Commercial only, no residential, enterprise-only API | Unknown | Acquired by Altus Group |
| **PropertyShark (Yardi)** | [propertyshark.com](https://www.propertyshark.com/) | Property records, 180+ data points | $60-170/mo | 100M+ residential, 20M+ commercial. Best in NYC | **No API** | No API at all — web interface only. Coverage best in NYC | Unknown | Yardi subsidiary |
| **DataTree (First American)** | [datatree.com](https://web.datatree.com/) | Property, ownership, liens, HOA, PACE | Avg ~**$30.5K/yr** | Nationwide incl. recorded document images | REST (JSON) | Enterprise pricing, no transparent tiers, limited public docs | Unknown | First American subsidiary |
| **Black Knight (ICE)** | [mortgagetech.ice.com](https://mortgagetech.ice.com/) | Property, climate risk, permits | Enterprise only (custom) | Comprehensive residential | REST | Purely institutional, acquired by ICE for $11.7B. Inaccessible to startups | Unknown | ICE subsidiary |
| **HouseCanary** | [housecanary.com](https://www.housecanary.com/) | Property analytics, AVM, rental | $79/mo; per-call $0.30-6.00 | US residential | REST | More analytics than raw records | Unknown | Unknown |

### Building Permits

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **Shovels.ai** | [shovels.ai](https://www.shovels.ai/) | Building permits, contractors | **$599/mo**; 250 free API calls | 2,000+ jurisdictions, 85% US pop, 180M permits | REST | 15% US uncovered, US only, monthly updates only | 2022 | $6.5-8.25M raised (Base10) |
| **BuildZoom** | [buildzoom.com](https://www.buildzoom.com/) / [buildzoomdata.com](https://www.buildzoomdata.com/) | Building permits, contractors | Enterprise/partnership only (not public) | **350M+ permits**, 2,400 jurisdictions, 90% US pop, 6M+ contractors | Bulk files, custom integrations | **No public API**, no self-service, partnership-only | Unknown | Unknown |
| **ConstructConnect** | [constructconnect.com](https://www.constructconnect.com/) | Construction project leads | **$129-199/mo** (Starter/Professional) | 1M+ projects, 400+ markets, 5,000 updated daily | REST (with Project Intelligence) | More project leads than raw permits, contractor-focused | Unknown | Unknown |
| **Construction Monitor** | [constructionmonitor.com](https://www.constructionmonitor.com/) | Permit data, construction leads | Custom pricing; shop available for 5 states | 17M+ permits, 70+ metro areas | REST (Elasticsearch) + FTP | Limited to 70+ metros, 5 states in self-serve shop | Unknown | Unknown |
| **ATTOM** | [attomdata.com](https://www.attomdata.com/) | 300M+ building permits | Custom (bundled with property data) | 2,000+ building depts | REST | Expensive, bundled with property data, not standalone | 2012 | N/A |

### Zoning & Land Use

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **Zoneomics** | [zoneomics.com](https://www.zoneomics.com/) | Zoning codes, land use, FLUM | Usage-based or monthly (opaque pricing) | US + Canada | REST + Tiles | Pricing not transparent, limited international | Unknown | Moody's partnership |
| **Gridics** | [gridics.com](https://gridics.com/) | Parcel-level zoning, development capacity | Custom pricing | US (select municipalities) | REST | Limited coverage, municipality-dependent | 2014 | Unknown |
| **LightBox** | [lightboxre.com](https://www.lightboxre.com/) | Zoning (as add-on to property data) | Custom pricing | National US | REST + Bulk | Zoning is add-on, not primary product | 2019 | $400M+ raised |

### Government Procurement

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **SAM.gov** | [sam.gov](https://sam.gov/) | Federal contracts, opportunities | Free (1,000 req/day with key) | US federal only | REST | 1-4 week registration wait, complex nested JSON, 1K req/day limit | N/A | Government |
| **USAspending** | [usaspending.gov](https://api.usaspending.gov/) | Federal spending, contracts, grants | Free, no key needed | All US federal spending since FY2008 | REST (open source) | Awards/spending only, not opportunities | N/A | Government |
| **HigherGov** | [highergov.com](https://www.highergov.com/) | Federal + SLED procurement | **$500/yr** (Starter) to **$2,500/yr** (Standard); API included | 200+ sources, 65M+ awards, 300+ API fields | REST | US-only, 300 API fields is subset of 5,000+ tracked | Unknown | Unknown |
| **GovWin (Deltek)** | [govwin.com](https://iq.govwin.com/) | Federal + SLED procurement intelligence | **$13K-$119K/yr** (~$50-100/user/mo) | US + Canada, 1.9M company profiles | Platform (subscriber-only API) | Very expensive, no public API docs, no international beyond US/Canada | 2005 | Roper Technologies subsidiary |
| **Bloomberg Gov** | [about.bgov.com](https://about.bgov.com/) | Federal procurement + legislative | Enterprise ($10K-$50K+/yr est.) | US federal | REST/CSV/JSON (data license) | Very expensive, US-only, terminal product not API-first | N/A | Bloomberg subsidiary |
| **Govly** | [govly.com](https://www.govly.com/) | Federal + vehicle opportunities | Free tier; **$99/user/mo** ($15K+/yr) | 40+ contract vehicles (GSA, SEWP, ITES) | API on premium plans | US-only, newer entrant, API only on premium | 2020 | Unknown |
| **GovCon API** | [govconapi.com](https://govconapi.com/) | SAM.gov wrapper | Free (25 req/day); **$19/mo** (Developer) | 134K+ federal opportunities | REST (clean JSON) | Limited to SAM.gov data only | Unknown | Unknown |
| **GovSpend** | [govspend.com](https://govspend.com/) | SLED spending + federal | ~$7K-$25K/yr | SLED purchase orders, bids, contracts + 19 federal datasets | Salesforce/Zapier/API | SLED-focused, expensive | Unknown | Unknown |
| **Spend Network** | [spendnetwork.com](https://www.spendnetwork.com/) | Global procurement | Enterprise (unlisted) | **160 countries**, 700+ data feeds | REST (JSON) | Coverage depth varies wildly by country, opaque pricing | 2007 | Unknown |
| **EU TED** | [ted.europa.eu](https://ted.europa.eu/) | EU-wide procurement | Free | All EU member states + EEA | REST + FTP + CSV | Only above-threshold procurement, complex XML, language barriers | N/A | EU Government |
| **OpenTender.eu** | [opentender.eu](https://opentender.eu/) | European procurement (OCDS) | Free (**non-commercial only**) | 35 European jurisdictions | Bulk download (OCDS JSON) | Non-commercial license, not a real-time API | N/A | NGO (academic) |

### Sanctions & Compliance

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **ComplyAdvantage** | [complyadvantage.com](https://complyadvantage.com/) | Sanctions, PEP, adverse media | From $120/mo; **free 12mo for startups** (ComplyLaunch). Est. $15K-100K+/yr at scale | Global, 100+ sanctions lists | REST | Expensive at scale | 2014 | $100M+ raised |
| **Dow Jones Risk** | [dowjones.com](https://www.dowjones.com/professional/risk/) | Sanctions, PEP, adverse media | **$50K-$200K+/yr**, opaque pricing | Global, editorially curated, premium | Various | Very expensive, enterprise-only, opaque | N/A | News Corp subsidiary |
| **LSEG World-Check** | [lseg.com](https://www.lseg.com/en/data-analytics/financial-data/sanctions-screening) | Sanctions, PEP, entity data | Points-based, **$30K-$300K+/yr** | Global, 4.9M+ risk profiles | Various | Very expensive, LSEG subsidiary | N/A | LSEG subsidiary |
| **OpenSanctions** | [opensanctions.org](https://www.opensanctions.org/) | Sanctions, PEP, watchlists | Free (non-commercial); **EUR 0.10/API call** (commercial); self-host yente for free | Global, open source | REST (yente) | Commercial license needed for business use | 2021 | Grants/donations |
| **sanctions.io** | [sanctions.io](https://www.sanctions.io/) | Sanctions, PEP screening | **$899/5,000 calls** (~$0.18/call) | Global, 1M+ PEP records, hourly updates | REST | Newer player | Unknown | Unknown |
| **Dilisense** | [dilisense.com](https://dilisense.com/) | Sanctions, PEP, criminal watchlists | **EUR 0.01/screening** (cheapest in market) | Global | REST | Newer/smaller player | Unknown | Unknown |
| **Sanctionssearch.com** | [sanctionssearch.com](https://sanctionssearch.com/) | Sanctions screening | **GBP 90/yr + GBP 0.10/search** | Global | Web + API | Basic matching, less sophisticated | Unknown | Unknown |
| **NameScan** | [namescan.io](https://namescan.io/) | PEP + sanctions screening | **$0.48-$1.80/scan** (PAYG) | Global | REST | Pay-as-you-go only | Unknown | Unknown |

### Import/Export & Trade Data

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **Panjiva** | [panjiva.com](https://panjiva.com/) | Bills of lading, shipment data | **$1K-$3K+/mo** (custom) | 2B+ records, 22 customs sources | Platform | Expensive, S&P Global owned, no self-serve | 2006 | Acquired by S&P Global |
| **Descartes Datamyne** | [descartes.com](https://www.descartes.com/) | Global trade data | Enterprise (custom) | **230 markets**, comprehensive | Platform | Enterprise-only, very expensive | Unknown | Public (NASDAQ: DSGX) |
| **ImportGenius** | [importgenius.com](https://www.importgenius.com/) | US customs, bills of lading | **$149-$399/mo** (self-serve); enterprise custom | 25+ countries | Platform + API (enterprise) | API only on enterprise tier | 2006 | Unknown |
| **ImportKey** | [importkey.com](https://www.importkey.com/) | US import/export data | **~$25-45/mo** (basic) | US-focused | Platform | Basic, US only | Unknown | Unknown |
| **TradeInt** | [tradeint.com](https://tradeint.com/) | Trade intelligence | Custom pricing | Multiple countries | Platform | Smaller player | Unknown | Unknown |
| **UN Comtrade** | [comtradeplus.un.org](https://comtradeplus.un.org/) | Trade flow data (aggregated) | Free (rate-limited) | Global, all countries | REST | Aggregated flows not shipment-level, rate limits | N/A | UN |

### SEC / Corporate Filings

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **SEC EDGAR** | [sec.gov](https://www.sec.gov/search-filings/edgar-application-programming-interfaces) | All SEC filings | Free | All US public companies | REST | 10 req/sec limit, no streaming | N/A | Government |
| **sec-api.io** | [sec-api.io](https://sec-api.io/) | Enhanced EDGAR access | Free (100 calls) → $55-239/mo | 18M+ filings, 800K+ filers | REST + WebSocket | Small company, niche | Unknown | Unknown |
| **SEC Filing Data** | [secfilingdata.com](https://www.secfilingdata.com/) | EDGAR data | Tiered plans | Full EDGAR | REST | Smaller player | Unknown | Unknown |

### Lobbying & Campaign Finance

| Company | URL | Data | Pricing | Coverage | API Type | Weaknesses | Founded | Funding |
|---------|-----|------|---------|----------|----------|-----------|---------|---------|
| **OpenSecrets** | [opensecrets.org](https://www.opensecrets.org/) | Campaign finance, lobbying | Free (API) + bulk downloads | US federal + state | REST (JSON/XML) | Limited API features, nonprofit resources | 1983 | Nonprofit |
| **FEC API** | [api.open.fec.gov](https://api.open.fec.gov/) | Federal campaign finance | Free | US federal only | REST | Raw data, hard to use | N/A | Government |
| **FollowTheMoney** | [followthemoney.org](https://www.followthemoney.org/) | State campaign finance | Free (merged with OpenSecrets) | US state-level | REST | Being deprecated/merged | N/A | Nonprofit |

---

## 5. Buyer Analysis

### Who Pays for What

| Niche | Primary Buyers | Job Titles | Current Spend | Pain Point | Where They Hang Out |
|-------|---------------|------------|---------------|------------|-------------------|
| **Business entity data** | Fintechs, lenders, banks, compliance teams | Compliance Officer, VP Risk, CTO | $2K-50K/yr | KYB verification, fraud prevention | Fintech meetups, LendIt, Money20/20, r/fintech |
| **Court records** | Law firms, insurance, background check cos | Paralegals, Claims Adjustors, Legal Ops | $5K-100K/yr | Litigation monitoring, risk assessment | ABA conferences, LegalTech, ILTACON |
| **Property data** | Real estate investors, lenders, insurers | RE Analyst, Underwriter, Portfolio Mgr | $10K-500K/yr | Property valuation, lien discovery | BiggerPockets, RE investor groups, IMN conferences |
| **Building permits** | Solar companies, HVAC, home improvement, RE | Sales Ops, Market Analyst, BD Manager | $5K-50K/yr | Lead generation, market sizing | Construction forums, SolarPowerWorld, HBA |
| **Professional licenses** | Healthcare orgs, HR, staffing, insurance | Credentialing Specialist, HR Director | $3K-30K/yr | Compliance, credential verification | NAMSS, HCCA conferences |
| **Govt procurement** | Defense contractors, IT firms, consultants | BD Manager, Capture Manager, GovCon | $5K-50K/yr | Finding and winning contracts | GovConWire, AFCEA, PSC conferences |
| **Sanctions/AML** | Banks, fintechs, crypto, money services | Chief Compliance Officer, AML Analyst | $10K-200K/yr | Regulatory compliance (BSA/AML) | ACAMS conferences, compliance forums |
| **Import/export** | Manufacturers, freight forwarders, sourcing | Supply Chain Mgr, Procurement, Logistics | $3K-30K/yr | Supplier discovery, competitive intel | TradeWinds, JOC events |
| **Zoning data** | Real estate developers, investors, proptech | RE Developer, Land Planner, CTO | $5K-50K/yr | Site selection, development feasibility | ULI conferences, NAIOP |
| **Environmental** | ESG analysts, RE due diligence, insurers | ESG Analyst, Environmental Consultant | $5K-100K/yr | Phase I assessments, ESG reporting | ASTM, EBA conferences |
| **Restaurant inspections** | Food delivery (DoorDash, Uber Eats), insurance, RE | Risk Analyst, Data Scientist, Ops | $5K-50K/yr | Risk scoring, marketplace trust | Food safety conferences |
| **Lobbying/political** | Advocacy groups, corporations, journalists | Government Affairs, Policy Analyst | $2K-20K/yr | Tracking political influence | PACS, advocacy conferences |

---

## 6. Arbitrage Opportunities

### Government Charges Fees → Could Be Aggregated Cheaper

| Data Source | Current Cost | Opportunity |
|-------------|-------------|-------------|
| **PACER** | $0.10/page, $3/doc cap | CourtListener/RECAP already offers free alternative for some data. Full archive aggregation could undercut |
| **ACRA Singapore** | S$5-15/company report | Aggregate and resell at lower per-query price |
| **MCA21 India** | Per-document fees | Aggregate Indian company data into a clean API |
| **Japanese company registry** | Per-lookup fees at 法務局 | English-language API for Japanese companies |
| **ASIC Australia** | Paid company extracts | ABR is free but ASIC details require payment |
| **Italian Camera di Commercio** | Per-visura fees | Italian company API is underserved |

### Legacy Providers Charge Premium for Technically Free Data

| Provider | Annual Cost | Data Source (Free) | Arbitrage Potential |
|----------|------------|-------------------|-------------------|
| **D&B** | $50K+/yr | Secretary of State filings + commercial registries | High — SOS data is public |
| **CoreLogic/ATTOM** | $10K-500K/yr | County assessor/recorder offices | Medium — hard to scrape all 3,000+ counties |
| **GovWin** | $10K+/yr | SAM.gov + agency websites | High — SAM.gov has free API |
| **Panjiva** | $5K+/yr | CBP bills of lading (FOIA) | Medium — data cleaning is the value-add |
| **LexisNexis** | $10K+/yr | Court records, public records | High — data is public but aggregation is hard |

### Cross-Border Data Gaps

| Data Exists Here | Missing Here | Opportunity |
|-----------------|-------------|-------------|
| UK Companies House (free API) | Germany Handelsregister (no API) | Pan-EU company data API |
| UK FHRS (food hygiene API) | US (no national API) | US restaurant inspection aggregator |
| US EPA ECHO (environmental API) | Most other countries | International environmental compliance API |
| US SAM.gov (procurement API) | India, Brazil, Africa | Emerging market procurement API |
| US PACER (court records) | India eCourts (no API) | Indian court records API |

### Demand Signals Without Good API Providers

| Signal | Evidence | Current Solution |
|--------|----------|-----------------|
| **Restaurant inspection data** | Real estate investors, insurance companies, food delivery platforms all need this | Manual lookup on county websites |
| **Multi-state license verification** | Healthcare credentialing is a $2B+ industry, construction licensing verification required by law | Call individual state boards or use fragmented tools |
| **Zoning code lookups** | Every RE developer needs this, proptech companies building site selectors | Hire a land use attorney or manually read municipal codes |
| **State-level lobbying disclosure** | Political intelligence firms and advocacy groups need this | Manual FOIA requests or per-state portal crawling |
| **Indian company verification** | International banks and fintechs expanding to India need KYB | Manual MCA21 lookups or expensive providers |
| **African company data** | Due diligence on African counterparties for trade finance | Almost nothing available |

---

## 7. Technical Feasibility Assessment — Top 10 Opportunities

### 1. Restaurant / Health Inspection Data (US)

| Factor | Assessment |
|--------|-----------|
| **Data source** | ~3,000 county health department websites |
| **Scrapeable?** | Yes, but extreme fragmentation. Many use HealthSpace platform (single vendor = opportunity). Some publish on open data portals |
| **Official API?** | No national API. A few cities (NYC, Chicago, SF) have open data portals |
| **Anti-bot measures** | Generally low on government sites |
| **Legal considerations** | Public records, scraping likely legal per hiQ v. LinkedIn. No login required for most |
| **Update frequency** | Inspections happen 1-3x/year per restaurant. Data updates irregularly |
| **Engineering effort** | **High** — need 3,000+ scrapers, but many use common platforms (HealthSpace, Decade). MVP: start with top 50 metros (cover 60%+ of restaurants). Estimate: 3-6 months for MVP |
| **Moat** | High — once you have the scraping infrastructure, it's very hard to replicate |

### 2. Professional License Verification (US, multi-profession)

| Factor | Assessment |
|--------|-----------|
| **Data source** | 50 state licensing boards × multiple professions per state |
| **Scrapeable?** | Yes, most boards have public lookup tools |
| **Official API?** | Very few states have APIs (MA, CA have some). NPPES/NPI free for healthcare |
| **Anti-bot measures** | Some boards use CAPTCHAs. Generally low |
| **Legal considerations** | Public records. License status is public information by law |
| **Update frequency** | Licenses renew annually or biennially |
| **Engineering effort** | **High** — 50 states × 20+ professions = 1,000+ scraper targets. MVP: focus on top 5 professions (contractors, doctors, nurses, lawyers, real estate agents) across all states. Estimate: 4-6 months for MVP |
| **Moat** | High — maintenance of 1,000+ scrapers is a significant barrier |

### 3. Building Permits (International + US gaps)

| Factor | Assessment |
|--------|-----------|
| **Data source** | US: remaining ~18,000 jurisdictions not covered by Shovels. International: municipal building departments |
| **Scrapeable?** | US: yes, rural/small counties may have PDFs or no online data. International: varies |
| **Official API?** | Very rare |
| **Anti-bot measures** | Low on government sites |
| **Legal considerations** | Public records |
| **Update frequency** | Permits issued continuously |
| **Engineering effort** | **Medium-High** — US gap-filling: focus on remaining metros not in Shovels. International: start with UK/Australia/Canada where data is more digital. Estimate: 3-6 months for MVP |
| **Moat** | Medium — Shovels has head start in US, but international is wide open |

### 4. Secretary of State / Business Entity (US, cheaper)

| Factor | Assessment |
|--------|-----------|
| **Data source** | 50 state SOS websites |
| **Scrapeable?** | Yes, but states change their sites frequently. Cobalt Intelligence reports 10-15% of scrapers need weekly fixes |
| **Official API?** | A few states have APIs (CA, NY). Most don't |
| **Anti-bot measures** | Some states have CAPTCHAs, rate limits. Some charge fees for bulk access |
| **Legal considerations** | Public records. Some states have ToS on their websites. Consider state-specific data resale laws |
| **Update frequency** | Entity filings happen continuously |
| **Engineering effort** | **High** — 50 state scrapers with high maintenance. Cobalt Intelligence has been doing this since 2015 with a dedicated team. Estimate: 6+ months for full coverage |
| **Moat** | High — maintenance is the moat. Cobalt has first-mover advantage |

### 5. Zoning & Land Use Data

| Factor | Assessment |
|--------|-----------|
| **Data source** | 20,000+ municipal zoning codes, typically published as PDFs or on municipal websites |
| **Scrapeable?** | Partially — zoning maps are GIS data (shapefiles), zoning codes are legal text. Need NLP/LLM to parse |
| **Official API?** | Very rare. Some cities have GIS portals (ArcGIS) with zoning layers |
| **Anti-bot measures** | Low |
| **Legal considerations** | Public records (zoning codes are law). GIS data may have licensing terms |
| **Update frequency** | Zoning changes are infrequent (monthly/quarterly) |
| **Engineering effort** | **Very High** — parsing zoning codes requires AI/NLP. GIS data aggregation from thousands of sources. Zoneomics has been doing this for years. Estimate: 6-12 months for MVP |
| **Moat** | Very High — AI parsing + GIS aggregation is extremely hard to replicate |

### 6. State Court Records

| Factor | Assessment |
|--------|-----------|
| **Data source** | State court websites (varying quality) |
| **Scrapeable?** | Varies greatly. Some states (TX, CA, FL) have decent online systems. Others have almost nothing |
| **Official API?** | Very rare |
| **Anti-bot measures** | Some courts block scrapers, require accounts |
| **Legal considerations** | Public records, but some states restrict bulk access. Some courts have ToS. Privacy concerns for certain case types |
| **Update frequency** | Cases filed/updated daily |
| **Engineering effort** | **High** — 50 states with wildly different systems. Estimate: 6-12 months for meaningful coverage |
| **Moat** | High — UniCourt has multi-year head start |

### 7. International Procurement Data

| Factor | Assessment |
|--------|-----------|
| **Data source** | Government procurement portals in each country |
| **Scrapeable?** | Yes, most are public websites |
| **Official API?** | EU TED has an API. Most emerging markets don't |
| **Anti-bot measures** | Generally low |
| **Legal considerations** | Public procurement is public by law in most countries |
| **Update frequency** | Tenders published continuously |
| **Engineering effort** | **Medium** — start with 5-10 key countries. Standardize tender schema. Estimate: 3-4 months for MVP |
| **Moat** | Medium — data is public, but normalization and coverage are the value-add |

### 8. Indian Company & Court Data

| Factor | Assessment |
|--------|-----------|
| **Data source** | MCA21 (companies), eCourts (courts), state land records |
| **Scrapeable?** | MCA21: yes but has CAPTCHAs. eCourts: yes but rate-limited. Land records: varies by state |
| **Official API?** | MCA21 has limited API. eCourts: no. Land: no |
| **Anti-bot measures** | CAPTCHAs on MCA21, rate limiting on eCourts |
| **Legal considerations** | India's IT Act doesn't clearly prohibit scraping public data. Data protection bill (DPDPA) is new |
| **Update frequency** | Filings: continuous. Courts: daily |
| **Engineering effort** | **Medium-High** — CAPTCHAs add complexity. Need to handle Hindi/regional languages. Estimate: 4-6 months for MVP |
| **Moat** | Medium — Indian startups (Surepass, SignalX) are starting to address this |

### 9. Environmental Permits & Violations (US)

| Factor | Assessment |
|--------|-----------|
| **Data source** | EPA ECHO (federal), 50 state DEQ/DEC websites |
| **Scrapeable?** | EPA ECHO has API. State data is scrapeable but fragmented |
| **Official API?** | EPA ECHO: yes. States: rarely |
| **Anti-bot measures** | Low |
| **Legal considerations** | Public records |
| **Update frequency** | Permits and violations updated as they occur |
| **Engineering effort** | **Medium** — EPA ECHO provides foundation. State data adds coverage. Estimate: 3-4 months for MVP |
| **Moat** | Medium — EPA data is free, value-add is state-level integration |

### 10. Lobbying & Political Data (US, state-level)

| Factor | Assessment |
|--------|-----------|
| **Data source** | State lobbying disclosure websites (50 states) |
| **Scrapeable?** | Yes, most states publish lobbying registrations and expenditure reports |
| **Official API?** | Very few |
| **Anti-bot measures** | Low |
| **Legal considerations** | Public records by law |
| **Update frequency** | Quarterly/annual reports |
| **Engineering effort** | **Medium** — 50 state scrapers needed but data formats are simpler than courts or property. Estimate: 2-4 months for MVP |
| **Moat** | Low-Medium — OpenSecrets could expand to cover this |

---

## 8. Recommended Go-To-Market Strategy

### Phase 1: Start Here (Months 1-6)

**Recommended First Niche: Restaurant / Health Inspection Data API**

**Why this niche:**
- Literally zero API providers serving this market nationally
- HDI (Hazel Analytics/Ecolab) is enterprise-only with no public API — serves 250+ brands (Starbucks, Uber Eats) but not developer-accessible
- HDScores offers $0.05/query but appears to have limited current activity
- Clear buyer personas with budget (food delivery platforms, insurance, real estate)
- Data is unambiguously public records
- Many health departments use common platforms (HealthSpace), reducing scraper variety
- Can start with top 50 metro areas and cover 60%+ of US restaurants
- UK already has FHRS API — proves the concept works

**Pricing strategy:**
- Free tier: 100 lookups/month (attract developers)
- Starter: $99/mo — 5,000 lookups (small apps, individual investors)
- Pro: $499/mo — 50,000 lookups (food delivery, insurance companies)
- Enterprise: $2,000+/mo — unlimited, bulk data, SLA, dedicated support

**First customers to target:**
- Food delivery platforms (risk scoring for restaurant partners)
- Commercial real estate investors (due diligence on food service tenants)
- Insurance underwriters (restaurant liability assessment)
- Health & safety consultants
- PropTech companies building restaurant/retail analytics

**Where to find them:**
- Product Hunt launch for developer awareness
- Direct outreach to food delivery platform data teams
- Real estate investor communities (BiggerPockets)
- Food safety conferences (IAFP, NEHA)
- API marketplaces (RapidAPI, API Layer)

### Phase 2: Expand (Months 6-12)

**Add: Professional License Verification API**
- Start with top 5 professions: contractors, doctors, nurses, lawyers, real estate agents
- Same technical infrastructure (web scraping government sites)
- Larger TAM and more diverse buyer base
- Complement building permit data (verify contractor licenses)

### Phase 3: Platform Play (Months 12-18)

**Add: Building Permits (US gaps + international) OR Zoning Data**
- By this point you have scraping infrastructure for government data
- Expand to adjacent niches where the same technical capabilities apply
- Consider becoming a "public records API platform" rather than single-niche

---

## 9. Blue Ocean Opportunities

Niches with **proven demand** but **zero or one API provider**:

| Opportunity | Demand Evidence | Current Providers | Why It's Blue Ocean |
|-------------|----------------|-------------------|-------------------|
| **US restaurant inspection API** | Food delivery platforms need it, insurance needs it, RE investors need it. UK already has national API (FHRS) proving the concept. HDI/Ecolab serves enterprise only (powers Yelp scores). | HDI/Ecolab (enterprise, no public API), HDScores ($0.05/query, limited) | No affordable developer API |
| **Multi-profession license verification API** | $2B+ credentialing industry, every hospital/staffing firm needs it, construction companies legally required to verify | Verifiable (healthcare only), LicensedCheck (limited) | No cross-profession API with good coverage |
| **State-level lobbying data API** | Political intelligence is growing market, companies spend billions on lobbying, transparency demand increasing | OpenSecrets (federal only, nonprofit) | Zero state-level API providers |
| **German/Italian company data API** | Handelsregister has no API, Italian visura system charges per-lookup, KYB demand is massive | North Data (Germany, limited), none for Italy | Near-zero quality API providers |
| **Indian court records API** | 100M+ pending cases, lawyers/litigants/businesses desperate for case tracking | None with API access | Zero API providers, massive market |
| **African company verification API** | Trade finance, AML/KYB, international business expanding into Africa | Almost nothing | Zero comprehensive providers |
| **International building permit API** | Construction market is global, permit data valuable for materials suppliers, investors | None outside US | Zero providers |
| **Municipal zoning code API (affordable)** | Every RE developer needs zoning lookups, proptech companies building tools | Zoneomics (opaque pricing), Gridics (limited) | Only 2 players, both expensive/limited |

---

## 10. Key Risks & Mitigations

| Risk | Mitigation |
|------|-----------|
| **Scraper maintenance burden** | Use common platform detection (HealthSpace, Tyler Technologies). Build monitoring/alerting. Budget 20-30% of eng time for maintenance |
| **Government sites blocking scrapers** | Respect robots.txt, rate limit aggressively, rotate IPs. Consider FOIA requests for bulk data |
| **Legal challenges** | hiQ v. LinkedIn strongly supports scraping public data. Avoid sites requiring login. Get legal review for each state |
| **Incumbent response** | First-mover advantage in underserved niches. Build data quality moat. Lock in contracts early |
| **Data quality issues** | Invest heavily in normalization, deduplication, entity matching. This is the actual value-add |
| **GDPR/privacy** | For EU data, ensure GDPR compliance. Avoid personal data where possible. Focus on business/entity data |
| **Scaling costs** | Start with hosted scraping, move to dedicated infra. Use serverless for variable loads |

---

## 11. Financial Model Sketch

### Restaurant Inspection Data API (Year 1)

| Metric | Estimate |
|--------|----------|
| **Top 50 metros coverage** | ~600K restaurants |
| **Development cost** | $150-200K (2-3 engineers × 6 months) |
| **Infrastructure cost** | $2-5K/mo (scraping + hosting) |
| **Target: 50 paying customers by month 12** | Mix of $99-2,000/mo plans |
| **Year 1 revenue (conservative)** | $200-400K ARR |
| **Year 1 revenue (optimistic)** | $500K-1M ARR (if landing 1-2 enterprise deals) |
| **Breakeven** | Month 10-14 |

### Key unit economics:
- Cost to acquire and maintain data for one restaurant: ~$0.01-0.05/year
- Price per API lookup: $0.01-0.05
- Gross margin: 80-90% at scale

---

## Appendix: Key URLs & Resources

### Free Government APIs Worth Knowing
- US SEC EDGAR: https://www.sec.gov/search-filings/edgar-application-programming-interfaces
- US SAM.gov: https://open.gsa.gov/api/get-opportunities-public-api/
- US EPA ECHO: https://echo.epa.gov/tools/web-services
- US FEC: https://api.open.fec.gov/
- US FDA OpenFDA: https://open.fda.gov/apis/
- US FSIS Recall API: https://www.fsis.usda.gov/science-data/developer-resources/recall-api
- US BLS: https://www.bls.gov/bls/api_features.htm
- US NPPES (NPI): https://npiregistry.cms.hhs.gov/api/
- UK Companies House: https://developer-specs.company-information.service.gov.uk/
- UK FHRS: https://api.ratings.food.gov.uk/help
- France SIRENE: https://api.insee.fr/
- EU TED: https://ted.europa.eu/
- OpenSanctions: https://www.opensanctions.org/api/

### Competitor Pricing Pages
- Shovels.ai: https://www.shovels.ai/pricing
- UniCourt: https://unicourt.com/pricing
- sec-api.io: https://sec-api.io/pricing
- ComplyAdvantage: https://complyadvantage.com/pricing/
- OpenCorporates: https://opencorporates.com/pricing/
- Zoneomics: https://www.zoneomics.com/pricing/api
- ImportGenius: https://www.importgenius.com/pricing
- HigherGov: https://www.highergov.com/pricing/
- Regrid: https://app.regrid.com/plans

### Legal Precedents
- hiQ Labs v. LinkedIn (9th Circuit, 2022): Scraping publicly accessible data does not violate CFAA
- Van Buren v. United States (Supreme Court, 2021): Narrowed CFAA's "exceeds authorized access"
- Meta v. Bright Data (2024): ToS violations can still create breach of contract liability

---

*This analysis is based on publicly available information gathered in March 2026. Pricing and coverage details may change. Always verify current pricing directly with providers before making business decisions.*
