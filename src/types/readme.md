# ISalons

## Поле `type`

- Если `type` не указан → салон показывается везде (в т.ч. в футере).
- Если `type` указан и включает `'footer'` → показывается в футере.
- Если `type` указан и НЕ включает `'footer'` → в футере не показывается.

То есть `type` работает как “белый список” только когда он задан. Без него — показ везде.

Соберу точный список всех мест в проекте, где фильтруют по полю `type` из **salons.json**.

Вот все файлы, где есть проверка `!salon?.type || salon?.type.includes(...)` для данных из `salons.json`:

- src/components/ExtendedFooter.astro
- src/components/Header/Header.astro
- src/components/Contacts.astro
- src/components/Modals.astro
- src/components/PageTypes/Landing.astro
- src/components/PageTypes/LandingGAC.astro
- src/components/PageTypes/LandingHAVAL.astro
- src/components/PageTypes/Site.astro
- src/components/PageTypes/SiteAlphaCenter.astro
- src/components/SpecialSalonsInfo.astro
- src/const.js
- src/pages/__import.astro
- src/pages/__trade-in.astro
- src/pages/contacts.astro
- src/pages/cookie-policy.astro
- src/pages/models/[...slug].astro
- src/pages/privacy-policy.astro
- src/pages/test-drive.astro

## Поле `hidden_in`

Если нужно скрыть адреса в каком-либо регионе/регионах, то указываем `"hidden_in": ["footer", "map"]` - адрес не будет указан в футере и на карте, даже если по какой-то причине был указан `"type"` с перечнем регионов, в который не входили вышеперечисленные регионы. То есть `"hidden_in"` приоритетнее.