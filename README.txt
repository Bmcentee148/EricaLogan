ERICA LOGAN CLOTHING BOUTIQUE
Marketing site - SPEC BUILD
===============================================================================

WHAT THIS IS
  A pitch/spec build, not a finished site. Sections built so far:
      Hero -> New Arrivals -> What We Carry -> About -> Visit Us
      -> Follow Along -> Footer
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
    hero-desktop.webp             landscape hero, used above 520px
    hero-mobile.webp              portrait hero, used at 520px and below
    share-card.jpg                1200x630 Open Graph / link preview image
    apple-touch-icon.png          180px home-screen icon
    icon-512.png                  spare large icon (not referenced yet)
    icons/                        6 category illustrations, What We Carry
    products/                     6 products x 3 sizes (-400, -520, -820)


===============================================================================
PRODUCTION CHECKLIST
===============================================================================

--- A. BLOCKERS -- wrong or broken if shipped as-is ---------------------------

  [x] DOMAIN -- DONE. The real domain is https://ericaloganclths.com/ and it
      is now wired in everywhere:
        - <link rel="canonical"> and og:url in the <head>
        - og:image and twitter:image switched to absolute URLs
        - JSON-LD "url", "image" (absolute) and "hasMap" added
        - robots.txt and sitemap.xml created, both referencing the domain
      If the domain ever changes, grep for  ericaloganclths.com  -- it appears
      in index.html, robots.txt and sitemap.xml and nowhere else.

      NOTE: that domain currently answers on /password, which is the Shopify
      store-lock path. Confirm who controls the DNS before cutover.

  [ ] PRICES ARE INVENTED. All six were made up to fill the layout ($52-$88).
      Search for  card__price  and replace with real prices, or delete the
      six spans if they would rather not publish pricing.

  [ ] HERO PHOTOS - CONFIRM THESE ARE THE REAL SHOP. Both heroes and the
      share card now use the bright interior supplied on 15 Aug. It matches
      the product photography (light plank floor, white walls, gold rails);
      the previous images did not - they had dark wood floors. If this one is
      a real photo of the Islip store, this item is DONE and the hero is
      accurate. If it is another AI render, it still has to be replaced
      before launch.
      img/hero-mobile.webp is a portrait crop of the same photo, taken from
      x=360 of the source - the calmest part of the frame for text to sit on.

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

  [x] OWNER NAMES - CONFIRMED by the owners: Tracy, with daughters Sidney
      and Andrea. Used in the About section. "Erica Logan" is a brand name
      drawn from names meaningful to the family, not a person.

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

  [ ] Hero photos - see BLOCKERS. Confirm the new bright image is real.
  [x] Share card - rebuilt from the new hero. Keeps a dark left panel
      because the wordmark asset is white; on a bright card it would vanish.
  [x] Product photos - real, and good. Consistent hanger, rail, floor and the
      Erica Logan hang tags visible. A snapshot in time; swapped weekly.
  [ ] Category icons - AI-generated watercolour illustrations. Visually
      consistent with the palette, but confirm the client is comfortable
      using AI artwork and check whatever licence applies.
  [x] Photo of the owners - supplied and in use in About. Cropped at 74% of
      the original height to drop the foreground merchandise while keeping
      the signage and all three faces. Served at 560/900/1200.
  [ ] The other storefront photo supplied is the OLD Hauppauge shop (door
      reads 926, balloons = grand opening). Not used anywhere. Now that the
      About copy mentions the Hauppauge-to-Islip move it could earn a place
      there, but only if clearly framed as the original location.


--- E. NOT BUILT YET ----------------------------------------------------------

  [ ] 404 page.
  [ ] robots.txt and sitemap.xml.
  [ ] Analytics. Nothing is installed.


--- F. WORTH DOING ------------------------------------------------------------

  [ ] Tell them their Facebook page still shows the old Hauppauge address
      (926 Wheeler Rd). Free goodwill, and it is actively costing them
      walk-ins and NAP consistency.
  [ ] Ask whether their Google Business Profile is claimed and verified. For
      a walk-in shop that outranks anything on this site for local search.


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

THE HERO IS LIGHT TYPE ON A DARK SCRIM
  Headline white, italic in --gold-lt (#CFA470, the dark-background gold),
  over a dark left-to-right scrim. The photo is a mid-tone interior (mean
  luminance ~144), so it needs a fairly strong scrim to carry white type -
  the scrim runs .74 at the left edge falling to 0 by 96%. That is 80% of
  the strength white type would normally want - deliberately pulled back so
  the shop still reads bright, which is what the client asked for. Measured
  contrast sits at 7.9:1 or better everywhere, well clear of AA. Below about
  60% strength the mobile headline starts failing, so that is the floor.
  If a much brighter photo is ever swapped in, this has to flip to ink type
  on a LIGHT veil, with the italic in --gold-ink (#7A5E30). Both golds exist
  in the token list for exactly that reason: --gold-lt for dark backgrounds,
  --gold-ink for light ones.

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
  phone ~455KB / desktop 1x ~510KB / desktop 2x ~775KB
  Plus ~67KB of Google Fonts. The map adds ~1.8MB only if clicked.


===============================================================================
SOURCES FOR ANYTHING FACTUAL ON THE PAGE
===============================================================================
  About section copy + names            supplied directly by the owners
  Hauppauge May 2022 -> Islip move      supplied directly by the owners
  Hours, "mother & daughters owned"  their Instagram bio, @ericaloganclothing
  Islip address                      business listing + Google geocode
  Phone                              their Facebook page (old address on it)
  Shoes, private shopping parties    their own Facebook page text
  Weekly arrivals / Wednesdays       business listing
  Owner names                        AI search summary only - UNVERIFIED
