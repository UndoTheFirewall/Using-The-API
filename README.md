# Introduction

The True Story API fetches the latest news aggregrated from a variety of sources and creates a news feed combined by news from many different sources.

## Use Cases

We encourage you to use the API to bring real news to your website, app, or software. The API is free to use and you can use it to create your own news feed.
The news feed that you generate on [Undo The Firewall](https://undothefirewall.com) is a static version of the news from Russia - and shows the most important news over a 7 day period.
If you want to provide Russian visitors with a news feed that is uncensored and always up to date - pulling the very latest news - you can interface directly with the API.

We would suggest that you pull from the API via. a server-side language - instead of interfacing with the API via. Javascript. Because the API endpoint is most likely blocked in Russia then using the API via. a server-side language will make sure the news gets displayed even if the endpoint is blocked in Russia. Because the endpoint is never exposed to the user, it cant be blocked.


## Description of the API

The API is a RESTful API that uses JSON as its communication format. 
Below you will find a description of the API endpoints and how to use them.

```http
GET https://thetruestory.news/api/widget/main?edition=ru&limit=20&period=24hd&with_snippets=1&with_icons=1
```

| Parameter       | Type     | Description                                                                                      |
|:----------------|:---------|:-------------------------------------------------------------------------------------------------|
| `edition`       | `string` | The edition of the news stories you want to see. Options are: RU, EN, NY, UKR, IA, UL            |
| `limit`         | `number` | Number of stories you want the API to fetch                                                      |
| `period`        | `string` | The number of days the API should pull the main stories from - can be 12h, 24h, 7d               |
| `with_snippets` | `string` | Should the API pull headlines only or also a small textual snippet. Can be 0 (false) or 1 (true) |
| `with_icons`    | `number` | Should the API should deliver icons from the news service Can be 0 (false) or 1 (true)           | |

## Only show the latest news to those with Russian as their language settings

If you want to only show the news feed to those with Russian as their language settings you can use the following code (Javascript example)

```
if (navigator.language === 'ru-RU') {
  // Display the news feed
}
```
