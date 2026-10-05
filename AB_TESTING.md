# CMCNJ A/B testing

The experiment name is `homepage_hero_v1`.

Visitors are assigned A/B 50/50 and the assignment is persisted in `localStorage`. For QA or campaign-specific links, force a variant with `?variant=A` or `?variant=B`.

Example:
`https://YOUR-DOMAIN/?utm_source=linkedin&utm_medium=organic_social&utm_campaign=img_ascp&variant=B`

The page emits GA4 events including:
- `ab_assignment`
- `cta_click`
- `form_start`
- `form_submit_attempt`
- `generate_lead`
- `form_submit_error`
- `section_view`
- `faq_toggle`
- `calculator_change`
- `link_click`
- `certification_card_flip`

For GA4 reporting, register `ab_variant` and `experiment_name` as event-scoped custom dimensions. Then compare `generate_lead` by variant and break it down by UTM source/medium/campaign.

GA4 also provides approximate country/city geography dimensions.
