# dusk-li-data

## What is dusk-li?

Dusk-li is a website that rates websites based on their accessibility in terms of their support for **Dark Mode**.

Dark mode is defined by the [Bureau of Internet Accessibility](https://www.boia.org/blog/dark-mode-can-improve-text-readability-but-not-for-everyone) as follows:

> Dark modes and themes are extremely popular and they’re frequently touted as an accessibility solution. While the term "dark mode" can have different meanings for different developers, the basic idea is simple: Instead of displaying dark-colored text over a light background, a dark mode inverts the color scheme to display light-colored text over a dark background. This can create more contrast between the content and the background, limiting eyestrain and improving content readability.

As that page also states, Dark Mode is not a panacea - while it helps with several conditions, it can also hinder other conditions - especially if the dark mode color theme has a low contrast ration.

A truly accessible site from a Brightness and Contrast perspective therefore must meet the following criteria:

1. Dark mode is supported
2. Dark mode will recognise the system setting for light or dark
3. Dark mode can be manually overriden
4. Site contrast is acceptable as assessed by https://color.a11y.com/Contrast/
5. Optionally, the site supports custom themes, ideally without having to create a login to do so.

The website is hosted at https://dusk.li and the data behind it is maintained in yaml files in the [sites-data](/sites-data) directory of this repo.

Anyone can submit a PR to request an addition or change to the site.

Objectionable sites cannot be added. Websites are categorised using [Symantec Sitereview](https://sitereview.bluecoat.com/).

Categories that will not be permitted to be added to the data repository:
+ Adult/Mature Content
+ Child Pornography
+ Compromised Sites
+ Controlled Substances
+ Gore/Extreme
+ Malicious Outbound Data/Botnets
+ Malicious Sources/Malnets
+ Marijuana
+ Nudity
+ Phishing
+ Pornography
+ Potentially Unwanted Software
+ Scam/Questionable Legality
+ Spam
+ Suspicious
+ Violence/Intolerance
+ Weapons

Each yaml file contains data in the following schema:

> **company**: *Site or Company name*

> **category**: *Site category as assessed by [Symantec Sitereview](https://sitereview.bluecoat.com/)*

> **url**: *https://www.example.com*

> **description**: *Brief description of the website*

> **dark_mode**: *None | Manual | Auto (0 Points | 1 Point | 2 Points - substract half a point if the entire site doesn't support dark mode)*

> **mode_configurable**: *No | Yes (0 Points | 1 Point*

> **default_theme_style**: *Bright | Mixed | Dark (0 Points | 1 Point | 2 Points)*

> **supports_custom_themes**: *No | LoggedIn | Yes (0 Points | 1 Point | 2 Points)*

> **contrast_accessibility**: FAIL | PASS (0 Points | 1 Point)

> **accessibility_rating**: *Total of the above scores*

> **last_updated**: *YYYY-MM-DD*