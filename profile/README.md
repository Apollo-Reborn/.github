# Apollo-Reborn

A community continuation of the [Apollo for Reddit](https://apolloapp.io/) ecosystem — the iOS tweak that keeps the app alive, and the notifications backend that powers it.

## Background

Apollo for Reddit shut down on June 30, 2023 after Reddit's API pricing changes made it untenable to operate. The app lived on through [JeffreyCA/Apollo-ImprovedCustomApi](https://github.com/JeffreyCA/Apollo-ImprovedCustomApi), an iOS tweak that let sideloaders plug in their own Reddit and Imgur API keys, unlocked the paid Ultra features, and added a long list of genuine improvements the original app never shipped.

In May 2026, JeffreyCA [announced](https://github.com/JeffreyCA/Apollo-ImprovedCustomApi/issues/263) that the project had grown beyond what they could sustain solo, and the tweak was transferred here and renamed to **Apollo-Reborn**. This org is its new home, alongside a revived self-hostable notifications backend, maintained as an open community project.

## Projects

### [Apollo-Reborn](https://github.com/Apollo-Reborn/Apollo-Reborn) (the iOS tweak)

Formerly `Apollo-ImprovedCustomApi`. Lets sideloaded Apollo builds use your own Reddit and Imgur API credentials and adds substantial functionality on top:

- Custom Reddit + Imgur API keys, with fully working Imgur integration and native Reddit media uploads (images, albums, videos)
- All Ultra features unlocked — New Comments Highlightifier, Saved Categories, app icons, themes, Pixel Pals
- **Inline media previews** and **rich link cards** rendered directly in posts and comments
- **Tag filters** to blur NSFW / spoiler posts, with per-subreddit overrides
- **Backup & restore** of Apollo and tweak settings as a `.zip`
- **Bulk in-place translation** with configurable provider and target language
- **Recently read posts**, editable saved categories, user profile pictures throughout the app
- **Liquid Glass** icons and UI enhancements for iOS 26+
- Reddit `/s/` share link support, DuckDuckGo Imgur proxying, auto-collapsing pinned comments, and more

Build instructions, IPA sources, and the full feature list live in the [repo README](https://github.com/Apollo-Reborn/Apollo-Reborn#readme).

### [apollo-backend](https://github.com/Apollo-Reborn/apollo-backend)

The self-hostable notifications backend. A Go service that delivers push notifications, monitors Reddit inbox messages, and runs subreddit/user watchers for sideloaded Apollo builds — forked and reworked from Christian Selig's archived [`christianselig/apollo-backend`](https://github.com/christianselig/apollo-backend).

It pairs with the tweak: point **Settings → Custom API → Notification Backend** at your deployment, and notifications and watchers come back to life. Single-tenant by design — one deployment serves one sideloaded Apollo build, suitable for personal use or sharing with a small group of friends running the same build.

Three hard prerequisites before you start (none are negotiable):

1. A **paid Apple Developer account** — required for the APNs entitlement.
2. A **custom bundle ID**, not `com.christianselig.Apollo` — Reddit's edge WAF blocks the original.
3. An **explicit App ID with Push Notifications enabled** at developer.apple.com — not a wildcard profile.

Full setup, configuration, and the list of changes from upstream live in the [repo README](https://github.com/Apollo-Reborn/apollo-backend#readme).

## Getting started

- **Just want to use Apollo with your own API keys?** → [Apollo-Reborn tweak README](https://github.com/Apollo-Reborn/Apollo-Reborn#readme) for build and sideload instructions.
- **Want push notifications working again?** → [apollo-backend README](https://github.com/Apollo-Reborn/apollo-backend#readme) for self-hosting setup.
- **Hit a bug or have a feature request?** → open an issue on the relevant repo.

## Acknowledgments

- **[Christian Selig](https://github.com/christianselig)** — for building Apollo for Reddit and for open-sourcing the original backend that made this continuation possible.
- **[JeffreyCA](https://github.com/JeffreyCA)** — for years of solo stewardship of Apollo-ImprovedCustomApi (now Apollo-Reborn), and for transferring it to this org so the community can carry it forward.
- **Every [tweak contributor](https://github.com/Apollo-Reborn/Apollo-Reborn/graphs/contributors)** and **[backend contributor](https://github.com/christianselig/apollo-backend/graphs/contributors)** whose work this org builds on.

Apollo-Reborn is currently maintained by [@nickclyde](https://github.com/nickclyde).

## License

Each repository carries its own license — see the `LICENSE` file in each project.
