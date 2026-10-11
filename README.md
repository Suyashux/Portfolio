# Suyash Krishna Portfolio

A light, editorial portfolio homepage in [index.html](index.html), with a concise product-design introduction, updated portrait, LinkedIn link, downloadable CV, company logos, screenshot previews and links to two Best Buy Ask Blue AI case studies, and a contact section with Bangalore, email, and phone details. The homepage has no build step, package dependencies, or JavaScript. Its profile images and icons live in `assets/`.

The linked case studies are [Progressive login.html](Progressive%20login.html), with screenshots in `images/`, and [untitled folder/agentic-attach-case-study-figma.html](untitled%20folder/agentic-attach-case-study-figma.html), with screenshots beside the page. Both include navigation back to selected work. Existing file paths are preserved. The Agentic Attach page loads its existing fonts from Google Fonts. The alternate Agentic AI draft is not linked from the homepage.

## Preview

Open [index.html](index.html) in a browser. A local server is not required. The homepage uses a consistent white theme regardless of system settings, and supports reduced motion, keyboard navigation, and print styling.

The supplied resume is copied to `assets/suyash-krishna-resume.pdf`. The current portrait is a gently adjusted crop of the supplied photo at `assets/suyash-krishna-portrait.jpg`; the original asset remains available as `assets/suyash-krishna.jpg`. Company logos come from Wikimedia Commons, US Bank's website, and the Australian Digital Health Agency logo image provided for the portfolio. Icons come from Lucide. Review personal contact details and public-use permissions for company marks and project content before publishing.

## Add Your Media

The following notes concern the Progressive Login case study. Use original Figma exports or approved screenshots, not crops of the whole case-study PDF: small text will become unreadable. The multi-tab scenario uses a flow diagram instead of a media placeholder.

| Slot ID | Artifact | What to demonstrate |
| --- | --- | --- |
| `media-overview` | Large-view recommendation and inline nudge | The value-first interaction in context |
| `media-explorations` | Embedded, floating, popover, and drawer comparisons | Alternatives, tradeoffs, and prototype iteration |
| `media-soft-nudge` | Optional sign-in after recommendations | Clear dismissal and uninterrupted shopping |
| `media-history` | History selection and recognition gate | Identity-dependent access and a path back to chat |
| `media-wishlist` | Product save and authentication gate | Phase II scope and cancel/success outcomes |
| `media-chat-close` | Chat-close retention exploration | Distinguish leaving chat from closing a browser tab |

The supplied screenshots are now present and referenced by the case-study pages. For future media replacements, keep paths relative, preserve figure captions, and use the actual image dimensions. A media slot can contain an image as follows:

```html
<div class="media-slot" id="media-overview">
  <img
    src="assets/ask-blue-overview.webp"
    alt="Ask Blue recommends televisions, followed by an optional sign-in card to keep the conversation."
    width="2000"
    height="1000"
    fetchpriority="high"
  >
</div>
```

Use the actual exported image dimensions. For below-the-fold images, use `loading="lazy"` instead of `fetchpriority="high"`. Keep paths relative so the page works inside a GitHub Pages repository path. Captions should explain the design decision, not repeat every label in the screen. For video, use native `<video controls preload="metadata">`, include a transcript or equivalent storyboard, and avoid autoplay.

## Confirm Before Publishing

- **Public disclosure:** confirm that internal screens, PRD details, token names, metrics, and Best Buy references are approved for public portfolio use. Remove customer data and internal identifiers. These materials have not been reviewed for confidentiality.
- **Personal details:** add your preferred portfolio name, team composition, and contact link. The confirmed duration is approximately 1.5 months; exact project dates are not disclosed and are not required.
- **Current status:** released to employees only, with public rollout planned before the US holiday season. This supersedes the PDF's handoff status. Do not describe the planned public rollout as completed or add outcomes without measured evidence.
- **Baseline:** ~23% recognized and ~79% anonymous/unauthenticated are inconsistent as complementary values. The page uses only ~23%; confirm the analytics source, timeframe, denominator, and UT/AT definitions before adding another statistic.
- **Evidence:** the transcript's 1.5-2 average turns comes from Gift Finder and is recalled directional context. Replace or corroborate it with an approved analytics artifact. No formal user study, sample size, or conversion uplift is claimed.
- **Trigger logic:** confirm the missing-location condition and whether caps apply per browser session or conversation. The primary narrative uses the stated once-per-session policy and the explicit AND condition between three shopping turns and one recommendation.
- **Scenario 1:** browser-tab closure is confirmed: BestBuy.com is open in the tab with Ask Blue in a side panel. Validate any proposed exit-time sign-in prompt with engineering; browser-close events cannot reliably display a custom sign-in UI. This is distinct from closing only the chat panel or requesting History again.
- **Scenario 2:** confirm that the other tabs begin anonymously under the same VT, and whether cross-tab stitching and prompt resolution were designed, approved, prototyped, or implemented. The page labels the suggested contract as proposed behavior.
- **Scope:** confirm whether the chat-close exploration entered final scope. Wishlist remains Phase II. Resolve the session-end definition and verify retention and account-change behavior with engineering.

The public narrative uses direct, neutral case-study language, with design ownership stated in the overview, additional scenarios described as design intent, and metrics described as future success measures. Project facts such as the recognized-session baseline are stated without source attribution or implying they were discovered through original research. Source checks and implementation questions belong in these authoring notes, not in the recruiter-facing story. Do not substitute simulated results for measured outcomes.

## Publish On GitHub Pages

The homepage now links to the two supplied case studies. Before pushing or deploying them publicly, confirm the public-disclosure checks above. Include the linked case-study HTML files, `images/`, the referenced Agentic Attach PNGs, and the existing homepage assets. Keep alternate drafts, source transcripts, internal PDFs, and macOS `.DS_Store` changes out of this integration commit. Files already tracked in Git are not made private by leaving them out of a new commit.

In repository **Settings > Pages**, select **Deploy from a branch**, choose `main` and the `/(root)` folder, then save. Verify the homepage, images, and resume download using the Pages URL after deployment.

For more case studies, place each in a separate folder with its own `index.html`, then add its summary and link to the homepage.

## Checks

Browser validation should cover 320px, 390px, 768px, 1024px, and 1440px widths; the persistent light theme under both system color preferences; keyboard focus; case-study links and return navigation; image loading; anchor navigation; and print output. Run a fresh accessibility and performance audit after inserting real media, because image sizes and embeds can change layout and load performance.
