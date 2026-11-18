# SE Ranking OpenAPI Specification

This repository contains [OpenAPI](https://www.openapis.org/) specifications for the [SE Ranking API](https://seranking.com/api).

Developers can use these specs to generate client libraries, explore endpoints in tools like [Swagger UI](https://swagger.io/tools/swagger-ui/) or [Redocly](https://redocly.com/), or integrate SE Ranking data into their workflows.

## Changelog

See [GitHub Releases](https://github.com/seranking/openapi/releases) for a history of spec changes.

## Directory Structure

| Directory  | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| `/openapi` | The latest OpenAPI specs for all SE Ranking APIs, in JSON + YAML |

## Specs

### `/openapi`

| API                  | YAML                       | JSON                       | Documentation                                                      |
| -------------------- | -------------------------- | -------------------------- | ------------------------------------------------------------------ |
| Data API             | `data-api.yaml`            | `data-api.json`            | [seranking.com/api/data](https://seranking.com/api/data/)          |
| Project API          | `project-api.yaml`         | `project-api.json`         | [seranking.com/api/project](https://seranking.com/api/project/)    |
| Local Marketing API  | `local-marketing-api.yaml` | `local-marketing-api.json` | [seranking.com/api/local-marketing-api](https://seranking.com/api/local-marketing-api/) |
| SE Visible API       | `se-visible-api.yaml`      | `se-visible-api.json`      | [seranking.com/api/se-visible](https://seranking.com/api/se-visible/) |

The YAML and JSON file of each API contain the same specification. Use whichever format your tooling prefers.

The specs follow the public API documentation: every endpoint, parameter and response field described there is in
the spec, with the documented request and response examples. Each operation links back to its documentation section.

## Available APIs

### Data API

SEO data for any domain, URL or keyword:

- **Backlinks**: backlink profiles, referring domains, anchors, authority scores and historical trends
- **Domain Analysis**: organic and paid keyword rankings, competitors, traffic estimates and domain overviews
- **Keyword Research**: search volume, keyword difficulty, similar, related, question and long-tail keywords
- **AI Search**: brand and domain visibility in AI-generated answers, leaderboards and prompt-level data
- **SERP**: search engine results pages collected on demand
- **Website Audit**: technical SEO audits with crawl data, issues and page-level analysis
- **Account System**: subscription and credit balance

### Project API

The SE Ranking projects in your account: projects and project groups, keywords and rankings, search engines,
competitors, URL tags, Google Search Console data, the marketing plan, website audits, Backlink Checker and
AI Results Tracker.

### Local Marketing API

Read-only data for your Local Marketing locations: location profiles and overviews, local rankings, Google Business
Profile reports, business listings, reviews and Local Marketing audits.

### SE Visible API

Brand visibility in AI engines: SE Visible projects, brands, topics and prompts, prompt results, sources, engines,
locations and the subscription.

## Authentication

All four APIs are served from `https://api.seranking.com` and use the same SE Ranking API key. Send it in the
`Authorization` header with the `Token` scheme (recommended):

```bash
curl 'https://api.seranking.com/v1/account/subscription' \
  -H 'Authorization: Token YOUR_API_KEY'
```

or as the `apikey` query parameter:

```
https://api.seranking.com/v1/account/subscription?apikey=YOUR_API_KEY
```

Create a key on the [API Dashboard](https://online.seranking.com/admin.api.dashboard.html). See
[Getting API access](https://seranking.com/api/how-to-get-api/), [API rate limits](https://seranking.com/api/rate-limits/)
and the [API credit system](https://seranking.com/api/api-credits-system/).

## Usage Examples

### Import in Swagger UI

Point Swagger UI at the raw spec URL, for example:

```
https://raw.githubusercontent.com/seranking/openapi/main/openapi/data-api.yaml
```

### Generate a Client Library

Using [OpenAPI Generator](https://openapi-generator.tech/):

```bash
openapi-generator-cli generate \
  -i openapi/data-api.yaml \
  -g python \
  -o ./seranking-python-client
```

### Validate the Specs

```bash
npx @redocly/cli lint openapi/*.yaml
```

## OpenAPI Version

The specs use **OpenAPI 3.0**. Both JSON and YAML formats are kept in sync.

## Contributing

If you find issues with the spec (missing fields, incorrect types, documentation errors), please [open an issue](https://github.com/seranking/openapi/issues).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
