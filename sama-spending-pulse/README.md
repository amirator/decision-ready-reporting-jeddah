# Saudi consumer spending pulse (SAMA point-of-sale data)

**Repo:** https://github.com/amirator/ksa-pos-spending-dashboard

A Python and DuckDB SQL pipeline with a Power BI-style dashboard tracking card spending at points of sale across Saudi Arabia: **307 weeks** of official Saudi Central Bank (SAMA) data, May 2020 to March 2026, with **23 automated checks** in `tests/test_data_quality.py`.

## Why the checks exist

I don't present a result until it has been tested against its source. Public data has quirks: SAMA replaced one series with another mid-2025, weeks can go missing, and a figure that looks fine on a chart can be off because of a join, a duplicate or a units mismatch. So the checks verify the raw files against a recorded hash, that there are no duplicate keys or gaps in the weekly series, that sectors add up to the national total, that week-on-week changes recomputed from the levels match SAMA's published change, that the old and new releases agree where they overlap, and that every headline number in the summary traces back to the computed KPIs. If a check fails, the finding doesn't ship. It's the same rule I use at work before any figure goes to the CEO.

## Limitations

- The data is national and city level; it cannot show individual merchants or customers.
- Sector trends stop at July 2025 because the new SAMA release splits and renames sectors.
- SAMA updates the series weekly, so a refresh can change the latest figures; the committed outputs match the snapshot recorded in that repo's manifest.
