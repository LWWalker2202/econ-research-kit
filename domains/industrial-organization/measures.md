# Industrial organization and regulation: constructing the treatment variable

In industrial organization the treatment is usually a rule rather than a programme: a transaction that had to be notified, a product that left the government pricing catalogue, an item that disappeared from the negative list, a boundary inside which a zone was designated. The measurement problem is that the outcome of interest — concentration, markup, entry — is itself a market-structure object that the same regulation moves. Write down which side of that line each variable sits on before estimating anything, because the same variable is a treatment in one paper and an outcome in the next.

## Constructing the treatment variable

Four definitions cover most designs in this field. Each names the unit at which the rule binds.

| Treatment definition | How it is built | Data source | Implicit assumption | When to use |
|---|---|---|---|---|
| Merger-review exposure | Case-level indicator for firms involved in a notified concentration, coded by outcome (clearance, conditional clearance, prohibition) and by decision date; or an industry-year count of reviewed cases | Merger case lists from the competition authority | Cases that reach review are not selected on the outcome; remedies are binding | Effects of mergers on prices, concentration, entry |
| Price-liberalization exposure | Product-level indicator that the item left the central or provincial pricing catalogue in year t; alternatively the share of industry sales under administered prices | Published pricing catalogues, successive vintages | The timing of item removal is unrelated to item-level price trends | Price, markup, and entry responses to deregulation |
| Entry-restriction exposure | Count of negative-list items covering the industry in each list vintage; or an indicator for the 2014 registration reform by firm type | Market access negative list versions; registration rules | Variation in list content is exogenous to firm outcomes within industry | Firm entry, market structure, productivity |
| Development-zone exposure | Zone designation date crossed with firm location; or the share of a county's area inside a zone boundary | Zone announcements, boundary maps, firm registry addresses | Zone location is not chosen on anticipated growth | Entry, TFP, agglomeration, place-based policy evaluation |

Two further definitions appear often enough to be named, although they are usually studied as environmental policy. 去产能 (capacity reduction) is built as a province-by-industry target or as the share of capacity on published shutdown lists. 环保限产 (production restriction and suspension) is built as a city-by-sector-by-heating-season indicator. Both are market-structure shocks: they remove capacity, raise the measured concentration of surviving firms, and move markups. Use them as treatments only after controlling for the environmental layer, or use the environmental layer as a treatment and hold market structure as the outcome.

The second table fixes the market-structure constructs, which carry as much identification risk as the treatment itself.

| Construct | How it is built | Data source | Implicit assumption | When to use |
|---|---|---|---|---|
| Concentration (HHI, CR4) | Sum of squared market shares, or the top-four share, computed within an industry-year from firm sales | Firm census or above-scale industrial survey; customs values for traded goods | The industry code is the relevant antitrust market and coverage is constant across years | Describing market structure; as an outcome of entry or merger policy |
| Markup | Output elasticity of a variable input divided by its revenue share, from an estimated production function; or price over average cost from accounting data. The production-function route follows Hall (to confirm against the official codebook) and De Loecker and Warzynski (to confirm against the official codebook) | Firm-level production data; listed-firm financial statements | Cost minimization, a single-product firm, and a production function that is stable across firms | Rent extraction, pass-through, competition intensity |
| TFP | Residual from a production function estimated by control-function or dynamic-panel methods: Olley and Pakes (to confirm against the official codebook), Levinsohn and Petrin (to confirm against the official codebook), Ackerberg, Caves, and Frazer (to confirm against the official codebook) | Firm-level capital, labour, materials, output | The proxy variable corrects for simultaneity; deflators are consistent across inputs | Productivity dispersion, reallocation, policy effects on efficiency |
| Market segmentation index | Dispersion of relative prices of comparable goods across regions; alternatively divergence of regional production structures | Regional price indices, commodity price monitoring, industrial output by province | Price gaps reflect barriers rather than transport costs and quality | Local protection, market integration, reform effects |
| Entry and exit rates | Registrations and deregistrations per industry-region-year; or appearance in and disappearance from a firm panel | Business registry; the industrial survey panel | Registration means operation, and disappearance means exit | Dynamics of competition, policy effects on turnover |

## Identification assumptions by definition

| Definition | What must hold | What would break it |
|---|---|---|
| Merger-review exposure | Notification is not driven by the expected price effect; the review outcome is observed before the outcome window | Only cases with large expected effects are notified, so the sample is selected on the outcome |
| Price-liberalization exposure | Items are removed for reasons unrelated to their price path; the catalogue vintage is dated before the outcome | Items are liberalized because prices already fell or rose abnormally |
| Entry-restriction exposure | The list vintage changes for institutional reasons rather than in response to industry performance | The list is revised to accommodate incumbent firms |
| Development-zone exposure | Designation is not anticipated and zone boundaries are not drawn around already-growing places | Zones are placed where growth was already under way |
| HHI as an outcome | Coverage is constant across the threshold changes in the underlying data | Coverage changes exactly when the policy changes |
| Markup as an outcome | The production function is common enough across firms that one elasticity is defensible | Firms differ in technology, so the elasticity is firm-specific |

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Computing HHI only on firms above the survey size threshold | Concentration is overstated, and the bias moves with the threshold | Report the coverage rule for every year; reweight to the registry universe or state the bound |
| Using one deflator for output and a different one for inputs | Measured markup absorbs relative price changes | Use a consistent deflator set and show results under alternatives |
| Pooling years across an industry-classification revision | The HHI series jumps at the revision and the jump is read as a competition effect | Recode all years to one classification vintage and report the crosswalk |
| Treating zone designation as an absorbing treatment | Later expansions and re-designations contaminate the comparison group | Use a staggered design with cohort-specific pre-trends |
| Matching the industrial survey to customs records on firm name only | False matches concentrated among large firms, understating the match rate | Match on a unique identifier, report the match rate by size, and validate against trade totals |
