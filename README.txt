ERICA LOGAN CLOTHING BOUTIQUE
Marketing site - SPEC BUILD
===============================================================================

WHAT THIS IS
  A pitch/spec build, not a finished site. Sections built so far:
      Hero -> In the Shop -> What We Carry -> About -> Visit Us
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
    hero-desktop.webp             1536x1024 landscape hero, used above 520px
    hero-mobile.webp              768x1024 portrait hero, used at 520px and below
                                  (3:4 crop of the same photo, source x500-1268,
                                  chosen so the racks sit right of the text)
    share-card.jpg                1200x630 Open Graph / link preview image
    apple-touch-icon.png          180px home-screen icon
    icon-512.png                  spare large icon (not referenced yet)
    icons/                        6 category illustrations, What We Carry
    shop/                         In the Shop mosaic. 6 client photos x 3
                                  sizes, all cropped to 4:5. The street shot
                                  (street-style) is the feature tile and runs
                                  700/1100/2100; the other five run
                                  420/620/1040, except graphic-tee, whose
                                  source is only 881px wide so its top size
                                  is 881. See "THE IN THE SHOP MOSAIC" below.


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

  [x] PRICES ARE INVENTED. RESOLVED by deletion. The six product cards and
      their made-up $52-$88 prices are gone - New Arrivals is now In the
      Shop, a photo mosaic with no names and no prices, so there is nothing
      left to price. If they ever DO want pricing on the page it has to come
      from them; do not reconstruct the old cards from git history and
      re-use the numbers, they were invented.

  [ ] PERMISSION FOR THE PEOPLE IN THE PHOTOS. Three of the six In the Shop
      photos show identifiable faces - the street-style shot, the graphic-tee
      shot, and the storefront shot. Erica supplied them, but supplying a
      photo is not the same as the person in it agreeing to sit on a public
      website indefinitely. Confirm each one, and confirm whether any of them
      is a customer rather than family or staff. This is a launch blocker.

  [x] HERO PHOTOS ARE NOT THEIR SHOP. RESOLVED - the AI-generated interiors
      have been replaced with the client-supplied photograph of the real
      shop. hero-desktop.webp is the full frame; hero-mobile.webp is a 3:4
      crop placing the racks to the right of the text; share-card.jpg was
      rebuilt from the same photo at 1200x630. See "THE HERO PHOTO" below
      for what is still outstanding on it.

      NOTE: a different hero photo (the bright interior supplied 15 Aug,
      1774x887, light plank floor and cream walls) was briefly on main and
      has been deliberately superseded by this one. They are two different
      rooms, not two crops of one - if there is any doubt about which is
      the Islip shop, settle that before launch.

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
  [?] In the Shop sub      "Come see what's waiting on Main Street."
                            Came back from the client side during review,
                            not written here - but nobody has confirmed
                            whether it is Erica's own wording or the
                            agency's. Ask; if it is hers, close this.
  [?] Feature caption      "Try it on. Fall in love. Wear it out." Also
                            came back from the client side; same question
                            about whose words they are.
                            NOTE, raised and overruled, recorded so it is
                            not re-litigated: "wear it out" also idiomatically
                            means to wear a garment until it is ruined. The
                            intended reading is "wear it out of the shop" and
                            most people land there. Kept deliberately. If it
                            is ever revisited, "Wear it home." keeps the
                            three-beat rhythm and loses the ambiguity.
  [ ] Lower caption        "Bag in hand, back out onto the street." Mine,
                            still. There were six captions; four were cut
                            because six identical ones read as a template.
  [?] In the Shop band     "Clothes you'll actually wear. / Pieces you'll
                            keep reaching for." Client-side, same question.
                            It is positioning rather than a sourced fact -
                            a promise about the merchandise, not a claim
                            like a price or an address - so it carries no
                            sourcing burden, but it should still be a line
                            they are happy to stand behind.
  [ ] MAIN STREET SAID TWICE. The section sub now says "on Main Street" and
      the band's link under it says "MAIN STREET, ISLIP" - twice inside one
      section, and a third time in the Visit Us sub. Fine for local SEO,
      clunky to read. Easiest fix is to relabel the band link (it points at
      #visit, so "HOURS & DIRECTIONS" does the same job and reads better).
  [ ] In the Shop note     "See what landed this week."
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
  [x] 6 product names      GONE with the product cards. Nothing in In the
                            Shop names or prices a garment, which is the
                            point - see WHY NEW ARRIVALS BECAME IN THE SHOP.

  The hero headline ("The little boutique everyone tells their friends
  about.") came from the client side, so that one is fine.


--- D. IMAGERY ----------------------------------------------------------------

  [x] Hero photos - real shop photo, supplied by the client.
  [x] Share card - rebuilt at 1200x630 from the real hero photo, carrying
      the wordmark treatment: img/logo.webp at 512px over a left panel,
      then a gold rule and ISLIP, NEW YORK in Mulish 700 / .19em / #CFA470.
      Same design as the version that was briefly on main, re-made against
      this photo. Its panel runs deeper and further across than the site
      scrim (.93 at the left edge, clearing at 100%) because this photo's
      left side is busy floral wallpaper rather than a dark aisle - the
      white script needs the extra cover to hold. See SHARE CARD below.
  [ ] HIGHER-RESOLUTION HERO ORIGINAL. The supplied file is 1536x1024. The
      hero is full-bleed, so anything wider than 1536 CSS px upscales, and
      every retina screen upscales it 2x. Ask for the camera original.
      (The superseded 15 Aug photo was 1774x887, so a wider original of
      THIS room may well exist too - worth asking.)
  [x] In the Shop photos - six, all supplied by the client, all real. Phone
      photographs rather than product photography: mixed aspect ratios (0.56
      to 0.76), mixed light, no two framed alike. That is why they are laid
      out as a mosaic and not a product grid - see WHY NEW ARRIVALS BECAME
      IN THE SHOP below - and why they carry a shared grade. An earlier
      draft of this README claimed the mixed light "is the texture, not a
      defect"; that was making a virtue of a constraint. It needed grading.
      Consent on the three with faces in them is still open, in section A.
  [ ] LOW-RESOLUTION SOURCE on the graphic-tee photo: 881x1408, the smallest
      of the six. Fine at the tile sizes it is served at, but it cannot be
      promoted to the feature slot. If they have the camera original, take it.
  [x] The old product photos (img/products, 6 slugs x 3 sizes) were deleted
      when the section changed. They are in git history if they are ever
      wanted back.
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

WHY NEW ARRIVALS BECAME IN THE SHOP
  The client did not want to be updating the website every week, and a
  section called New Arrivals is a promise to do exactly that - it is stale
  the moment it is not true, and a visibly stale "new" section reads worse
  than having none.

  The photographs she then supplied settled it. All six are phone photos of
  the shop and the people in it, not garments on a hanger against a wall.
  Not one of them shows a single item cleanly enough to carry a name and a
  price, and no price on this site may be invented (see the checklist). So
  the section stopped pretending to be a catalogue: it is now six pictures
  of a real shop with one atmospheric line over each, no names, no prices,
  nothing that expires. The weekly churn moved to where it already lives -
  the Instagram CTA at the foot of the section, which is unchanged.

  The announcement bar still says "New arrivals dropping weekly". That is
  fine and should stay: it is sourced (a business listing), it is a claim
  about the shop rather than about the page, and nothing on the page now
  has to be re-shot to keep it true.

THE IN THE SHOP MOSAIC
  Six tiles, every one a 4:5 portrait box:

      >900px   street shot 2 cols x 2 rows, rails and tee stacked beside
               it, the copy band full width, then denim / jewelry /
               storefront across the bottom
      601-900  2 columns, placed EXPLICITLY (grid-template-areas) rather
               than auto-flowed - the band needs both columns and
               auto-placement leaves a hole in the row above it
      <=600    2 columns, with the street shot, the band and the storefront
               shot spanning both, so it reads big / pair / band / pair /
               big rather than a flat grid or a 3,000px single-column scroll

  The feature tile drops its aspect-ratio above 900px and takes its height
  from the two rows it spans, which land at very nearly 4:5 on their own.

THE DARK BAND IN THE MOSAIC (.mosaic__say)
  The first pass at this section was six photographs in six identical boxes
  with six identical captions, and it read as a camera roll rather than a
  designed section - flat, no hierarchy beyond one box being bigger, and no
  typographic voice at all when every other section on the page mixes type
  and image. Three things fixed it, and all three matter together:

    1. The band. --ink-deep with the headline in Playfair and the second
       half in --gold-lt italic - the same roman-then-gold-italic pattern as
       the hero headline. Below the hero this is the only place the brand
       gold appears at any size. Contrast measured: gold-lt on ink-deep is
       7.5:1, cream on ink-deep about 17:1, both fine for the small caps.
    2. Captions cut from six to two, and the survivors made bigger. They sit
       at opposite corners of the desktop mosaic (top-left feature,
       bottom-right storefront), which is what balances it.
    3. The shared grade on the photographs - see below.

  The band is not decoration: it links to #visit, so the section now points
  somewhere.

  Two things in it are hand-set and will silently rot if the copy is edited
  without them:
    - the <br>, which puts one sentence per line and lets the roman/italic
      split fall on the sentence boundary. Without it the two sentences run
      together and the gold italic starts mid-line.
    - the &nbsp; in "reaching&nbsp;for.", which stops "for." being left
      alone on its own line on a phone. At 390px that phrase wraps whatever
      you do; the nbsp only decides where.
  The inset gold frame is a ::before at inset clamp(12px,1.4vw,20px), and
  the band's padding is always comfortably larger than that inset so the
  type never crowds it. If the padding is ever reduced, check both.

THE SHARED GRADE ON THE PHOTOGRAPHS
  Six phone photos taken at different times of day in different light. Left
  alone in identical boxes they read as a camera roll. gen-time grade, baked
  into the .webp files (there is no CSS filter to undo):

    - each photo's mean luminance pulled 45% of the way toward 152, so they
      sit in a common register without being flattened into each other
    - black point lifted to 9/255 - the matte, printed look, and it buries
      the noise in the two dim interior shots
    - a small warm bias (R x1.020, B x0.982) toward the --paper ground
    - saturation to 94%, which mostly calms the jewellery shot

  The numbers are constants at the top of the generator. If a photo is
  swapped, re-run the same grade over it or it will not match the other
  five - this is the step that makes them a set.

  SWAPPING A PHOTO. Three files at the same slug:
      <slug>-420.webp   <slug>-620.webp   <slug>-1040.webp
  (the feature slot is 700/1100/2100 instead - it is twice the width). Crop
  to 4:5 first, then resize; the crop is baked into the files, the CSS only
  does object-fit:cover as a safety net. Never upscale - graphic-tee tops
  out at 881 because its source does. Then update the slug in all three
  srcset entries, the src, the width/height, the alt text and the caption.

  These do NOT need to match each other the way the old product shots did.
  The mosaic is meant to look like a phone camera roll - mixed light and
  mixed framing is the texture, not a defect. What it does need is for the
  street shot to stay in the feature slot, or something with comparable
  resolution: it is the only source above 1200px wide and the only one that
  can fill a 2,100px tile.

  Section weight is about 452KB at 1x desktop, against 279KB for the six
  product cards it replaced. Encoded at webp q72 - these are detailed
  photographs (beads, denim texture, a whole streetscape), so they cost more
  per tile than a garment on a plain wall did. Everything is loading="lazy"
  and the section is below the fold, so none of it touches LCP.

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

SHARE CARD - HOW TO REBUILD IT
  img/share-card.jpg is not a plain crop of the hero, it is a composed
  card: the photo, a left scrim panel, img/logo.webp at 512px wide, an
  86x2 gold rule, then ISLIP, NEW YORK in Mulish 700, .19em tracking,
  #CFA470. Rendered as HTML at 1200x630 on a 2x viewport and downsampled
  to 1200x630, saved JPEG q88 (~127KB). Rendering at 2x matters - the
  wordmark is fine script and JPEG rings badly on it at 1x.

  If the hero photo changes, this has to be re-made; it does not update
  itself. Check two things when you do: that the white script still has
  cover under it (this photo needed a much deeper panel than the previous
  one), and that og:image:width/height still say 1200x630.

  Note the painted "Erica" wall sign is faintly visible behind the
  wordmark. It is their real signage and was left in, consistent with the
  same decision on the hero, but it does put two "Erica"s on one card -
  worth a look if the client is fussy about it.

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
  showing through the scrim drop to ~2.5:1 in small patches on desktop,
  under the 3:1 WCAG minimum for large text. It reads as mottling rather
  than as unreadable text.

  DO NOT FIX THIS BY DARKENING THE SCRIM. The client asked for the scrim
  to be pulled back from where it originally sat; the current values are
  their call, not an oversight. The .hero h1 / .lede text-shadow was
  strengthened instead - a tight shadow behind the letterforms only, so
  the photo's brightness is untouched.

  Know what that bought and what it did not. The shadow lifts the typical
  case (p95 backdrop contrast 4.2 -> 4.5 on desktop, 5.5 -> 6.1 on mobile)
  and visibly firms up the letterforms. It does NOT move the worst-case
  hot spots: those blooms sit between the glyphs, where only the wide
  28px layer reaches, and that layer is too diffuse to darken them -
  measured, pushing its alpha from .35 to .70 moves the worst pixel from
  2.53 to 2.57. So the sub-3:1 patches on desktop are still there. The
  only things that would actually clear them are the scrim (ruled out) or
  a differently framed desktop photo.

  Two other things the new photo introduced:
    - The painted "Erica Logan" wall sign is half-dimmed by the scrim and
      the script "Logan" under it is illegible, so it reads as a smudge
      rather than as signage. On desktop it sits at ~45% width, just right
      of the headline. On mobile the chosen crop puts it at 23-42% width,
      directly behind the gold rule, where the scrim is only 60-78% black.
      This is the cost of the mobile framing: the sign sits between the
      quiet wall and the racks, so any crop that puts empty space behind
      the text also pulls the sign into it. LEFT AS IS on purpose - it is
      their real wall sign, and the alternatives (darker scrim, or
      retouching the sign out of hero-mobile.webp) were both declined.
    - The pendant lights are sliced through by the top edge at wide
      viewports, because the photo is 3:2 and the hero box is much wider
      than that. Only fixable by cropping or a taller source frame.


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
  In the Shop photographs            supplied directly by the owners
  Owner names                        AI search summary only - UNVERIFIED
