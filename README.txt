ERICA LOGAN CLOTHING BOUTIQUE
Marketing site - SPEC BUILD
===============================================================================

WHAT THIS IS
  A pitch/spec build, not a finished site. Sections built so far:
      Hero -> New Arrivals -> What We Carry -> Visit Us -> Follow Along
      -> Footer
  Some copy, all prices, and both hero photos are placeholders. The
  PRODUCTION CHECKLIST below lists everything that has to change before this
  can go live for a paying client.

DEPLOY
  Drag this whole FOLDER onto netlify.com/drop - not index.html on its own.
  The images live in img/ and the page will look broken without them.

FILE STRUCTURE
  index.html                      the entire site, one file
  favicon.ico                     EL monogram, 16/32/48
  README.txt                      this file
  img/
    logo.webp / logo-500.webp     white wordmark, transparent background
    hero-desktop.webp             1536x1024 landscape hero, used above 520px
    hero-mobile.webp              768x1024 portrait hero, used at 520px and below
                                  (right-half crop of the same photo)
    share-card.jpg                1200x630 Open Graph / link preview image
    apple-touch-icon.png          180px home-screen icon
    icon-512.png                  spare large icon (not referenced yet)
    icons/                        6 category illustrations, What We Carry
    products/                     6 products x 3 sizes (-400, -520, -820)


===============================================================================
PRODUCTION CHECKLIST
===============================================================================

--- A. BLOCKERS -- wrong or broken if shipped as-is ---------------------------

  [ ] DOMAIN. Find/replace  https://REPLACE-WITH-DOMAIN.com  with the real
      URL. 7 occurrences: canonical, og:url, og:image, twitter:image, and
      twice inside the JSON-LD. A canonical pointing at a domain that does
      not exist will keep the whole site out of search results. Do this first.

  [ ] PRICES ARE INVENTED. All six were made up to fill the layout ($52-$88).
      Search for  card__price  and replace with real prices, or delete the
      six spans if they would rather not publish pricing.

  [x] HERO PHOTOS ARE NOT THEIR SHOP. RESOLVED - the AI-generated interiors
      have been replaced with the client-supplied photograph of the real
      shop. hero-desktop.webp is the full frame; hero-mobile.webp is a 3:4
      crop of the right half (the racks); share-card.jpg was rebuilt from
      the same photo at 1200x630. See "THE HERO PHOTO" below for the two
      things still outstanding on it.

  [ ] LOGO LINK. The header logo is still  href="#" . Point it at "/".

  [ ] FOOTER CREDIT. The bottom bar carries "Site by Benchwork Digital".
      Agree it with the client or delete the line - it is commented in
      index.html so it is easy to find.

  [ ] GET DIRECTIONS. Currently a Google Maps *search* URL built from the
      business name. Swap in their actual Google Business Profile link so it
      lands on the verified listing.

  [ ] TEST THE CONTACT FORM after deploying. Netlify Forms only works once
      deployed - it cannot submit from a local file. Confirm the submission
      lands in the Netlify dashboard and that notifications point at an
      address they actually read.


--- B. FACTS TO CONFIRM WITH THE OWNERS ---------------------------------------

  [ ] STREET ADDRESS. A business listing says "454 Main St". Google geocodes
      that to "454 E MAIN St, Islip NY 11751" and the map pin lands correctly.
      Confirm whether the street is signed East Main. This matters more than
      it looks: NAP (name/address/phone) consistency across the site, their
      Google Business Profile and their Facebook is a real local-search
      ranking factor, and a mismatch works against them.
      Appears in: the Visit Us block, the map card, and the JSON-LD.

  [ ] PHONE. (631) 406-7846 comes from their Facebook page - the same page
      that still lists the OLD Hauppauge address. Confirm it reaches Islip.

  [ ] OWNER NAMES. An AI search summary named "Tracy Mankowski" with
      daughters "Sidney" and "Andrea". NOT independently verified. The only
      corroboration is the contact email Sidney@ericaloganclths.com on their
      Facebook. Get spellings directly from them - Brian first heard
      "Tracey", the summary said "Tracy". Publish none of these names until
      confirmed. ("Erica Logan" appears to be a brand name, not a person -
      worth asking where it came from. Usually a good line for About.)

  [ ] CATEGORIES. The six in What We Carry are assumptions. Tops, Sweaters,
      Denim and Bottoms are safe - they are literally in the product photos.
      DRESSES and ACCESSORIES are inferred. SHOES was built and then removed;
      their own Facebook text says "all women's clothes, shoes + accessories",
      so shoes are confirmed and should probably go back in. Note: 7 items
      leaves one centred alone on desktop; 9 fills three clean rows of three.

  [ ] "NEW ARRIVALS DROPPING WEEKLY" (announcement bar). Corroborated by a
      listing saying new arrivals land weekly, "especially on Wednesdays".
      Confirm - and consider naming Wednesdays, which is sharper.

  [ ] THEY ALREADY HAVE A SHOPIFY STORE at ericaloganclths.com, currently
      password-protected behind an "Opening soon" page. Settle whether this
      marketing site sits alongside it, replaces it, or links to it. This
      build assumes NO online shopping - no cart, accounts or checkout.


--- C. COPY I WROTE THAT NEEDS THEIR VOICE ------------------------------------

  All of this was written to fill the layout. None came from them.

  [ ] Hero lede            "Curated pieces, timeless trends, and everyday
                            favorites..." - generic, and now slightly at odds
                            with the headline's stronger voice
  [ ] New Arrivals sub     "Fresh styles. Handpicked for you."
  [ ] New Arrivals note    "New pieces land on the racks every week."
  [ ] What We Carry sub    "A little of everything, chosen one piece at a time."
  [ ] 6 category blurbs    e.g. "washes that wear in, not out"
  [ ] What We Carry close  "Not sure where to start? That's what we're here for."
  [ ] Visit Us sub         "Main Street, Islip. Mother and daughters owned."
                            (the mother/daughters half IS confirmed - it is
                            in their own Instagram bio)
  [ ] Private party line   "Shopping for something specific? Ask about an
                            after-hours private party." The service is real -
                            their Facebook advertises it - the wording is mine
  [ ] Follow Along sub     "See the shop between visits."
  [ ] Meta description, og and twitter descriptions
  [ ] 6 product names      Descriptive, not their SKU names. Note the file
                            named grey_pullover is actually warm brown; it is
                            labelled "Washed Crewneck Pullover" with no colour
                            word, so nothing on the page is inaccurate.

  The hero headline ("The little boutique everyone tells their friends
  about.") came from the client side, so that one is fine.


--- D. IMAGERY ----------------------------------------------------------------

  [x] Hero photos - real shop photo, supplied by the client.
  [x] Share card - rebuilt at 1200x630 from the real hero photo.
  [ ] HIGHER-RESOLUTION HERO ORIGINAL. The supplied file is 1536x1024. The
      hero is full-bleed, so anything wider than 1536 CSS px upscales, and
      every retina screen upscales it 2x. Ask for the camera original.
  [x] Product photos - real, and good. Consistent hanger, rail, floor and the
      Erica Logan hang tags visible. A snapshot in time; swapped weekly.
  [ ] Category icons - AI-generated watercolour illustrations. Visually
      consistent with the palette, but confirm the client is comfortable
      using AI artwork and check whatever licence applies.
  [ ] A photo of the owners on the shop floor. Still the highest-value asset
      missing - About cannot be built well without it.
  [ ] The storefront photo supplied is the OLD Hauppauge shop (door reads
      926, balloons = grand opening). Do not use it on Visit Us. It would
      work in About, telling the Hauppauge-to-Islip story.


--- E. NOT BUILT YET ----------------------------------------------------------

  [ ] ABOUT section. #about is linked twice in the nav and goes nowhere.
      Blocked on owner names, their story, and a photo of them.
  [ ] 404 page.
  [ ] robots.txt and sitemap.xml.
  [ ] Analytics. Nothing is installed.


--- F. WORTH DOING ------------------------------------------------------------

  [ ] Tell them their Facebook page still shows the old Hauppauge address
      (926 Wheeler Rd). Free goodwill, and it is actively costing them
      walk-ins and NAP consistency.
  [ ] Ask whether their Google Business Profile is claimed and verified. For
      a walk-in shop that outranks anything on this site for local search.

  [ ] SCRIM/IMAGE BREAKPOINT MISMATCH. The portrait hero swaps in at 520px
      (the <source> media query) but the lighter mobile scrim starts at
      900px (the @media max-width:900px block). Between 521 and 900px you
      get the wide landscape photo under the scrim meant for the portrait
      crop, so the headline sits on the brightest part of the wallpaper.
      768px is the worst case. Pre-dates this photo, but the old hero was
      dark on the left so it never showed. Align the two numbers.


===============================================================================
HOW THINGS WORK (maintenance notes)
===============================================================================

SWAPPING IN NEW ARRIVALS
  Each product needs THREE files at the same slug:
      <slug>-400.webp   <slug>-520.webp   <slug>-820.webp
  From a 1000x1503 source (2:3 portrait). The three sizes match the srcset
  ladder in index.html - a phone pulls 400, desktop pulls 520, retina pulls
  820. Keep all three or the wrong size gets served.
  Then update the slug, name, price and alt text in index.html.

  Shooting them: same hanger, same rail, same distance, same light every
  time. The grid only reads as a set because the framing matches.

THE MAP IS CLICK-TO-LOAD - LEAVE IT THAT WAY
  The Google Maps embed pulls ~1.8MB of third-party JS and tiles, four times
  the rest of the page. Visit Us shows an address card and only builds the
  iframe when someone presses "Show map". Making it eager takes the page from
  ~545KB to ~2.3MB and hurts Core Web Vitals, which IS a ranking factor.
  The embed itself is not.

THE FOOTER DELIBERATELY DOES NOT REPEAT THE HOURS
  Address, phone and Instagram are duplicated there, but hours are not -
  they already live in three places (below) and a fourth copy is one more
  thing to forget. The footer links to #visit instead.

OPENING HOURS LIVE IN THREE PLACES
    1. the visible <dl class="hours"> list
    2. the HOURS object in the script at the bottom (drives the
       "Open now / Closed - opens Tuesday" badge)
    3. openingHoursSpecification in the JSON-LD
  Change all three together. The badge computes in America/New_York on
  purpose, so someone checking from another timezone still sees the shop's
  real status.

WHY IMAGES ARE IN A FOLDER, NOT BASE64
  Separate files let srcset serve each device the right size - a phone pulls
  ~450KB instead of the ~835KB a single embedded desktop-sized set would
  cost. They also cache, so the weekly photo swap does not force every
  returning visitor to re-download the whole page.

PAGE WEIGHT (own assets, whole page scrolled)
  phone ~470KB / desktop 1x ~575KB / desktop 2x ~840KB
  Plus ~67KB of Google Fonts. The map adds ~1.8MB only if clicked.
  The real hero costs ~65KB more than the AI one it replaced (desktop
  147KB -> 212KB, mobile 89KB -> 104KB) - the floral wallpaper is
  detail-dense and does not compress as well as the old soft-focus aisle.
  Both are written at WebP q76; dropping to q68 saves another ~40KB if
  the budget gets tight.


THE HERO PHOTO
  The scrim was tuned against the ORIGINAL hero, which had a dark, empty
  aisle running down the left side - a naturally quiet bed for the
  headline. The real photo does not have that. Its left half is bright,
  high-contrast floral wallpaper plus a white fridge and white cabinets,
  directly behind the text.

  Measured, it still passes: the gold italic headline averages 6.5-7.3:1
  against its backdrop at every breakpoint. But the brightest blooms
  showing through the scrim drop to ~2.4:1 in small patches on desktop,
  under the 3:1 WCAG minimum for large text. It reads as mottling rather
  than as unreadable text. Strengthening the left stop of the horizontal
  gradient in .hero__scrim is the fix if the client notices it.

  Two other things the new photo introduced:
    - The painted "Erica Logan" wall sign sits at ~45% width, half-dimmed
      by the scrim, and the script "Logan" under it is illegible. It lands
      just right of the headline and reads as a smudge. Nudging
      object-position, or cropping the desktop frame tighter, moves it.
    - The pendant lights are sliced through by the top edge at wide
      viewports, because the photo is 3:2 and the hero box is much wider
      than that. Only fixable by cropping or a taller source frame.


===============================================================================
SOURCES FOR ANYTHING FACTUAL ON THE PAGE
===============================================================================
  Hours, "mother & daughters owned"  their Instagram bio, @ericaloganclothing
  Islip address                      business listing + Google geocode
  Phone                              their Facebook page (old address on it)
  Shoes, private shopping parties    their own Facebook page text
  Weekly arrivals / Wednesdays       business listing
  Owner names                        AI search summary only - UNVERIFIED
