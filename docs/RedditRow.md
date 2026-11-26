

# RedditRow

One row of /dimensions/reddit. Fields depend on view: subreddits (subreddit, citations, unique_authors, positive, negative, neutral, positive_pct, negative_pct, yours, url), authors (author, citations, subreddits, extra_subreddits, leaning, positive, negative, neutral, brands, yours, url), threads (url, title, subreddit, author, subreddit_yours, author_yours, yours, citations, latest_cited_at, upvotes, comments, avg_position, sentiment, archived, posted_at) and breakdowns (breakdown, key, count, pct).

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**subreddit** | **String** | Subreddit name without the r/ prefix; null on a thread whose subreddit is unknown |  [optional] |
|**author** | **String** | Reddit username; null on a thread whose author is unknown |  [optional] |
|**url** | **String** | The subreddit, author profile or thread URL |  [optional] |
|**title** | **String** | Thread title, read from the post or its URL (view&#x3D;threads) |  [optional] |
|**citations** | **Integer** | Reddit citations of the row in the window |  [optional] |
|**uniqueAuthors** | **Integer** | Distinct authors cited in the subreddit (view&#x3D;subreddits) |  [optional] |
|**positive** | **Integer** | Citations in answers with a positive or very positive sentiment |  [optional] |
|**negative** | **Integer** | Citations in answers with a negative or very negative sentiment |  [optional] |
|**neutral** | **Integer** | Citations in answers with a neutral sentiment |  [optional] |
|**positivePct** | **BigDecimal** | positive over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) |  [optional] |
|**negativePct** | **BigDecimal** | negative over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) |  [optional] |
|**yours** | **Boolean** | Whether the account claims the subreddit or author as its own (on threads, either of them) |  [optional] |
|**subreddits** | **List&lt;String&gt;** | The first subreddits the author was cited in (view&#x3D;authors) |  [optional] |
|**extraSubreddits** | **Integer** | Further subreddits the author was cited in, beyond those listed (view&#x3D;authors) |  [optional] |
|**leaning** | **String** | positive, negative or neutral, whichever sentiment has more of the author&#39;s citations (view&#x3D;authors) |  [optional] |
|**brands** | [**List&lt;RedditAuthorBrand&gt;**](RedditAuthorBrand.md) | Brands the content of the author&#39;s cited posts names, your own first (view&#x3D;authors) |  [optional] |
|**subredditYours** | **Boolean** | Whether the account claims the thread&#39;s subreddit (view&#x3D;threads) |  [optional] |
|**authorYours** | **Boolean** | Whether the account claims the thread&#39;s author (view&#x3D;threads) |  [optional] |
|**latestCitedAt** | **OffsetDateTime** | The thread&#39;s most recent citation (view&#x3D;threads) |  [optional] |
|**upvotes** | **Object** | Upvotes as the scraped post reports them, a number or a numeric string, or null when unknown (view&#x3D;threads) |  [optional] |
|**comments** | **Object** | Comment count as the scraped post reports it, a number or a numeric string, or null when unknown (view&#x3D;threads) |  [optional] |
|**avgPosition** | **BigDecimal** | Average rank of the thread&#39;s citations, 1 &#x3D; first; null when no citation has a visible rank (view&#x3D;threads) |  [optional] |
|**sentiment** | **String** | The most frequent sentiment of the answers that cite the thread; null when none is rated (view&#x3D;threads) |  [optional] |
|**archived** | **Object** | Whether the thread is archived as the scraped post reports it, usually a boolean, or null when unknown (view&#x3D;threads) |  [optional] |
|**postedAt** | **OffsetDateTime** | When the thread was posted; null when unknown (view&#x3D;threads) |  [optional] |
|**breakdown** | **String** | sentiment, model or country (view&#x3D;breakdowns) |  [optional] |
|**key** | **String** | The slice, a sentiment label, a model or an uppercase country code (view&#x3D;breakdowns) |  [optional] |
|**count** | **Integer** | Reddit citations in the slice (view&#x3D;breakdowns) |  [optional] |
|**pct** | **BigDecimal** | Share of the slice within its breakdown, 0-100 (view&#x3D;breakdowns) |  [optional] |



