<p align="center">
 <h2 align="center">GitHub Readme Stats</h2>
 <p align="center">Get dynamically generated GitHub stats on your readmes!</p>
 <p align="center"><a href="https://github.com/anuraghazra/github-readme-stats">forked from anuraghazra/github-readme-stats</a></p>
 <p align="center">**Please do not fork this repo, fork from the original author. The contents of this fork is modified for my uses and is not intended to take credit for any of the contents. I am using my own "Vercel instance" at Netlify and have removed all links that would use the original author's resources.**</p>
</p>

# GitHub Stats Card

Available ranks are S+ (top 1%), S (top 25%), A++ (top 45%), A+ (top 60%), and B+ (everyone).
The values are calculated by using the [cumulative distribution function](https://en.wikipedia.org/wiki/Cumulative_distribution_function) using commits, contributions, issues, stars, pull requests, followers, and owned repositories.
The implementation can be investigated at [src/calculateRank.js](./src/calculateRank.js)

### Hiding individual stats

To hide any specific stats, you can pass a query parameter `?hide=` with comma-separated values.

> Options: `&hide=stars,commits,prs,issues,contribs`

### Adding private contributions count to total commits count

You can add the count of all your private contributions to the total commits count by using the query parameter `?count_private=true`.

_Note: If you are deploying this project yourself, the private contributions will be counted by default. Otherwise, you need to choose to share your private contribution counts._

> Options: `&count_private=true`

### Showing icons

To enable icons, you can pass `show_icons=true` in the query param.

### Themes

With inbuilt themes, you can customize the look of the card without doing any [manual customization](#customization).

Use `&theme=THEME_NAME` parameter

#### All inbuilt themes :-

dark, radical, merko, gruvbox, tokyonight, onedark, cobalt, synthwave, highcontrast, dracula

You can look at a preview for [all available themes](./themes/README.md) or checkout the [theme config file](./themes/index.js).

### Customization

You can customize the appearance of your `Stats Card` or `Repo Card` however you wish with URL params.

#### Common Options:

- `title_color` - Card's title color _(hex color)_
- `text_color` - Body text color _(hex color)_
- `icon_color` - Icons color if available _(hex color)_
- `border_color` - Card's border color _(hex color)_. (Does not apply when `hide_border` is enabled)
- `bg_color` - Card's background color _(hex color)_ **or** a gradient in the form of _angle,start,end_
- `hide_border` - Hides the card's border _(boolean)_
- `theme` - name of the theme, choose from [all available themes](./themes/README.md)
- `cache_seconds` - set the cache header manually _(min: 1800, max: 86400)_
- `locale` - set the language in the card _(e.g. cn, de, es, etc.)_
- `border_radius` - Corner rounding on the card_

##### Gradient in bg_color

You can provide multiple comma-separated values in bg_color option to render a gradient, the format of the gradient is :-

```
&bg_color=DEG,COLOR1,COLOR2,COLOR3...COLOR10
```

> Note on cache: Repo cards have a default cache of 4 hours (14400 seconds) if the fork count & star count is less than 1k, otherwise, it's 2 hours (7200 seconds). Also, note that the cache is clamped to a minimum of 2 hours and a maximum of 24 hours.

#### Stats Card Exclusive Options:

- `hide` - Hides the specified items from stats _(Comma-separated values)_
- `hide_title` - _(boolean)_
- `hide_rank` - _(boolean)_ hides the rank and automatically resizes the card width
- `show_icons` - _(boolean)_
- `include_all_commits` - Count total commits instead of just the current year commits _(boolean)_
- `count_private` - Count private commits _(boolean)_
- `line_height` - Sets the line-height between text _(number)_
- `custom_title` - Sets a custom title for the card
- `disable_animations` - Disables all animations in the card _(boolean)_

#### Repo Card Exclusive Options:

- `show_owner` - Show the repo's owner name _(boolean)_

#### Language Card Exclusive Options:

- `hide` - Hide the languages specified from the card _(Comma-separated values)_
- `hide_title` - _(boolean)_
- `layout` - Switch between two available layouts `default` & `compact`
- `card_width` - Set the card's width manually _(number)_
- `langs_count` - Show more languages on the card, between 1-10, defaults to 5 _(number)_
- `exclude_repo` - Exclude specified repositories _(Comma-separated values)_
- `custom_title` - Sets a custom title for the card

> :warning: **Important:**
> Language names should be uri-escaped, as specified in [Percent Encoding](https://en.wikipedia.org/wiki/Percent-encoding)
> (i.e: `c++` should become `c%2B%2B`, `jupyter notebook` should become `jupyter%20notebook`, etc.) You can use
> [urlencoder.org](https://www.urlencoder.org/) to help you do this automatically.

#### Wakatime Card Exclusive Options:

- `hide` - Hide the languages specified from the card _(Comma-separated values)_
- `hide_title` - _(boolean)_
- `line_height` - Sets the line-height between text _(number)_
- `hide_progress` - Hides the progress bar and percentage _(boolean)_
- `custom_title` - Sets a custom title for the card
- `layout` - Switch between two available layouts `default` & `compact`
- `langs_count` - Limit number of languages on the card, defaults to all reported langauges
- `api_domain` - Set a custom API domain for the card, e.g. to use services like [Hakatime](https://github.com/mujx/hakatime) or [Wakapi](https://github.com/muety/wakapi)
- `range` – Request a range different from your WakaTime default, e.g. `last_7_days`. See [WakaTime API docs](https://wakatime.com/developers#stats) for list of available options.

---

# GitHub Extra Pins

GitHub extra pins allow you to pin more than 6 repositories in your profile using a GitHub readme profile.

### Usage

Copy-paste this code into your readme and change the links.

Endpoint: `api/pin?username=anuraghazra&repo=github-readme-stats`

Use [show_owner](#customization) variable to include the repo's owner username

# Top Languages Card

The top languages card show a GitHub user's most frequently used top language.

_NOTE: Top Languages is the GitHub metric of which languages have the most code on GitHub._

### Usage

Copy-paste this code into your readme and change the links.

Endpoint: `api/top-langs?username=anuraghazra`

### Exclude individual repositories

You can use `?exclude_repo=repo1,repo2` parameter to exclude individual repositories.

### Hide individual languages

You can use `?hide=language1,language2` parameter to hide individual languages.

### Show more languages

You can use the `&langs_count=` option to increase or decrease the number of languages shown on the card. Valid values are integers between 1 and 10 (inclusive), and the default is 5.

### Compact Language Card Layout

You can use the `&layout=compact` option to change the card design.

# Wakatime Week Stats

Base URL: `/api/wakatime?username=<username>`

---

Please see the original repo from the original author for more details or to contribute. This fork is modified for my uses. This repo is possible due to the original author's work.
